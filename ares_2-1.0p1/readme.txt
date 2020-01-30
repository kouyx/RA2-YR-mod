A R E S  R E A D M E
--------------------

For credits and further information on how to use Ares with your mod,
have a look at index.html in the Documentation folder.


USING THE STANDALONE VERSION OF ARES
------------------------------------

Since you are reading this readme, it is assumed you have already
downloaded the Ares Standalone Package.

1. Ares works with Command & Conquer: Yuri's Revenge version 1.001 only. Update
   your copy of the game if necessary.

2. Extract the Ares Standalone Package into your YR game directory.
   Make sure Syringe.exe, Ares.dll, Ares.dll.inj and ares.mix are all directly
   in that directory, not in a sub-folder.

3. Ensure that you have installed the following runtime files from Microsoft.
   Please note that you will need the x86 version of the runtime files, even if
   you have a 64 bit processor.
   https://go.microsoft.com/fwlink/?LinkId=746571

4. Ensure that gamemd.exe and syringe.exe are both set to the same Compatibility
   Mode.

5. Click in the Windows Explorer's address bar while you're in the game 
   directory. Type 
       Syringe "gamemd.exe"
   and press Enter. 
   Or use the included RunAres.bat or make your own a batch file to do that for
   you... no difference.

6. If Ares is active, it will show its version number on the startup screen as
   well as in the lower right corner of the main menu. If this does not happen,
   inspect syringe.log for further information.


CREATING A MOD WITH ARES
------------------------

When Ares is active, it is integrated into Yuri's Revenge and all its features
can be used as if they were part of the original game. Creating a mod involves
setting up Ares and distributing it to your players along with the mod files.

1. Follow the steps above to extract the Ares files into the game folder and
   launch the game via Syringe. Ares is now active.

2. Write some modifications. You can now edit the INIs and make use of all the
   new Ares features and fixes. See the documentation for more information.

3. To distribute your mod, include Ares.dll, Ares.dll.inj, ares.mix,
   Syringe.exe, license_ares.txt, and license_syringe.txt along with your
   modified game files.

4. Make sure that players also launch the game as described in step 5 above. For
   that you can include RunAres.bat also or use a custom launcher or client.

5. Note that all players have to have the same versions of the Ares files.
   Incompatible versions cause Reconnection Errors in multiplayer games.

--------------------------------------------------------------------------------

Please mind the licenses of all involved files, read the manual before asking
questions, and file bugs you find in the Bugtracker (not the forums) so they can
be fixed.

We will happily answer questions about Ares at the forums or in chat, but
THERE IS NO OFFICIAL NPATCH > ARES MIGRATION SUPPORT.
The reasons for this have been discussed at length and will not be reiterated
in this readme. If you wish to migrate from NPatch, feel free to coordinate
your efforts with other NPatch users.


Most importantly, enjoy Ares! :)
The Ares Development Team


URLS
----
Ares: http://ares.strategy-x.com/
Project: https://launchpad.net/ares
Bugtracker: https://bugs.launchpad.net/ares
Source code: https://github.com/Ares-Developers/Ares
ModEnc: http://www.modenc.renegadeprojects.com/Ares
Chat: http://tinyurl.com/l4k9eaz (Browser) or
      irc://chat.freenode.net/RenProj (IRC Client)

--------------------------------------------------------------------------------
For information about copyrights and other legal information, read the
respective license files.

EOF