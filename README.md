# speech_recognization

A Python library and command-line tool for performing speech recognition, audio segment processing, and model management. This project is designed for developers and researchers who need robust audio-to-text capabilities, with a focus on handling various audio formats and easy integration with speech recognition models like Vosk.

## Features

- **Audio Data Handling:** Provides a flexible `AudioData` class for reading, slicing, and converting audio between WAV, AIFF, FLAC, and raw byte formats.
- **Model Management:** Includes a CLI for downloading and setting up Vosk speech recognition models.
- **Command-Line Interface:** Use the `sprc` tool to manage models and perform utility operations.
- **Testing:** Comes with a suite of unit tests for audio loading, segmentation, and format conversion.
- **Extensible:** Designed for integration with other speech recognition engines and APIs.

## Installation

Requires **Python 3.9+**.

Clone this repository and install with pip:

```bash
git clone https://github.com/bhawan-grewall/speech_recognization.git
cd speech_recognization
pip install .
```

Or install in editable/development mode:

```bash
pip install -e .
```

## Usage

### Command-Line Tool

Download and setup a Vosk model:

```bash
sprc download vosk --url https://alphacephei.com/vosk/models/vosk-model-small-en-us-0.15.zip --dir model
```

The model will be downloaded and extracted to the `model` directory.

### Python API

```python
import speech_recognition as sr

# Load audio data and process it
audio = sr.AudioData.from_file("audio.wav")
segment = audio.get_segment(start_time, end_time)
raw_bytes = segment.get_raw_data()
```

## Development

### Lint and Check

```bash
make lint
make rstcheck
```

### Build and Publish

```bash
make distribute
make publish
```

### Run Tests

```bash
python -m unittest discover
```

## Project Structure

```
speech_recognition/   # Library source code
tests/                # Unit tests
Makefile              # Development utilities
setup.py              # Packaging script
make-release.sh       # Release helper
```

## License

This project is based on the BSD License. See [LICENSE](LICENSE) for details.

## Credits

Developed by [bhawan-grewall](https://github.com/bhawan-grewall).  
Inspired by and adapted from the [Uberi/SpeechRecognition](https://github.com/Uberi/speech_recognition) project.

---

> _Note: For more details and advanced usage, please refer to the source code and docstrings._
