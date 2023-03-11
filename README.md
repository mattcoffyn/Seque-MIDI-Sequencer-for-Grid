# Seque

Seque is a polyphonic, 8-step sequencer profile for the Grid EN16 MIDI controller from Intech Studio. Uses multiple counters / timers triggered by a global timer in the system events to send up to 8 MIDI notes at independent intervals. WIP but contributions / forks are welcome!

For more info on Intech Studio

## Installation

Just drop the included json file in your user folder (Documents/grid-userdata/profiles/user) and load it onto your EN16 module in the Grid Editor.

## Usage

### Encoders 0 — 7 (Top Two Rows): Individual Step Controllers

- Rotate Left / Right
  - Increase / Decrease note repetition frequency. This is done by adjusting the counter between `midi_send` commands.
- Button
  - Toggle on / off `midi_send`. Does not stop the counter.
- LED
  - Red == 'off'.
  - Blue (encoders 0 — 3) or purple (encoders 4 — 7) == 'on'.
  - Flash indicates start of counter (and note send if on).

### Encoders 8 — 11 (Third Row): Individual Pitch Adjustments

- Rotate Left / Right
  - Decrease / Increase pitch of MIDI note for encoders 0 — 3 respectively.
- Push & Rotate Left / Right
  - Decrease / Increase pitch of MIDI note for encoders 4 — 7 respectively.
  - Pitch changes are incremented by 1 (one semitone)
- LED
  - Blue == Controlling pitch of encoder two rows above.
  - Purple == Controlling pitch of encoder one row above.

### Encoder 12 (Bottom Left): Scale / Mode Selector

- Rotate Left / Right
  - Move through Mode selector. Current Options are:
    1. Ionian (I) 🔴
    2. Dorian (ii) 🟠
    3. Phrygian (iii) 🟡
    4. Lydian (IV) 🟢
    5. Mixolydian (V) 🔵
    6. Aeolian (iv) 🟣
    7. Locrian (viiø) 🟣
- Button
  - Apply selected scale to all note steps. Applies the scale from root (encoder 0) to octave (encoder 7).
  - Is based on current Root Note (Encoder 13).
- LED
  - Displays mode options (see colours above).

### Encoder 13: Root Note Selector

- Rotate Left / Right
  - Select root note of scale.
  - Default is currently C3
  - **_IMPORTANT: To apply root note, use scale selector button (Encoder 12)_**
- Button
  - 'Zero out' all notes to current selected root note.

### Encoder 14 : Random Rythm Generator

- Rotate Left / Right
  - Increase / Decrease speed of new random step / note frequency set.
- Button
  - Toggle On / Off.
  - Off by default.
  - When on, random step count with be applied to all 8 sequencer encoders.
  - Will keep generating new random sequences until turned off.
- LED
  - Random colour as visual indicator for new sequence generator

### Encoder 15 (Bottom Right): Global Start / Stop & Tempo Control

- Rotate Left / Right
  - Increase / Decrease global tempo.
- Button
  - Toggle Start / Stop of sequencer.
  - Resets counter to zero but does not clear current steps and / or note pitches.
- LED
  - Tempo Indicator

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
