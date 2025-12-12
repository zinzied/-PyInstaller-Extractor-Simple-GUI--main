# PyInstaller Extractor - Enhanced GUI

A powerful and user-friendly GUI tool for extracting and decompiling PyInstaller executables with enhanced features including progress tracking, drag & drop support, and support for modern Python versions via PyCDC.

![image](https://github.com/user-attachments/assets/196b265f-eccd-437c-9661-fd39fcf2d252)

## ✨ New Features

### 🐍 Modern Python Support (New!)
- **PyCDC Integration**: Support for decompiling **Python 3.9+** (including 3.10, 3.11, 3.12, 3.13, 3.14) by integrating `pycdc.exe`.
- **Automatic Fallback**: Smartly chooses between `decompyle3` (for older Python) and `pycdc` (for newer Python) based on availability.

### 🔐 Robust Extraction
- **Signed Executables**: Now supports extracting digitally signed executables or files with appended data.
- **Missing Manifests**: Fallback logic to decompile files even if the archive structure is non-standard (missing `.manifest` files).

### 🎯 Progress Bar & Status Updates
- Real-time progress tracking during extraction
- Detailed status messages for each extraction phase
- Visual feedback for long-running operations

### 🖱️ Drag & Drop Support
- Simply drag and drop executable files onto the application
- Automatic file validation (only .exe files accepted)
- Intuitive user interface

## 🚀 Key Features

- **PyInstaller Archive Extraction**: Supports PyInstaller versions 2.0, 2.1+, and 3.0+
- **Smart Decompilation**: Automatically decompiles extracted `.pyc` files to source code (`.py`)
- **Modern GUI**: Clean CustomTkinter-based interface with dark mode
- **Threaded Operation**: No UI freezing during large extractions
- **Detailed Logging**: Comprehensive log of entry points and file operations

## 📋 Requirements

- Python 3.6+
- CustomTkinter
- tkinterdnd2
- colorama
- pyinstaller
- decompyle3 (installed via requirements)

### Optional (for newer Python versions)
- **pycdc.exe** (Decompyle++): Required to decompile Python 3.9+ files.

## 🛠️ Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/PyInstaller-Extractor-Enhanced-GUI.git
cd PyInstaller-Extractor-Enhanced-GUI
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. **(Recommended) Add PyCDC:**
   - Download or compile `pycdc.exe` from [Decompyle++](https://github.com/zrax/pycdc).
   - Place `pycdc.exe` in the **root folder** of this application (next to `main.py`).

4. Run the application:
```bash
python main.py
```

## 📖 Usage

### Method 1: Drag & Drop
1. Launch the application
2. Drag an executable (.exe) file onto the drop area
3. Click **Extract** to unpack the archive
4. Click **Decompile** to convert bytecode to source code

### Method 2: File Browser
1. Launch the application
2. Click **Browse** to select an executable file
3. Click **Extract** and then **Decompile**

### Output
- **Extracted Files**: Saved in `[filename]_extracted` folder
- **Source Code**: Decompiled Python files are saved in the `result` folder

### Decompilation Logic
- The tool checks for `pycdc.exe` in the application folder.
- **If found**: It uses `pycdc` (supports Python 3.14 etc).
- **If not found**: It falls back to `decompyle3` (supports up to Python 3.8).

## 🔍 Supported File Types

- PyInstaller executables (.exe)
- Digitally signed executables
- Executables with extra data appended

## ⚠️ Notes

- **Password Protected**: Encrypted archives cannot be extracted without the key.
- **Obfuscation**: Heavily obfuscated code may not decompile cleanly.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.
