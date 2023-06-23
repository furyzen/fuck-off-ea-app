# "Fuck off EA App"

A small project to patch the EA Origin app and keep it running, avoiding the nags to upgrade to the new EA App.

If you start up Origin app and see a prompt telling you to install EA App, you've come to the right place.

What works (as of 2023-06-24):
* ✔️ login
* ✔️ main page
* ✔️ game startup
* ✔️ game downloads
* ✔️ friends section

## Download

### Installer

**[Download](https://github.com/p0358/Fuck_off_EA_App/releases)** the installer from Releases section and run it!

![installer screenshot](https://github.com/p0358/Fuck_off_EA_App/assets/5182588/b122e05c-79b3-4849-ba56-c8a79552b8ec)

### Manually

1. Go into [Releases section](https://github.com/p0358/Fuck_off_EA_App/releases) and grab the latest `version.dll` file
2. Drop it into your Origin installation folder, by default `C:\Program Files (x86)\Origin`
3. Restart Origin

Note: you can also compile the DLL manually, instructions are at the bottom of this file.

## Why

We're not ones wanting to step on EA's toes, however their new app just does not work properly for many users. The issues they experience are countless, ranging from small annoyances to outright being unable to use the EA App or launch the games at all. This project exists to let people keep using Origin for as long as it's possible, at least until EA App is significantly improved, as currently Origin is the superior solution...

Remember to leave a star and follow if it helped you ;)

## FAQ

### How do I re-install Origin if I already deleted it?

Use this link: https://download.dm.origin.com/origin/live/OriginSetup.exe

### Do I need a specific version of Origin?

No, it should work fine with both the latest `10.5.122.52971` and with the older `10.5.119.52718` or earlier (if you used the downgrade method before and disabled updates).

### What about `local.xml`?

You don't need to either add or remove anything from that file anymore when using this project, conveniently.

### How does it work?

Our custom DLL (named `version.dll`) is loaded by Origin during its startup, after you insert it under its installation directory. It conducts function hooks and patches that prevent the upgrade notice from appearing. You can study the code for more details.

### Is it safe?

Yeah, the thing is open-sourced, and the actual DLL and installer in Releases section is built by GitHub Actions CI. You can always compile it yourself too if so you wish...

### What if EA breaks something again? Will this keep working forever?

Given they already broke the older workarounds before a few times, probably not forever. In any case, follow this repository for updates (*star the project ;)*) -- if the workaround stops working, I will probably try to update it to work again in the future -- contributions are also welcome.

### How do I compile it myself?

1. Clone the repository with git
2. Run `generate.bat`
3. Open the .sln file from `build` folder in Visual Studio
4. Compile the solution

## Third-party libraries used

* [minhook](https://github.com/TFORevive/minhook) (fork)
* [silver-bun](https://github.com/IcePixelx/silver-bun)
