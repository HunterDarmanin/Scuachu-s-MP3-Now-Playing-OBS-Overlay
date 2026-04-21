README for Scuachu's MP3 Now Playing OBS Overlay.

WARNING: This app is designed for Windows operating systems only.

Video Guide:
[![Video Guide](https://img.youtube.com/vi/FQv-yiIqSPQ/maxresdefault.jpg)](https://youtu.be/FQv-yiIqSPQ)

1.2 Video Guide:
[![Video Guide](https://img.youtube.com/vi/ZaNPiL3PfnQ/maxresdefault.jpg)](https://youtu.be/ZaNPiL3PfnQ)


Formats:

	- Input format: Playlist | FileName
	- Index format: Title | Author | FileName
	- Index format (with dB adjustment): Title | Author | FileName | dBValue


Overview:

	Esc or the on-screen close button will close the app.
	This app is required to be fullscreen, but there is a minimise button available.
	Upon running this app, "now playing.txt", "pause.txt" and a few other files are created alongside this README.txt.
	If you lose these files, running the app again will create new ones.
	You will store your playlists in the StreamingAssets folder of this app.
	All audio files must be MP3s with a bitrate of 128kbps or higher; otherwise, looping will not work well.
	Unity struggles with lower bitrates (such as 124kbps) and will likely think your MP3s are double their length.
	Each playlist must have an index file stored inside it, sharing the same name as the playlist folder.
	The onscreen text will scroll if it is too long. The behaviour is as follows: Idle 5 seconds, move 5 seconds, Idle 5 seconds, move back 5 seconds.
	There is a config file where currently you can only set the target monitor.
	You can control the app's volume using the Digital Controller, or manually via Windows' volume mixer.


Digital Controller:

	The Digital Controller is a built-in popout window for controlling the app without writing to files manually. Open it via the on-screen controller button in the bottom right.

	It contains:
		- Playlist and MP3 dropdowns. Selecting "?" for either will play a random pick.
		- A Play button to queue the selected song.
		- A Pause/Unpause button.
		- A Refresh button to rescan your playlists and MP3s if you have made changes.
		- An Always On Top toggle.
		- A Volume slider and input box (0-100). This controls the app's volume in Windows' audio mixer directly.
		- A dB Adjustment slider and input box. This adjusts the volume of the currently playing song relative to others.

	The dB adjustment is saved automatically to the song's index entry when the next song loads.
	This means each song can have its own saved volume offset, which will be restored the next time that song plays.
	You will see a 4th field appear in your index files in the format "+6.0dB" or "-3.5dB". This is normal.


MP3 Manager:

	The MP3 Manager is a built-in popout window for managing your library.
	Open it via the on-screen folder button in the bottom right. It has four tabs:

		Add:
			- Browse for an MP3 file or drag and drop one into the window.
			- Fill in the Title and Author fields.
			- Select an existing playlist or make a new one with [ + NEW PLAYLIST ].
			- Choose to Copy or Move the selected MP3 into the playlist folder.

		Remove:
			- Search and filter your songs by Title, Author, Filename, or Playlist.
			- Remove an MP3 or only remove from the index. All folders and files removed this way are sent to the Recycle Bin for retrieval.
			- Check "Delete Playlist instead" to delete an entire playlist folder.

		Move:
			- Move a song from one playlist to another.
			- This updates both the index files and moves the MP3 file on disk.

		Verify Integrity:
			- Scans your playlists for missing index entries, missing titles, missing authors, incorrect file names and empty playlists.

	The "Open Playlists Folder" button at the bottom opens your StreamingAssets folder in Explorer.
	The "Open Crash Logs" button opens the Crash Logs folder.


Manual Instructions:
(You can manage everything through the MP3 Manager, but manual setup is still supported.)

	Setting Up Playlists:
		- Your playlists are folders that you create within StreamingAssets. You can name them whatever you want.
		- Within these playlist folders is where you will locally store your MP3 files.
		- Additionally, you need to make an index file with the same name as the playlist folder. For example, if the playlist folder is named "Playlist", the index file must be named "Playlist.txt" (case sensitive).
		- To format your index file correctly, refer to the format stencil above, or here (Title | Author | FileName).
		- The Title and Author will appear on screen, with Title above Author.
		- The Title and Author can be whatever you like; however, the FileName MUST match the name of the MP3you wish to play (".mp3" not included). For example, if the file is called "Song [345sfg57gh].mp3", the index entry would be "Title | Artist | Song [345sfg57gh]", without the quotations.
		- This app separates fields with " | " (vertical bar with spaces), so do not use " | " in your Title or Author. If the character is not on your keyboard, here it is to copy and paste:

		 | 


	Setting Up Inputs:
		- With the input method of your choosing, write to the "now playing.txt" file located within StreamingAssets.
		- Write the playlist name and the FileName of the MP3, separated by " | ".
		- Using "?" as the FileName will play a random MP3 from that playlist.
		- Using "?" as both the Playlist and FileName will play a random MP3 from a random playlist.
		- Example: "Playlist | Song [345sfg57gh]" or "Playlist | ?".


	Looping & Pausing:
		- Looping is automatic and cannot be turned off.
		- If a specific MP3 is queued, only that MP3 will loop.
		- If a random MP3 is queued, a new random MP3 will be selected at the end of each song.
		- To pause, write any text to "pause.txt". Any amount of text will pause the app (spaces included).
		- To unpause, remove ALL text from "pause.txt" (spaces included).


Crash Logs:

	If the app closes unexpectedly, a crash log will be saved automatically to the "Crash Logs" folder next to the app's .exe.
	These are named by date and time, e.g. "crash_2025-06-01_14-32-00.log".
	You can open this folder from the MP3 Manager window.
	A crashed can be forced by exiting out of the app by not clicking the quit button. Actions such as Alt F4, Task Manager, etc. These will be marked in the crash log as forced.


Brush Rebrushed:

	Not all characters are supported by Brush Rebrush. Unsupported characters will attempted to be replaced by Unity's standard font, but characters that are unsupported by that will be replaced by rectangles.
	Brush Rebrushed supported characters are:
		Uppercase letters (A–Z): A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
		Lowercase letters (a–z): a b c d e f g h i j k l m n o p q r s t u v w x y z
		Numbers (0–9): 0 1 2 3 4 5 6 7 8 9
		Punctuation & symbols: ! " # $ % & ' ( ) * + , - . / : ; < = > ? @ [ \ ] ^ _ ` { | } ~
		Accented / extended Latin characters: À Á Â Ã Ä Å Æ Ç È É Ê Ë Ì Í Î Ï Ð Ñ Ò Ó Ô Õ Ö × Ø Ù Ú Û Ü Ý Þ ß à á â ã ä å æ ç è é ê ë ì í î ï ð ñ ò ó ô õ ö ÷ ø ù ú û ü ý þ ÿ


That's about it! If you have any issues or suggestions, please leave a comment on the GitHub or Itch.io page.


https://www.youtube.com/@scuachu
https://www.twitch.tv/scuachu


Thank you, Sylvonir (my friend), & Claude.AI for helping me make and debug this app.
