## Create A Desktop App

Sure, you could just send a zip to everyone and people would only have to open the index.html to play your game, but if you want to distribute your game as a desktop app, you'll be able to use [Electron](http://electron.atom.io/) for it since Monogatari already has the basics for it.

First, finish your game of, you'll use the same files for the desktop version so if it's ready for the web, then you're ready!

If you prefer it, you can follow the [Official Electron's Documentation](https://github.com/atom/electron/blob/master/docs/tutorial/application-distribution.md) instructions for this.

Next, download the latest Electron binaries from it's <a href="https://github.com/atom/electron/releases">GitHub Page</a> you'll need to download all the binaries for every system you'd like to build your game for as well as the arquitectures.
At the moment this was written the latest version is electron v0.29.1, so assuming we want to build our game for every OS, then I'll download this files:

1. electron-v0.29.1-darwin-x64.zip (Mac OS X)
2. electron-v0.29.1-linux-arm.zip (Linux ARM Arquitecture)
3. electron-v0.29.1-linux-ia32.zip (Linux 32 Bit Arquitecture)
4. electron-v0.29.1-linux-x64.zip (Linux 64 Bit Arquitecture)
5. electron-v0.29.1-win32-ia32.zip (Windows 32 Bit Arquitecture)
6. electron-v0.29.1-win32-x64.zip (Windows 64 Bit Arquitecture)

And yes, that's a lot of files, but everyone of those files is your future game!, when you download them uncompress them and you'll realize they're already built apps, you can open it, but now we have to put or game on it.
In order to do so, follow this instructions

### For OS X
Right Click the Electron.app and select "Show Package Contents" (If you're not on OS X you'll see the Electron.app as a simple directory so just open it)

Now create a directory named "app" in Electron.app/Contents/Resources/ and copy your VN files to it.
Open the package.json file that comes with Monogatari and write your VN's name and version, once you've done that, just save the file and close it.

With this done you'r game will now run as an app however we still need to custimize it.
You should change the icon (icns) file for your game's icon.

Next, you need to rename the CFBundleDisplayName, CFBundleIdentifier and CFBundleName fields in following files: Electron.app/Contents/Info.plist Electron.app/Contents/Frameworks/Electron Helper.app/Contents/Info.plist
And finally Change the name of the Electron.app to to any name you like.

That's it, now you can distribute your application for Mac OS X

### For Windows

Create a directory named "app" in resources/ and copy your VN files to it.

Open the package.json file that comes with Monogatari and write your VN's name and version, once you've done that, just save the file and close it.

Finally rename the electron.exe to any name you like.

That's it, now you can distribute your application for Windows, the same procedure applies to all the arquitectures.
Sadly you can't change the icon as easy as in Mac, however you can search for a tool to do it or if you dare, you could Rebuilding Electron from source to achive this.

### For Linux
Create a directory named "app" in resources/ and copy your VN files to it.

Open the package.json file that comes with Monogatari and write your VN's name and version, once you've done that, just save the file and close it.

Finally rename the electron executable to any name you like.

That's it, now you can distribute your application for Linux, the same procedure applies to all the arquitectures.

### Wrapping up...
Please check the [Official Electron's Documentation](https://github.com/atom/electron/blob/master/docs/tutorial/application-distribution.md) as well, I'm sure you'll find it helpful.
Also, you can also protect your app's resources and source code from the users, instructions to do so are found [here](https://github.com/atom/electron/blob/master/docs/tutorial/application-packaging.md).
