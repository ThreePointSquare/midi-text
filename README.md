Scripts used to convert midi files to something that text-based neural networks can understand, and vice versa.

### How to use
Install [python-midi](https://github.com/vishnubob/python-midi), then flatten midi files with `demidi.py`
```
python3 demidi.py --mididir "/path/to/your/midis" --outdir "/path/to/output"
```

Run `remidi.py` to create a midi file that uses the same syntax
```
python3 remidi.py --datafile "/path/to/datafile.txt" --outfile "/path/to/outfile.mid"
```

### Syntax
Let's say you have a `NoteOnEvent` on Track 1 that looks like this.
```
NoteOnEvent(tick=8, channel=0, data=[66, 83])
```
It will be converted to this in text format
```
1NoteOnEvent8t0c66d83d
```

Using `--include-resolution` will append the [resolution](https://en.wikipedia.org/wiki/Pulses_per_quarter_note) to the beginning of the file. It is optional because most midi files seem to be at 96.

### Samples

[Here are some samples](https://soundcloud.com/user-122134918/sets/ai-generated-music) that were generated by a [textgenrnn](https://github.com/minimaxir/textgenrnn) neural net. It was trained with Undertale/Deltarune music at 20 epochs/4 layers/word-level and is bidirectional.
