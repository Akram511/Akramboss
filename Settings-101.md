Snickerstream stores its settings in an INI file called "settings.ini" located in the same folder as the executable/Au3 script. The INI contains a single section called [Snickerstream] that stores all keys and their assigned values.

Snickerstream’s settings can be divided into three groups: standard, advanced and interface settings. The Advanced section will also be very helpful if you wish to play around with the advanced menu.

# Standard settings
This group consists of all the core settings that the client needs to function properly. All of them can be changed from the connection window and most users only need to set these in order to have a great streaming setup.

**IpAddr**: The (N)3DS’ IP. It must be a valid IPv4 address, separated by dots.

**PriorityMode**: Boolean. Setting it to 0 will give priority to the top screen when streaming, otherwise setting it to 1 will give priority to the bottom screen. The default value is 0 (aka top screen).

**PriorityFactor**: Sets how many of the prioritized screen’s frames will have to be streamed before one of the non-prioritized screen gets sent. Setting it to 1 will give the same priority to both screens, while setting it to 0 will completely disable the non-prioritized screen. The default value is 5.

**ImageQuality**: Sets the frames’ quality value, ranging from 1 (worst) to 100 (best). NTR sends its frames as a stream of JPEG images which means that the frames will always get compressed, even if you set this variable to 100. Therefore _it is not recommended to set ImageQuality to any value above 95 as the stream will consume a lot more bandwidth while compression artifacts may still be visible!_ The default value is 70.

