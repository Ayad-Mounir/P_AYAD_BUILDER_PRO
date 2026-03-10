<<<<<<< HEAD
version https://git-lfs.github.com/spec/v1
oid sha256:c43f4051da3d8dbdc3c8dd98e69d1bc0a3ee43660323a30c0e7dc0d9474fa21e
size 61
=======
# AYAD BUILDER PRO v22.2

[![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python&logoColor=white)](https://www.python.org/)
[![PyQt6](https://img.shields.io/badge/PyQt6-6.4+-green?logo=qt&logoColor=white)](https://www.riverbankcomputing.com/software/pyqt/)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen)](https://github.com/Ayad-Mounir/AYAD_BUILDER_PRO)

## 🎯 Problem & Purpose

AYAD BUILDER PRO is a professional Python application builder designed for developers who need to create, analyze, and package Python projects into standalone executables without wrestling with complex dependency management and build configurations. If you've struggled with PyInstaller hidden imports, encoding issues, or debugging compiled applications, this tool eliminates those pain points through intelligent project analysis, automatic dependency detection, and a visual build interface. The application provides complete support for both Arabic and English, making it accessible to developers worldwide.

## ✨ Features

- **Intelligent Project Analysis** — Automatically scans your Python codebase to identify all dependencies, hidden imports, and library configurations without manual configuration
- **Multi-Language Support** — Complete Arabic/English interface with real-time language switching via the `Translator` class for seamless localization
- **Executable Diagnostics** — Built-in exe diagnostic system that identifies runtime issues and suggests fixes through the `diagnose_exe()` method
- **PE File Analysis** — Comprehensive parsing and examination of executable structure including imports, exports, resources, and debug information using industry-standard PE format handling
- **Protected Build System** — Integrated protection and obfuscation mechanisms documented in PROTECTION_GUIDE.md to secure your compiled applications
- **UTF-8 Console Handling** — Automatic Windows console encoding fixes to eliminate Unicode/encoding crashes in compiled applications
- **Virtual Environment Management** — Built-in venv creation and management through `VenvManager` for isolated dependency handling
- **Error Recovery & Logging** — Global exception handlers with safe fallback logging when stdout/stderr are closed in windowed mode

## 🛠️ Tech Stack

| Component | Technology | Version |
|-----------|-----------|---------|
| **Language** | Python | 3.9+ |
| **GUI Framework** | PyQt6 | 6.4–6.9 |
| **Build Tool** | PyInstaller | 5.13–6.x |
| **Cryptography** | cryptography | 41.0–42.x |
| **HTTP Client** | requests | 2.28–2.x |
| **Type Hints** | typing-extensions | 4.0–4.x |
| **PE Parsing** | pefile (bundled) | — |

## 📁 Project Structure

```
AYAD_BUILDER_PRO/
├── core/                          # Core build and analysis engine
│   ├── build_adapter.py          # Build system interface
│   ├── build_engine.py           # Main build orchestration
│   ├── orchestrator.py           # Component coordination
│   └── protection_system.py      # Application protection
├── managers/                       # Feature managers
│   ├── project_analyzer.py       # Dependency & import detection
│   └── venv_manager.py           # Virtual environment handling
├── knowledge_base/                # Library & configuration database
│   ├── knowledge/
│   ├── intelligence/
│   ├── hooks/
│   └── services/
├── ui/                            # User interface components
├── utils/                         # Utility functions & helpers
├── resources/                     # Icons, images, translations
├── tests/                         # Unit & integration tests
├── translations.py                # Multi-language support
├── constants.py                   # Library configs & imports
├── AYAD_BUILDER_PRO.spec         # PyInstaller specification
├── PROTECTION_GUIDE.md           # Security documentation
├── DIAGNOSTIC.bat                # Windows diagnostics script
└── requirements.txt              # Python dependencies
```

## 📋 Prerequisites

- **Python 3.9 or higher** (check via `python --version`)
- **Windows 10/11, macOS, or Linux** (Windows console optimization included)
- **pip** (Python package manager, included with Python)
- **500 MB free disk space** for virtual environment and dependencies
- **PyQt6 6.4+** (will be installed automatically)

## 🚀 Installation

### Method 1: Quick Setup (Recommended)

1. **Download the project** from GitHub or extract the AYAD_BUILDER_PRO folder
2. **Open Command Prompt** (Windows) or Terminal (macOS/Linux) in the project folder
3. **Run the setup**:
   ```bash
   pip install -r requirements.txt
   ```
4. **Verify installation**:
   ```bash
   python main.py --version
   ```

### Method 2: Manual Setup with Virtual Environment

1. **Create a virtual environment**:
   ```bash
   python -m venv .ayad_build_venv
   ```
2. **Activate the environment**:
   - **Windows**: `.ayad_build_venv\Scripts\activate`
   - **macOS/Linux**: `source .ayad_build_venv/bin/activate`
3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## 📖 Usage Guide

### Starting the Application

**Windows users**: Double-click `main.py` to launch the GUI.

**All platforms**: Open a terminal in the project folder and run:
```bash
python main.py
```

The application will:
- Initialize the console with UTF-8 encoding (Windows optimization)
- Verify PyQt6 installation and offer to install if missing
- Display the main application window

### 🔍 Core Workflow: Building a Python Project to EXE

#### Step 1: Load Your Project
1. Click **File** → **Open Project** in the menu bar
2. Navigate to your Python project folder (the one containing your main script)
3. Click **Select Folder**
4. The application will scan all `.py` files and display project information

#### Step 2: Review Project Analysis
Once loaded, you'll see:
- **Detected Dependencies** — All imported libraries (e.g., `requests`, `numpy`, `PyQt6`)
- **Hidden Imports** — Detected modules that PyInstaller typically misses
- **Entry Point** — Your main Python script selected by default
- **Project Tree** — All source files organized hierarchically

⚠️ **Check for missing dependencies** — If critical libraries are marked in red, install them first: `pip install library_name`

💡 **Tip**: The analyzer automatically detects common patterns (Django, Flask, machine learning) and suggests appropriate configurations.

#### Step 3: Configure Build Settings
1. In the **Build Settings** panel, set:
   - **Output Name** — Name of your `.exe` (default: your project name)
   - **Icon** — Click the folder icon to select a `.ico` file for your executable
   - **Console Mode** — Toggle between windowed app (unchecked) and console app (checked)
   - **One-File** — Checked = single `.exe` file; unchecked = folder with dependencies
2. Expand **Advanced Options** for:
   - **Optimization Level** — Trade-off between speed and file size
   - **Strip Binaries** — Remove debug symbols to reduce size
   - **Custom Hooks** — For complex dependencies like TensorFlow or OpenCV

⚠️ **Icon requirement**: Use 256×256 `.ico` files; PNG files must be converted first.

#### Step 4: Run Diagnostics (Optional but Recommended)
1. Click **Tools** → **Run Diagnostics**
2. The system will check:
   - Python version compatibility
   - PyQt6 installation integrity
   - Available disk space
   - Missing C++ runtime libraries
3. Fix any ⚠️ warnings before proceeding

#### Step 5: Start the Build
1. Click the **Build Project** button (green button with hammer icon)
2. Monitor the progress bar as the system:
   - Collects all dependencies
   - Resolves hidden imports
   - Compiles Python bytecode
   - Links executable
3. A build log window shows detailed output (watch for ⚠️ warnings)

#### Step 6: Test Your Executable
1. Once complete, click **Open Output Folder** to view your compiled `.exe`
2. Navigate to the output folder (typically `dist/` or `build/`)
3. Double-click the `.exe` to test your application
4. If errors occur:
   - Click **Tools** → **Analyze Error** in the app
   - Paste the error message
   - View suggested fixes

### 🔐 Language Switching
1. In the **Preferences** menu, select:
   - **English** — Full English interface
   - **العربية** (Arabic) — Complete Arabic localization
2. The interface reloads immediately
3. All dialogs, buttons, and help text update in real-time

### 🛡️ Protection & Obfuscation
For security-sensitive applications:
1. In **Advanced Options**, check **Enable Protection**
2. Configure protection level:
   - **Light** — Basic obfuscation
   - **Medium** — Code obfuscation + anti-debugging
   - **Heavy** — Full protection with tamper detection
3. See `PROTECTION_GUIDE.md` for detailed security information

### ⚠️ Common Issues & Fixes

| Issue | Solution |
|-------|----------|
| **PyQt6 not found** | Click the auto-install button or run: `pip install PyQt6` |
| **"AttributeError: module has no attribute"** | Run **Tools** → **Analyze Error** and follow suggestions |
| **Executable crashes on startup** | Check **Console Mode** toggle; windowed apps need proper event handling |
| **Build fails with "hidden import not found"** | Add to Advanced Options → Custom Hooks: `--hidden-import=module_name` |
| **Large file size (>500MB)** | Enable **Strip Binaries** and set **One-File** to false |
| **Windows Defender flags the exe** | This is normal; sign the executable or add exception in Defender |

### 💡 Best Practices

- **Test locally first**: Always run your Python script with `python script.py` before building
- **Freeze dependencies**: Generate a pinned requirements file: `pip freeze > pinned.txt`
- **Use relative paths**: Avoid hardcoded absolute paths; use `os.path.dirname(__file__)`
- **Minimal dependencies**: Remove unused imports to reduce executable size
- **Version your builds**: Include version info in output name (e.g., `MyApp_v1.2.1.exe`)

## 🧪 Testing

The project includes comprehensive unit and integration tests located in the `tests/` directory. These verify:
- Project analysis accuracy
- Dependency detection
- Build system integrity
- Language switching
- Error handling

Tests are automatically run during CI/CD pipelines. To run locally:
```bash
python -m pytest tests/ -v
```

## 📝 Contributing

Contributions are welcome! To contribute:

1. **Fork** the repository on GitHub
2. **Create a feature branch**: `git checkout -b feature/your-feature-name`
3. **Make changes** and test thoroughly
4. **Commit with clear messages**: `git commit -m "Add: description of changes"`
5. **Push to your fork**: `git push origin feature/your-feature-name`
6. **Submit a Pull Request** with description of changes

Please ensure all tests pass and code follows PEP 8 style guidelines.

## 📄 License

This project is licensed under the **MIT License** — see LICENSE file for details. You are free to use, modify, and distribute this software in personal and commercial projects.

## 👨‍💻 Author

| Contact | Details |
|---------|---------|
| 📧 **Email** | [![Email Badge](https://img.shields.io/badge/Email-contact.ayad.mounir%40gmail.com-red?style=flat-square&logo=gmail&logoColor=white)](mailto:contact.ayad.mounir@gmail.com) |
| 💬 **WhatsApp** | [![WhatsApp Badge](https://img.shields.io/badge/WhatsApp-%2B212653867667-25D366?style=flat-square&logo=whatsapp&logoColor=white)](https://wa.me/212653867667) |
| 🔗 **GitHub** | [![GitHub Badge](https://img.shields.io/badge/GitHub-Ayad--Mounir-black?style=flat-square&logo=github&logoColor=white)](https://github.com/Ayad-Mounir) |
| ✈️ **Telegram** | [![Telegram Badge](https://img.shields.io/badge/Telegram-%40Mounir__Ayad-0088cc?style=flat-square&logo=telegram&logoColor=white)](https://t.me/Mounir_AyadD) |

<p align="center">Made with ❤️ by Mounir Ayad</p>
>>>>>>> fc07fd29f10135860011978c34f1df6772268a56

<<<<<<< HEAD
<<<<<<< HEAD
=======

>>>>>>> 420334e072a2b65ac3cc0e440b63f02ecf619c01
=======
>>>>>>> 10b01d0a9faf4ec0b622e81c6127a07643c05704
## 📦 Downloads

| File | Size | Download |
|------|------|----------|
<<<<<<< HEAD
<<<<<<< HEAD
| `AYAD_BUILDER_PRO.exe` | — | [⬇️ Download](https://github.com/Ayad-Mounir/P_AYAD_BUILDER_PRO/releases/download/v20260305-033006/AYAD_BUILDER_PRO.exe) |
=======
| `AYAD_BUILDER_PRO.exe` | — | [⬇️ Download](https://github.com/Ayad-Mounir/P_AYAD_BUILDER_PRO/releases/download/v20260305-022309/AYAD_BUILDER_PRO.exe) |
>>>>>>> 420334e072a2b65ac3cc0e440b63f02ecf619c01
=======
| `AYAD_BUILDER_PRO.exe` | — | [⬇️ Download](https://github.com/Ayad-Mounir/P_AYAD_BUILDER_PRO/releases/download/v20260305-033006/AYAD_BUILDER_PRO.exe) |
>>>>>>> 10b01d0a9faf4ec0b622e81c6127a07643c05704

*Generated by [Ayad-RepoJet](https://github.com)*
