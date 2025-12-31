# Music Automaton Composer

A procedural melody generator built with React and the Web Audio API. This application uses Finite State Automata principles to generate musical sequences in real-time based on selected scales and probability matrices.

## Features

- **Procedural Melody Generation**: Uses a Markov chain-like approach (Finite State Automaton) to navigate between notes (states).
- **Dynamic Controls**:
  - **Tempo**: Adjust playback speed (60-200 BPM).
  - **Instruments**: Choose from Sine, Triangle, Square, and Sawtooth waveforms.
  - **Scales**: Select from various musical scales including Major, Minor, Pentatonic, Blues, Dorian, Lydian, Mixolydian, Phrygian, Harmonic Minor, and Whole Tone.
  - **Melody Resolution**: Control how frequently the melody attempts to return to the root note (Tonic).
- **Visualizations**:
  - **Active State**: Visual indication of the current note playing.
  - **Melody Sequence**: A history view of the generated notes.
  - **Pulse Effects**: Visual feedback synced with the beat.
- **Responsive UI**: Modern interface with glassmorphism effects and dark mode aesthetics.

## Technology Stack

- **React**: UI library.
- **Vite**: Build tool and development server.
- **Web Audio API**: Real-time sound synthesis.
- **TailwindCSS**: Styling.
- **Lucide React**: Icons.

## Installation

1.  Clone the repository or navigate to the project directory.
2.  Install dependencies:

    ```bash
    npm install
    ```

## Usage

Start the development server:

```bash
npm run dev
```

Open your browser and navigate to the URL shown (usually `http://localhost:5173`).

### How It Works

1.  **States & Notes**: Each state in the automaton corresponds to a note in the selected scale.
2.  **Transitions**: The application calculates the next note based on a probability matrix.
    - **Step Up/Down**: High probability to move to adjacent notes.
    - **Skip**: Lower probability to jump intervals.
    - **Return to Tonic**: Controlled probability to return to the root note based on the "Resolution" setting.
3.  **synthesis**: The Web Audio API creates oscillators on the fly to play the calculated frequency for each note.

