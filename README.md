# Music Player API
A simple yet powerful Music Player API written in C++. This project allows you to manage playlists, play songs, shuffle playlists, and save/load playlists to/from files. It is designed to be easy to use and extend.

Features
Playlist Management:

Create and delete playlists.

Add and remove songs from playlists.

Switch between playlists.

Playback Controls:

Play all songs in a playlist.

Shuffle songs in a playlist.

Song Metadata:

Store and display song details (title, artist, album, length).

File I/O:

Save playlists to a file.

Load playlists from a file.

User-Friendly Interface:

Interactive menu for easy navigation.

Getting Started
Prerequisites
A C++ compiler (e.g., g++).

Basic knowledge of C++ and terminal commands.

Installation
Clone the repository:

bash
Copy
git clone https://github.com/aditya7527/Music-Player-API.git
cd Music-Player-API
Compile the code:

bash
Copy
g++ main.cpp -o music_player
Run the program:

On macOS/Linux:

bash
Copy
./music_player
On Windows:

bash
Copy
music_player.exe
# Usage
Main Menu
When you run the program, you will see the following menu:

Copy
Music Player Menu:
1. Create Playlist
2. Delete Playlist
3. Switch Playlist
4. Add Song to Playlist
5. Remove Song from Playlist
6. Display Playlists
7. Play Current Playlist
8. Shuffle Current Playlist
9. Save Playlist to File
10. Load Playlist from File
11. Exit
Enter your choice:
Example Workflow
Create a Playlist:

Choose option 1 and enter a name for the playlist.

Add Songs to a Playlist:

Choose option 4, select a playlist, and enter song details (title, artist, album, length).

Play a Playlist:

Choose option 7 to play all songs in the current playlist.

Shuffle a Playlist:

Choose option 8 to shuffle the songs in the current playlist.

Save a Playlist to a File:

Choose option 9, select a playlist, and enter a filename to save the playlist.

Load a Playlist from a File:

Choose option 10, enter a filename, and provide a name for the new playlist.

# File Format for Playlists
Playlists are saved as .txt files in the following format:

Copy
Title,Artist,Album,Length
Title,Artist,Album,Length
...
Example:

Copy
Bohemian Rhapsody,Queen,A Night at the Opera,354
Stairway to Heaven,Led Zeppelin,Led Zeppelin IV,482
Hotel California,Eagles,Hotel California,391
Contributing
Contributions are welcome! If you'd like to contribute, please follow these steps:

Fork the repository.

Create a new branch for your feature or bugfix:

bash
Copy
git checkout -b feature/your-feature-name
Commit your changes:

bash
Copy
git commit -m "Add your message here"
Push to the branch:

bash
Copy
git push origin feature/your-feature-name
Open a pull request and describe your changes.
