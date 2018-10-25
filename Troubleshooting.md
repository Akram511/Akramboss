This section is dedicated to help you troubleshoot common issues with Snickerstream, NTR and HzMod. If you encounter any of these problems try out these solutions before asking questions on the thread or creating an issue!

And while we're here, please remind that the GitHub issue tracker should only be used to report bugs and suggest improvements. General help and other types of questions should instead be asked on Snickerstream's GBATemp thread!


***


**• I get a black screen,  a "Could not start remoteplay" or "Could not receive the stream from your console" error when using NTR.**

This usually happens if a firewall, antivirus or an external program is preventing Snickerstream from receiving the stream. Double check that your IP is correct, then whitelist Snickerstream in both your antivirus and firewall (optionally, if you run Snickerstream as admin it will try to allow itself through Windows Firewall). 

_For the love of all that is holy, do not disable either your firewall or antivirus!_ Not only you'd be putting yourself in unnecessary risk but Windows Firewall is sometimes known for reactivating itself for no reason. Instead, take the time to properly configure things.

If the issue still persists, try to connect using Snickerstream first, then switch to NTRViewer from the [NTR starter kit](https://github.com/44670/BootNTR/files/222950/NTR_3.4PREVIEW2_STARTER_KIT.zip) and see if the stream works. If it doesn't, it's not Snickerstream's fault and it's a problem on your end. If nothing seems to work, you can try using HzMod instead of NTR.

**• My custom settings don't get saved.**

If that happens then Snickerstream doesn’t have write permissions for the folder it’s currently in. You could either move Snickerstream to a path for which your account has write permissions (for example, a folder on your desktop) or take ownership of that folder. 

**• The stream's framerate is poor.**

This is generally caused either by poor Wi-Fi signal strenght or interference. If the first one's your problem try to either place your 3DS closer to your access point (remember, you could always use input redirection if the console is too far from you!) or to create an ad-hoc network closer to it, while if it's the second try to change your Wi-Fi channel. Alternatively, you can always drop the stream's quality a notch or increasing the priority value (remember to restart your 3DS afterwards if you're using NTR!)

**• The connection gets dropped after opening a certain game.**

If a game uses NFC connectivity it'll try to forcefully disable Wi-Fi. This can be circumvented using NTR by either returning to the Home menu and clicking Send NFC patch in Snickerstream or enabling Luma3DS' debugger (open Rosalina, go to Debugger options, Enable debugger). NFC patching is currently broken in HzMod but you can still enable Luma's debugger on a n3/2DS. There's currently no option to do that on old 3DS consoles.

**• Switching games or soft resetting causes the 3DS to softlock while using NTR.**

This is an issue caused by NTR and cannot be fixed. Use HzMod if you need either.

**• Weird colours appear when streaming Virtual Console titles with NTR.**

That's yet another issue caused by NTR. One workaround would be to use homebrew emulators instead and another would be to use HzMod instead (but keep in mind that a lot of VC games require TARGA support, which is currently not implemented in Snickerstream - more on that in the next point).

**• I get an error saying "Snickerstream currently does not support TARGA streams" while trying to stream a game with HzMod.**

Some games require a different format to stream their frames with HzMod. This format is not yet supported in Snickerstream but it will be in future versions. For now you'll either have to use NTR or the official HorizonScreen client instead!

**• DS/GBA games and VC titles cannot be streamed.**

They cannot be streamed because the 3DS unloads the entire OS while opening one of said games, including NTR and HzMod, then the respective console's firmware gets loaded instead and runs natively on the hardware. In other words, they cannot be streamed and this probably won't ever change either.


**• I get an error saying “There was an error while initializing Direct2D.”**
The Direct2D renderer will only work on Windows 7 and later. If you’re using Windows 7 then you must have the platform update installed, which is free and you can either install it from Windows Update or [separately from Microsoft’s website.](https://www.microsoft.com/en-us/download/details.aspx?id=36805) Keep in mind that it requires the Service Pack 1 to be already installed! If you’re on XP or Vista then you can still use the (deprecated) GDI+ renderer, even if you’ll be missing out on some features. If you’re on an earlier version of Windows (and I _really_ hope for you that you’re not) then you’re out of luck… _maybe it’s time for an upgrade?_