#include "music_player.h"
#include <iostream>
#include <stdexcept>

// Function to load a list of songs into the player
void loadSongs(MusicPlayer& player, const std::vector<std::string>& songs) {
    for (const auto& song : songs) {
        try {
            player.load(song);
            std::cout << "Loaded: " << song << std::endl;
        } catch (const std::exception& e) {
            std::cerr << "Error loading " << song << ": " << e.what() << std::endl;
        }
    }
}

// Function to handle playback
void playMusic(MusicPlayer& player) {
    try {
        player.play();
        std::cout << "Playback started." << std::endl;
    } catch (const std::exception& e) {
        std::cerr << "Error during playback: " << e.what() << std::endl;
    }
}

// Function to stop playback
void stopMusic(MusicPlayer& player) {
    try {
        player.stop();
        std::cout << "Playback stopped." << std::endl;
    } catch (const std::exception& e) {
        std::cerr << "Error stopping playback: " << e.what() << std::endl;
    }
}

int main() {
    // Create a MusicPlayer object
    MusicPlayer player;

    // List of songs to load
    std::vector<std::string> songs = {"song1.mp3", "song2.mp3"};

    // Load songs into the player
    loadSongs(player, songs);

    // Start playback
    playMusic(player);

    // Wait for user input to stop playback
    std::cout << "Press Enter to stop playback...";
    std::cin.get();

    // Stop playback
    stopMusic(player);

    return 0;
}
