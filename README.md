# BCPLCopyFile02

Enhancement to the first copy file. Green screen coolness! 

I have spent too much time playing Fallout 4 recently (and not enough time on this) so fancied recreating the green screen image used on terminals etc. This involves calling the VDU commands but this is not simple as they are not included by default in the build. For this we need NEEDCIN to add in the required code. This is somewhat like Inludes or Imports in modern languages.

The basic process is to add the NEEDS directive to the code, build and then run the NEEDCIN function to get it to add the required CINT code.

Function: - 

Use BCPL to copy a file byte by byte using hardcoded file names. Updates the display to green screen.

This is a simple example of using BCPL to step through a file a byte at a time in order to copy its contents. Written and tested on BeebEm and a BBC Model B. I have a 6502 second processor attached as it speeds things up somewhat.

Usage: - 

You will need the BCPL ROM present in your BeebEm (can be downloaded from the net) or in your Beeb.

Load BCPLS into disk 0. Load BCPLT into disk 1. Note that BCPLS is effectively the 'BCPL source' and BCPLT is the 'BCPL test' disc. There are two discs due to the limitations of DFS and I believe 31 (or 32) files only?

Type *BCPL

On drive 0 type "BCPL COPYFL CODE" to build. This will build into RAM. Type "SAVE CODE" to save it to disk.

Type *Drive 1 to move to BCPLT

Type "SAVE CODE" to save it to Drive 1 

Type "NEEDCIN CODE LIB EXE". This will include the code for the VDU command (which is in the LIB file) and create a file called EXE

Type "EXE" to run the program

Once completed it should turn the text green and show two *INFO reports to show the created file is the same size as the original.

You can use *DESTROY COPIED to remove the target file (answer yes and then yes).

Note that I have included the source file code separately to the .ssd files for ease of reading. The BCPLS.ssd disc image contains the source files.
