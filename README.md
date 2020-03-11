# Summoners War Hub Receiver

### DISCLAIMER:
#### Technically this software is a bot. It creates requests that are sent to the Summoners War game servers from your IP which do not come originally from a version of the game. The use is violating the Terms of Service of COM2US and your account CAN get banned for using this software. If you decide to use this, do so at your own risk.

## Description
Upon logging in to the game Summoners War, the game requests a data block called 'HubUserLogin'. Some external tools like [SWARFARM](https://swarfarm.com/) or [SWOP](https://tool.swop.one/) can interpret this data block for convenience. This way the user does not have to put in all of their monsters and runes manually. There are ways to receive this data block but most of them are quite fiddly or require deeper technological knowledge.
This software is a simple command line tool which simulates all the requests a Bluestacks emulator would do during login to your account. This way the HubUserLogin data block can be downloaded from the game servers without installing any emulator or other software.

One additional thing to notice: this tool works as of the current state of the game. With every game patch the login process may change, thus braking this tool. Some values can be configured in the 'config.json' file, however most changes will need an updated version of this tool. So before opening a bug report, check if there is a newer version of sw_hub_receiver or already another pending bug report concerning a game update.

### Download
The newest version of this command line tool will always be available at the [releases page](https://github.com/Artenuvielle/sw_hub_receiver/releases). Go there and download the executable for your operating system. This tool is currently compiled for Windows, Linux and MacOS. However tests have only happened under windows yet.
There is also an optional 'config.json' file available for download. If you place it alongside the downloaded executable in the same folder, you can manipulate some values which are sent to the server. E.g. by default the tool tells the server it is a German game client - you can change that by changing some values in this file.

### Usage
After downloading the executable for your operating system, run it and a command line should open. After the tool established a connection to the game servers the tool will ask to which one (global, asia, eu, ...) you want to connect. After some additional requests to the game servers, including making sure that there is no maintenance going on, you are asked to enter your HIVE ID and its password. These credentials won't be sent anywhere except to the game server. The password also won't be sent in a clear form but rather only a MD5 hash of it.
After logging in to your account and receiving the HubUserLogin data block from the server the connection will be terminated immediately. No change will be made to your account at all. The data block will get saved as 'HubUserLogin.json' in the directory where the executable is located.

### Security
The tool tries to trick the game servers to be a Bluestacks emulator running the current game version, but there might be ways to detect that it is not a real game client connecting. E.g. because right after logging in, nothing else gets done.
COM2US might decide to punish the use of this tool and could find the people using it. There is no real measurement taken against this.
Theoretically this tool will not give you any information or advantage over other players not using such tools.

### Source code
I decided to not publish the code for this tool, since it can be easily used to develop real bots, that play the game automatically for you. I do _not_ endorse the development of such bots at all. I don't want to help anyone to hack the game in any way and decided to not publish any information about the security layer of the game.
