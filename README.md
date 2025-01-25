# HtmlBlfReader

HtmlBlfReader is a JavaScript-based tool designed to parse binary log files (BLF) in the browser. It reads binary data, unpacks various data structures, and supports displaying the parsed output in a human-readable format using JavaScript and HTML.

---

## Features

- **File Loading**: Load and parse BLF files directly in the browser.
- **Binary Data Parsing**: Supports parsing of binary-encoded CAN messages and object structures.
- **Compression Handling**: Handles uncompressed and ZLIB-compressed data blocks.
- **Real-Time Output**: Displays parsed data in a formatted way on the web page.
- **Cross-Browser Compatibility**: Works with modern browsers that support `FileReader` and `DataView`.

---

## Requirements

- A modern web browser (Chrome, Firefox, Edge, etc.).
- No additional server-side requirements — runs entirely in the browser.

---

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/HtmlBlfReader.git
   cd HtmlBlfReader
   ```

2. Open the `index.html` file in a browser to start the application.

---

## File Structure

```
HtmlBlfReader/
├── index.html        # Main HTML file with the UI structure
├── script.js         # Main JavaScript file for logic and parsing
├── README.md         # Project documentation
```

---

## Usage

1. Open `index.html` in your browser.
2. Use the **"Load"** button to select a `.blf` file.
3. Click **"Show Content"** to parse the file and display the output.

### Output

The parsed data will be displayed in the output section of the page. For instance:

```
Loaded file: example.blf

Timestamp: 1737813045.5
Arbitration ID: 12345
Is Extended ID: true
Is Remote Frame: false
DLC: 8
Data: 12, 34, 56, 78
Channel: 0
```

---

## Key Functions

### Parsing Functions
- **`FILE_HEADER_STRUCTunpack`**: Parses the BLF file header.
- **`OBJ_HEADER_BASE_STRUCTunpack`**: Parses object header structures.
- **`parseData`**: Iterates over binary data and yields parsed objects.
- **`LOG_CONTAINER_STRUCTunpack`**: Handles log container unpacking and decompression.

### Helper Functions
- **`findLOBJ`**: Finds the "LOBJ" signature in the binary data.
- **`systemTimeToTimestamp`**: Converts system time arrays to timestamps.

---

## Contributing

Contributions are welcome! If you have ideas for improvements or new features:
1. Fork the repository.
2. Create a feature branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add feature description"
   ```
4. Push to your forked repository and submit a pull request.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

---

## Acknowledgments

- **[Pako](https://github.com/nodeca/pako)**: Used for ZLIB decompression.
- **HTML5 APIs**: `FileReader`, `DataView`, and `Uint8Array` for binary handling.

---

## Contact

For questions or suggestions, reach out via [GitHub Issues](https://github.com/yourusername/HtmlBlfReader/issues).
