README for Scuachu's MP3 Now Playing OBS Overlay.

Video Guide: https://www.youtube.com/watch?v=FQv-yiIqSPQ

WARNING: This app is designed to be used with hardware or software capable of writing to files. For example, an Elgato Stream Deck (with Text File Tools plugin by BarRaider). There is no built-in UI for selecting songs. An external input method is strongly advised.


Formats:

	- Input format: Playlist | FileName
	- Index format: Title | Author | FileName


Overview:

	This app is designed for Windows operating systems.
	Esc will close the app.
	This app is required to be fullscreen, so you need to alt+tab or windows key out of the application.
	Upon running this app, "now playing.txt", "pause.txt" and a few other files are created alongside this README.txt.
	If you lose these files, running the app again will create new ones.
	You will store your playlists in the StreamingAssets folder of this app (where this file is). You must also manually add MP3 files to each playlist folder before they can be played.
	All audio files must be MP3s with a bitrate of 128kbps or higher; otherwise, looping will not work well.
	Unity struggles with lower bitrates (such as 124kbps) and will likely think your MP3s are double their length.
	Each playlist must have an "index.txt" stored inside, sharing the same name as the playlist they are in.
	The onscreen text will move if the text is too long. The behaviour is as follows: Idle 5 seconds, move 5 seconds, Idle 5 seconds, move back 5 seconds.
	Sound control is your responsibility. I suggest using Windows' volume mixer to control audio levels.


Instructions:

	Setting Up Playlists:
		- Your playlists are folders that you create within StreamingAssets. You can name them whatever you want.
		- Within these playlist folders is where you will locally store your MP3 files.
		- Additionally, you need to make an index.txt file with the same name as the playlist folder. For example, If the playlist folder name is "Playlist", the index.txt needs to be named "Playlist.txt" (case sensitive).
		- To format your index.txt correctly, refer to the format stencil above or here (Title | Author | FileName).
		- The Title and Author will appear on the screen with Title being above Author.
		- The Title and Author can be whatever you make them; however, the FileName MUST match the name of the MP3 you wish to play (".mp3" not included). For example, if I have a file called "Song [345sfg57gh]", the format used would be "Title | Artist | Song [345sfg57gh]", without the quotations.
		- This app separates these entries with a " | " (Vertical Bar. Spaces included), so do not use " | " within your Title and Author fields. If the character is not native to your keyboard, here is the character by itself so you can copy and paste it.

		 | 


	Setting Up Inputs:
		- With the input method of your choosing, you need to write to the "now playing.txt" file located next to this README.txt file.
		- You will need to write what playlist you wish to play from and the FileName of the MP3 file.
		- Additionally, having your file name be "?" will play a random MP3 within the specified playlist (there is no randomly selected playlist feature).
		- To format your now playing.txt correctly, refer to the format stencil above or here (Playlist | FileName/?).
		- For example: if I wanted to play "Song [345sfg57gh]" from earlier, I would write "Playlist | Song [345sfg57gh]".
		- If I wanted a random song from my playlist, I would write "Playlist | ?".


	Looping & Pausing:
		- Looping is automatic and cannot be turned off. This app is primarily a music player, not a soundboard.
		- If a specific MP3 is input, only that MP3 will loop.
		- If a random MP3 is input, a random MP3 will be played at the end of each MP3 (repeats are possible).
		- To pause, write literally anything to the "pause.txt" file. If there is any amount of text in "pause.txt", the MP3 will pause (spaces included).
		- To unpause, remove ALL text from "pause.txt" (spaces included).


That's about it! If you have any issues or suggestions, please leave a comment on the GitHub page.


https://www.youtube.com/@scuachu
https://www.twitch.tv/scuachu


Thank you, Sylvonir & ChatGPT, for helping me make and debug this application.