**QoS**: Sets the UDP packets’ Quality of Service value. Refer to [this table](https://en.wikipedia.org/wiki/Differentiated_services#Commonly_used_DSCP_values) to see the commonly used DSCP values (see the decimal value column). The default value is 20. When using HzMod this variable is used for the Cap CPU Cycles setting and its default value is 0.

**Interpolation**: Sets the interpolation mode used by the rendering backend. Direct2D and GDI+ support different interpolation modes so this setting will have to be changed if you switch between the two (Snickerstream’s GUI will do this automatically). Direct2D has six interpolation modes: Nearest neighbor (0), Linear (1), Cubic (2), Bicubic (3), Multi Sample Linear (4), Anisotropic (5) and High Quality Bicubic (6), while GDI+ has Default (0), Low quality (1), High quality (2), Bilinear (3), Bicubic (4), Nearest-neighbor (5), Bilinear HQ (6) and Bicubic (7). The default value is 0.

**Layoutmode**: Sets which screen layout will be used when streaming. The accepted values are 0 (Vertical), 1 (Vertical, inverted), 2 (Horizontal), 3 (Horizontal, inverted), 4 (Top only), 5 (Bottom only), and 6 (Fullscreen, top only). The default value is 0.

**UseNTR**: Boolean. Specifies whether to use NTR (True) or HzMod (False) as the streaming homebrew app. Default: True.

# Advanced settings
These settings can be changed by going to the Advanced Menu and don’t need to be modified in most cases. Some of these can result in a bad or laggy streaming setup if misconfigured so it’s recommended to not touch them unless you know what you’re doing. _Proceed at your own risk!_

**Loglevel**: Sets the current log level (and thus also specifies whether to create a log file or not). There are three log levels: 1 (only logs basic information), 2 (logs some more in-depth stuff, such as current settings and invalid packet errors) and 3 (logs everything). _Setting the log level to 3 will produce very long log files and, as such, should only be used for debugging purposes!_ Setting this variable to 0 or lower will make Snickerstream not produce a log file, while setting it to anything higher than 3 will have the same effect as log level 3. This variable is set to 0 by default.

**LogConsole**: Specifies whether to output the log to a file (0), a console window (1) or both (2). Default: 0.

**ListenPort**: Sets what UDP port should Snickerstream listen to when streaming using NTR. Default: 8001.

**UseD2D**: Boolean. If set to True then Snickerstream will use Direct2D as its rendering backend, while if it’s set to False then GDI+ will be used instead. The GDI+ renderer has been deprecated and should not be used unless you really know what you're doing.

**PCIpAddr**: Binds Snickerstream to one of the IP addresses assigned to the computer. Useful in some situations (such as if UDP port 8001 is open on your router but you only want to listen to local connections for security reasons) _but will make you unable to stream if set incorrectly._ This variable is unset by default and Snickerstream will listen on all available network interfaces.

**WaitRemoteplayInit**: This variable specifies how many milliseconds Snickerstream will wait for a frame to be sent before sending the remoteplay packet. If a frame is received during that time span it means that remoteplay has already been started, so there will be no need to send the packet again and the client can receive frames right away. Setting this variable to a value too high will make Snickerstream take too much to connect to the (N)3DS for the first time, while setting it too low might make it take a bit longer for any subsequent connection. Setting it to 0 or a negative value will always make Snickerstream send the remoteplay packet. The default value is 1000 (1 second).

**Framelimit**: If set, enables Snickerstream’s experimental frame limiter feature which locks the stream to the specified framerate. Useful if you prefer a smooth stream over having a high but unstable framerate, howerer setting this value too low will make your stream laggy. This value is unset by default (the recommended value is 30).

**ReturnAfterMsec**: Specifies how many milliseconds will have to pass without receiving a frame before Snickerstream returns to the connection window. Useful if you reboot your (N)3DS frequently. Setting it to 0 or a negative value will disable this feature. _Setting this variable to a value too small might make Snickerstream disconnect too frequently, so it should be used with caution_. Snickerstream waits 8000 milliseconds (8 seconds) by default but this variable is not set when the INI is first created.

**CenterScreens**: If set to 1 it will center the screens inside the streaming window, otherwise the screens will be aligned to the left side of the window. Default: 1.

**Hotkeys**: A series of 10 key codes separated by a vertical line that define which action should be run when a specific button is pressed. The first one is assigned to the SCALE UP action, then going on there is SCALE DOWN, PERV. INTERP., NEXT INTERP., RETURN WINDOW, SCREENSHOT, SCREEN POPUP, CLOSE, HZM QUALITY-, HZM QUALITY+. You can find a list of compatible keycodes [here](https://www.autoitscript.com/autoit3/docs/libfunctions/_IsPressed.htm) but keep in mind that you can always bind them from the advanced menu if you don't want to bother with doing that manually by editing the INI. Also note that if the string doesn't contain exactly 10 key codes it will be automatically reset to the default ones!  Default: 26|28|25|27|0D|53|20|1B|51|45

**EnableHzMNFCPatch**: _This option is here only for forwards compatibility._ Boolean. As of writing this article NFC patching in HzMod is broken and it will result in a softlock when games try to enable NFC. This is a bug within HzMod itself and will require an update to that homebrew app in order for it to be fixed. Althrough it doesn't cause any permanent damage to the console it's suggested to leave this option disabled until an update is released that fixes this issue. Default: False.

**TopScalingFactor** and **BottomScalingFactor**: Self-explainatory, if set to anything other than 0 it will scale the respective screen by the specified factor (must be higher than 0.3). Default for both: 0.

**CustomWidth** and **CustomHeight**: Workarounds for high DPI monitors whose settings are not automatically detected by Snickerstream. You can set the streamin window's initial size (in pixels) by adding these variables to the INI. Keep in mind that CustomWidth must be higher than 150, CustomHeight must be higher than 200 and that **the window's content WILL NOT BE SCALED when setting a custom size using these variables!** Default for both: 0.

**CustomWidth2** and **CustomHeight2**: Same as above but they're used for the bottom screen window when using the separate windows layout.

# Interface settings
These settings control various things related to the GUI such as whether or not a message box has been shown or which function to call when a button gets pressed. As such, _changing these will give you no performance benefit whatsoever_ and usually should not be touched. They are generally unset by default and only get set when a specific action occurs, such as telling Snickerstream to not warn the user if the remoteplay settings aren’t optimal for its screen layout.

**NFCLastAnswer**: Stores the value returned by the message box asking which version of the NFC patch must be sent. The accepted values are 6 (>=11.4) and 7 (<=11.3). _Bug: Setting this to anything else will make the Send NFC button do absolutely nothing!_ This variable only gets set when the Send NFC button gets pressed and is unset by default.

**NoDisplayIPWarn**: By default, Snickerstream warns the user if PCIpAddr is set to a specific value in the INI file (mostly because in the PoC version it was set to the PC’s first network adapter’s IP which could cause problems if you have multiple ones). If set, this warning will not appear.

**DontCheckSettings**: By default, Snickerstream warns the user if the remoteplay settings he chose aren’t good for the screen layout he decided to use – such as giving priority to the bottom screen and setting the screen layout to top only. If set, Snickerstream will not check the settings when connecting to the (N)3DS and the warning will not appear.

**GDIPWarn**: When switching from Direct2D to GDI+ Snickerstream will warn the user that this rendering backend is deprecated. If set, this warning will not appear.

**AdvWarning**: When the user first enters the Advanced menu a warning will appear basically saying "here be dragons". If set, this warning will not appear.

**DontCheckForUpdates**: If set to a value different than 0 the update warner feature will be disabled completely. This feature can also be disabled by clicking on "Cancel" when the update warner asks the user if he wants to go to the GitHub releases page.