# mvdbmake
Start of a compiler/dependency tool

General idea is to come up with some concepts and then tools to handle including modules that are independent to your project.

As an example lets say you want to use the WOBJ library with a new tool you are making.  Instead of relying on a global
WOBJ library that may be updated and break your tool you can include WOBJ directly into your project.

As a basic overview

1. Seperate BP file for your project.  It is named for your project.  Lets say MVDEMOBP.
bp file would be MVDEMOBP.BP

All code you make should be prefixed with MVDEMOBP. 

Now, when you want to include WOBJ into your project, a sub data section is created under MVDEMOBP file
MVDEMOBPBP,WOBJ.BP

All code would then be renamed MVDEMOBP.<NAME OF PROGRAM>
All code doing a CALL WOBJ would be re-written to CALL MVDEMOBP.WOBJ.
  
At compile time you now have your own version of WOBJ and never have to be worried about another version.

Other items to think about

1. tmp files
2. commons
3. includes

The goal here is to duplicate the package concepts code such as .net, node, and javascript do in which they can include all dependencies directly into their project.

