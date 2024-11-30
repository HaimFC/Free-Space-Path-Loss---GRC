# Digital Wireless Communication System Using GNU Radio

This project implements a digital wireless communication system using GNU Radio for transmitting and receiving data. It simulates the principles of amplitude shift keying (ASK) and supports text-based transmission with real-time decoding.

## Overview

### Components

1. **Transmitter** (`lab1 - transmitter.grc`):
   - Reads the `Alice.txt` file as input.
   - Encodes text using Varicode and converts it into a binary stream.
   - Modulates the binary stream and sends it over a software-defined radio (SDR).

2. **Receiver** (`lab1 - receiver.grc`):
   - Captures and demodulates the transmitted signal using an SDR.
   - Decodes the binary stream back into text.
   - Outputs the decoded text to the console.

### Key Features

- **Varicode Encoding**: Efficiently converts text into binary streams with self-synchronizing properties.
- **GNU Radio Integration**: Uses GNU Radio Companion (GRC) for flowgraph design.
- **SDR Support**: Compatible with LimeSDR or USRP devices for real-world transmission.
- **Visualization**: Provides real-time signal analysis via QT GUI sinks.

## How to Use

### Equipment Setup

- Two Linux PCs with GNU Radio installed.
- Two SDR devices (LimeSDR or USRP).
- RF cables and adapters for connecting the transmitter and receiver.

### Transmitter Configuration

1. Set the sample rate to `192 kHz`.
2. Configure a `File Source` block to read `Alice.txt`.
3. Add a `Varicode Encoder` to convert text to a binary stream.
4. Modulate the binary stream using a Gaussian FIR filter.
5. Set the carrier frequency based on your assigned pair number:
6. Use an `osmocom Sink` to send the modulated signal.

### Receiver Configuration

1. Set the sample rate to `1.2 MHz`.
2. Capture the signal using an `osmocom Source`.
3. Use a `Low Pass Filter` for demodulation.
4. Decode the signal using a `Varicode Decoder`.
5. Output the decoded text to the console via a `File Sink`.

### Running the System

1. Launch the transmitter and receiver flowgraphs on separate PCs.
2. Observe the transmitted and received text in real-time.

## Experiments and Analysis

### Power vs. Distance
- Measure the received signal strength at varying distances between the transmitter and receiver.
- Plot the power vs. distance graph and analyze the relationship.

### Thresholds
- Determine the gain thresholds for:
- Starting error accumulation.
- Complete signal loss.
- Suggest methods to improve system performance.

### Results
- Verify errorless transmission at short distances.
- Document observations with screenshots and explanations.

## Dependencies

- GNU Radio (compatible with version 3.8 or higher).
- LimeSDR or USRP hardware.
- Python for custom scripts within GRC.

## File Structure

- `lab2 - transmitter.grc`: Transmitter flowgraph.
- `lab1 - receiver.grc`: Receiver flowgraph.
- `Alice.txt`: Input text file for transmission.

## Authors

- Developed as part of the Wireless Communications Laboratory at The School of Electrical and Computer Engineering. - Ben Gurion University
