HzMod is a custom system module for your 3DS which means that it runs seamlessly and cleanly on your 3DS and it’s very easy to install.

HzMod support for Snickerstream is still considered experimental at this point but it should be reliable enough to stream most games with no issues. However, keep in mind that two key features are still missing, namely backwards compatibility with earlier HzMod/HorizonM versions and support for “TARGA” games (aka, a very small percentage of games that rely on a customized TARGA image format to be streamed).

In order to install it you're going to download the AIO pack from [HzMod's GBATemp thread.](https://gbatemp.net/threads/hzmod-old3ds-screen-streaming.469817/) **Make sure you follow this step if you've already used HzMod/HorizonM before as only the latest version is supported at the moment!**

_Please note that this tutorial gives for granted that you know how to do basic stuff with your system_, like installing CIAs for example. If you don't know how to do a particular thing you might want to consult [the guide.](https://3ds.hacks.guide/)

Are you ready? Great, let's get started then!

1. Install HorizonM.cia and HzLoad.cia on your console, and also HzLoad_HIMEM.cia if you're on an old 2/3DS.
2. Make sure your 3DS is connected to the internet, then launch HorizonM Loader. (or HorizonM HIMEM Loader if you're on an old 2/3DS and you want to stream high memory games)
3. You should be booted back to the Home menu and the notification LED should be cyan. Make sure Snickerstream is connected on the same network as your PC, then launch Snickerstream.
4. On Other Settings (the right side of the window) click on the list box near Streaming app and select HzMod instead of NTR.
5. Now it's time to customize the remoteplay settings! If you want to you could just enter your 3DS's IP address and either go with the default ones or use one of the built-in presets, but for the sake of clarity I'll describe what each option does here:

***

**IP** - You must write your 3DS' IP address here. You could set a static one in the console's Internet settings or find out your own via several different methods (for example opening FTPD and looking at the first line of text on the top screen or opening FBI then going to Remote install -> Receive URLs over the network and looking at the bottom screen)

**Image quality** - Setting this to a higher value will produce less compression artifacts but will make your framerate worse, and the opposite will do, well... the complete opposite. It's not recommended to set it any higher than 90 as compression will always occur (even at the maximum, aka 100!) while it's going to _absolutely kill_ your framerate, while setting it below 50 will produce noticeable artifacts. (Default: 70, but the recommended value is 42 as it'll give the best quality/framerate ratio)

**Cap CPU cycles** - If some games suffer from slowdowns while streaming, set this value to something high. A value of 256 however will make the system module wait until VSync, which is almost nothing on New 2/3DS. (Default: 0)

***

6. Once everything is in place, click Connect! You should see your 3DS' notification LED turn green, then the top screen should start to be streamed to your PC. Success!

7. (Optional) If a game tries to disable the Wi-Fi connection forcibly you enable Luma3DS’ debugger on a New 2/3DS (open the Rosalina menu, go on Debugger options and Enable debugger). There is sadly no workaround on an Old 3DS as of now.

8. (Optional) If your game gets slowdowns you might want to increase the Cap CPU cycles option (see step 5) or set a frame limit in the advanced menu.

If everything went fine then you're all good to go, you can start doing whatever you want with your stream, including going back to the connection window and tweaking some of the advanced settings to your pleasure, or maybe choosing another screen layout or interpolation mode. From now on all you have to do to stream your games is to open up HzMod like in step 2, wait for the cyan notification LED then repeat steps 5 and 6. Have fun streaming!

If something went wrong, you could try the Troubleshooting guide, FAQ or you might have better luck with NTR instead.