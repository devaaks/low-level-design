# Dependency Inversion Principle 

This principle encourages high-level modules to depend on abstractions (interfaces or abstract classes) rather than concrete implementations. It also suggests that low-level modules should not depend on high-level modules, but both should depend on abstractions.

### Example 
Suppose you have a music player application. Instead of having the high-level module directly depend on specific audio formats (e.g., MP3, WAV), you would define an abstraction (interface) for audio playback. The high-level module would depend on this abstraction, and the low-level audio format classes would implement it.

```java
// Before DIP
class MusicPlayer {
    void playMP3() { /* ... */ }
}

class AudioApp {
    private MusicPlayer musicPlayer = new MusicPlayer();

    void playAudio() {
        musicPlayer.playMP3();
    }
}

// After DIP
interface AudioPlayer {
    void play();
}

class MP3Player implements AudioPlayer {
    @Override
    public void play() { /* ... */ }
}

class AudioApp {
    private AudioPlayer audioPlayer;

    AudioApp(AudioPlayer audioPlayer) {
        this.audioPlayer = audioPlayer;
    }

    void playAudio() {
        audioPlayer.play();
    }
}
```
### DIP Implementation
<img width="429" alt="Screenshot 2024-03-04 at 23 59 04" src="https://github.com/devaaks/low-level-design/assets/16061289/d7d6470e-c6d6-4cf3-8ef4-0759219b83ef">


