# bindbc-soloud
BindBC binding to [SoLoud sound engine](https://github.com/jarikomppa/soloud). Comes with a generator script in Python and a `soloud.d` wrapper module.

[![DUB Package](https://img.shields.io/dub/v/bindbc-soloud.svg)](https://code.dlang.org/packages/bindbc-soloud)
[![DUB Downloads](https://img.shields.io/dub/dm/bindbc-soloud.svg)](https://code.dlang.org/packages/bindbc-soloud)

## Usage example

```d
import soloud;

void main()
{
    loadSoloud();
    
    Soloud soloud = Soloud.create();
    soloud.init();
    
    WavStream music = WavStream.create();
    music.load("music.mp3");
    int voice = soloud.play(music);
    
    while (soloud.getActiveVoiceCount() > 0)
    {
        // do nothing while music is playing...
    }
    
    music.free();
    soloud.deinit();
}
```
