NTR is a true custom firmware which needs a bit more involvement when setting it up (but nothing out of this world, don't worry!). It's not a stand-alone CFW like Luma3DS however, it basically runs _alongside_ your CFW.

In order to make things easier we're going to use [BootNTR Selector](https://gbatemp.net/threads/release-bootntr-selector.432911/) instead of NTR's official one.

_Please note that this tutorial gives for granted that you know how to do basic stuff with your system_, like installing CIAs for example. If you don't know how to do a particular thing you might want to consult [the guide.](https://3ds.hacks.guide/)

Are you ready? Great, let's get started then!

1. Download one of BootNTR Selector's CIA (it doesn't matter which one, all that changes is the logo on the Home menu) and install it with FBI.
2. Make sure your 3DS is connected to the internet, then launch BootNTR Selector.
3. The homebrew should ask you to select which paths it should use, select "Use default" then "Save settings".
4. Lastly, the app should ask which NTR version you want to use. Select 3.6 _(the app will remember it from now on so you won't have to select it everytime!)_
5. The screen should flash blue and then you should be booted back to the Home menu. Make sure Snickerstream is connected on the same network as your PC, then launch Snickerstream.
6. Now it's time to customize the remoteplay settings! If you want to you could just enter your 3DS's IP address and either go with the default ones or use one of the built-in presets, but for the sake of clarity I'll describe what each option does here:

***

**IP** - You must write your 3DS' IP address here. You could set a static one in the console's Internet settings or find out your own via several different methods (for example opening FTPD and looking at the first line of text on the top screen or opening FBI then going to Remote install -> Receive URLs over the network and looking at the bottom screen)

**Screen priority** - The screen that gets prioritized will get a higher framerate. You can control the framerate factor with the next setting. (Default: Top screen)

**Priority factor** - The higher the value, the better the prioritized screen's framerate will be (and the worse the non-prioritized one will get!) A value of 1 will give both screens the same priority and a value of 0 will disable the non-prioritized screen completely. (Default: 5)

**Image quality** - Setting this to a higher value will produce less compression artifacts but will make your framerate worse, and the opposite will do, well... the complete opposite. It's not recommended to set it any higher than 90 as compression will always occur (even at the maximum, aka 100!) while it's going to _absolutely kill_ your framerate, while setting it below 50 will produce noticeable artifacts. (Default: 70)

**QoS Value** - Honestly, not much to say about this one. On supported routers it can give a nice framerate boost but most of the time it does nothing. Check [this Wikipedia article](https://en.wikipedia.org/wiki/Differentiated_services#Commonly_used_DSCP_values) to see commonly used values. A value of above 100 will disable this feature. (Default: 20)

***

7. Once everything is in place, click Connect! You should see your 3DS' top screen flashing briefly, then the screens should start to be streamed to your PC. Success!

8. (Optional) If a game tries to disable the Wi-Fi connection forcibly, you can either go back to the connection window (default hotkey: ENTER) and click on Send NFC patch or enable Luma3DS’ debugger (open the Rosalina menu, go on Debugger options and Enable debugger). 

If you want to stream multiple 3DS consoles to the same PC you will have to [follow this guide too.](https://github.com/RattletraPM/Snickerstream/wiki/Multiple-3DS-streaming-guide)

If everything went fine then you're all good to go, you can start doing whatever you want with your stream, including going back to the connection window and tweaking some of the advanced settings to your pleasure, or maybe choosing another screen layout or interpolation mode. From now on all you have to do to stream your games is to open up NTR via BootNTR Selector and then repeat steps from 5 to 7. Have fun streaming!

If something went wrong, you could try the Troubleshooting guide, FAQ or you might have better luck with HzMod instead.