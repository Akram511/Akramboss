### You only need to follow this guide if you're using NTR. HzMod supports this feature out of the box, you only need to open multiple instances of Snickerstream!

This tutorial gives for granted that you've already set up a working streaming setup for a single n3DS using NTR. If you haven't done that already, follow this guide.

1. First of all, copy your entire Snickerstream installation to a different folder. (You could use the same one via some command line options, but for simplicity's sake we're going to do this instead)
1. Connect one of your n3DSes' microSD card to your PC (or use FTP/microSD management to read it microSD from your PC)
2. Open the _copied_ Snickerstream installation **(not the original one!)**, then click on "Advanced".
3. Set Listen port to a valid value (must be >1 and <=65535, plus some ports cannot be used due to an internal NTR bug: in case you choose one of them, Snickerstream will tell you to use another port)
4. Click on Patch NTR, then locate and open your ntr.bin file. The default path for BootNTR Selector is <Drive letter>:\3ds\BootNTRSelector\ntr_3_6.bin .If you’re using FTP or microSD management then you’ll have to copy this file to your PC first.
5. Snickerstream will ask you if you really want to patch your NTR binary, answer yes. If everything goes OK, it'll tell you that the patch has been applied succesfully.
6. Click apply, then close Snickerstream and put the microSD back to your n3DS. **That Snickerstream installation is now "linked" to the n3DS whose NTR bin you've just patched, from now on you'll only be able to connect to that specific n3DS with it!** 
7. (Only if you have used FTP or microSD management) Copy the patched file back to your microSD, overwriting the old one if necessary.
8. Open _both_ Snickerstream executables, launch NTR on both consoles and click connect on each Snickerstream window. Success!

In case you want to "unlink" that n3DS all you need to do is to either follow steps 1 to 5 while using port 8001 or deleting the <Drive letter>:\3ds\BootNTRSelector\ folder and then let BootNTR selector redownload the files again.
