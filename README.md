# Music Player API

This repository contains a simple music player API implemented in C++. It allows developers to create applications that can play audio files, manage playlists, and control playback functionalities.

## Features

- Play audio files in various formats (e.g., MP3, WAV, FLAC).
- Pause, resume, stop, and seek playback.
- Create and manage playlists.
- Retrieve metadata information of audio files.
- Simple and easy-to-use interface.

## Installation

To use this API in your C++ project, follow these steps:

1. Clone this repository to your local machine:

git clone https://github.com/yourusername/music-player-api.git

c
Copy code

2. Include the necessary files in your project and link them accordingly.
3. Build your project with the provided source files.

## Usage

Here's a simple example of how to use the music player API:

```cpp
#include <iostream>
#include <string>
#include <vector>
#include <limits> // For input validation

class Song {
public:
    Song(std::string title, std::string artist, std::string album, int length)
        : title_(title), artist_(artist), album_(album), length_(length) {}

    std::string getTitle() const {
        return title_;
    }

    std::string getArtist() const {
        return artist_;
    }

    std::string getAlbum() const {
        return album_;
    }

    int getLength() const {
        return length_;
    }

    void display() const {
        std::cout << "Title: " << title_ << ", Artist: " << artist_
                  << ", Album: " << album_ << ", Length: " << length_ << " seconds" << std::endl;
    }

private:
    std::string title_;
    std::string artist_;
    std::string album_;
    int length_;
};

class MusicPlayer {
public:
    void addSong(const Song& song) {
        playlist_.push_back(song);
        std::cout << "Added song: " << song.getTitle() << std::endl;
    }

    void removeSong(int index) {
        if (index >= 0 && index < playlist_.size()) {
            std::cout << "Removed song: " << playlist_[index].getTitle() << std::endl;
            playlist_.erase(playlist_.begin() + index);
        } else {
            std::cerr << "Invalid song index." << std::endl;
        }
    }

    void play() const {
        if (playlist_.empty()) {
            std::cerr << "Playlist is empty. Add songs to play." << std::endl;
            return;
        }
        for (const auto& song : playlist_) {
            std::cout << "Playing: " << song.getTitle() << " - " << song.getArtist() << std::endl;
        }
    }

    void playSong(int index) const {
        if (index >= 0 && index < playlist_.size()) {
            std::cout << "Now playing: ";
            playlist_[index].display();
        } else {
            std::cerr << "Invalid song index." << std::endl;
        }
    }

    void displayPlaylist() const {
        if (playlist_.empty()) {
            std::cout << "Playlist is empty." << std::endl;
            return;
        }
        std::cout << "Current Playlist:" << std::endl;
        for (size_t i = 0; i < playlist_.size(); ++i) {
            std::cout << i + 1 << ". ";
            playlist_[i].display();
        }
    }

private:
    std::vector<Song> playlist_;
};

int main() {
    MusicPlayer player;
    int choice;
    while (true) {
        std::cout << "\nMusic Player Menu:" << std::endl;
        std::cout << "1. Add Song" << std::endl;
        std::cout << "2. Remove Song" << std::endl;
        std::cout << "3. Play Playlist" << std::endl;
        std::cout << "4. Play Specific Song" << std::endl;
        std::cout << "5. Display Playlist" << std::endl;
        std::cout << "6. Exit" << std::endl;
        std::cout << "Enter your choice: ";
        std::cin >> choice;

        // Clear input buffer to handle invalid input
        std::cin.clear();
        std::cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');

        switch (choice) {
            case 1: {
                std::string title, artist, album;
                int length;
                std::cout << "Enter song title: ";
                std::getline(std::cin, title);
                std::cout << "Enter artist: ";
                std::getline(std::cin, artist);
                std::cout << "Enter album: ";
                std::getline(std::cin, album);
                std::cout << "Enter song length (in seconds): ";
                std::cin >> length;
                player.addSong(Song(title, artist, album, length));
                break;
            }
            case 2: {
                int index;
                std::cout << "Enter the index of the song to remove: ";
                std::cin >> index;
                player.removeSong(index - 1); // Adjust for 0-based index
                break;
            }
            case 3:
                player.play();
                break;
            case 4: {
                int index;
                std::cout << "Enter the index of the song to play: ";
                std::cin >> index;
                player.playSong(index - 1); // Adjust for 0-based index
                break;
            }
            case 5:
                player.displayPlaylist();
                break;
            case 6:
                std::cout << "Exiting the music player. Goodbye!" << std::endl;
                return 0;
            default:
                std::cerr << "Invalid choice. Please try again." << std::endl;
                break;
        }
    }

    return 0;
}
Documentation
For detailed documentation on how to use each function and class provided by the API, refer to the music_player.h file.
Contributing
Contributions are welcome! If you have any suggestions, bug fixes, or new features to add, please feel free to open an issue or submit a pull request.
