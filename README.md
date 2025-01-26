# HtmlBlfReader

HtmlBlfReader is a JavaScript-based tool designed to parse and display binary log files (BLF) directly in the browser. It provides real-time parsing and visualization of CAN messages, log containers, and related binary data structures.

---

## Features

- **File Loading**: Upload `.blf` files directly in the browser for parsing.
- **Binary Data Parsing**: Unpacks structured binary data such as CAN messages and log containers.
- **Real-Time Output**: Displays parsed data in a dynamic HTML table with readable timestamps and message details.
- **Compression Handling**: Supports ZLIB-compressed and uncompressed binary containers using the `pako` library.
- **Cross-Browser Compatibility**: Utilizes modern web APIs like `FileReader` and `DataView` for a seamless experience.
- **Responsive Design**: Presents parsed data in a clear and organized table format.

---

## Requirements

- A modern web browser (Chrome, Firefox, Edge, etc.).
- No additional server-side requirements — runs entirely in the browser.

---

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/tioali/HtmlBlfReader.git
   cd HtmlBlfReader
   ```

2. Open the `index.html` file in a browser to start the application.

---

## File Structure

```
HtmlBlfReader/
├── index.html        # Main HTML file with the UI structure and event listeners
├── script.js         # Main JavaScript file for parsing logic
├── README.md         # Project documentation
```

---

## Usage

1. Open `index.html` in your browser.
2. Use the **"Load .BLF File"** button to select a `.blf` file.
3. The parsed data will be displayed in the dynamic table with details such as timestamps, arbitration IDs, and message data.

### Example Output

Parsed data will be displayed in a table like this:

| Timestamp                    | ID          | Extended | Data (8-byte array)       |
|------------------------------|-------------|----------|---------------------------|
| Date: 2025-01-25, Time: 14:05:22 | 0x1FFFFFFF | Yes      | 12 34 56 78 90 AB CD EF  |

---

## Key Features

### Parsing Functions
- **`parseBLF`**: Main function for reading and parsing `.blf` files.
- **`parseData`**: Iterates over binary data and yields parsed objects like CAN messages.
- **`LOG_CONTAINER_STRUCTunpack`**: Handles log container unpacking and supports ZLIB decompression.

### Helper Functions
- **`systemTimeToTimestamp`**: Converts system time arrays to UNIX timestamps.
- **`findLOBJ`**: Finds the "LOBJ" signature in binary data for object detection.

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

- **Author**: tioali@gmai..com
- **GitHub**: [HtmlBlfReader](https://github.com/tioali/HtmlBlfReader)
