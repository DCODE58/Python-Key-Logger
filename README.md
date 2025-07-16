# Python-Key-Logger
yeah You read it right 

# Advanced Keylogger - Python Keylogging Utility

![Python Version](https://img.shields.io/badge/python-3.7%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)

A sophisticated keylogger implementation with advanced features including timestamped logging, inactivity detection, and special key handling. Designed for security research and ethical monitoring purposes.

## Features

- **Precise Timestamping**: Each keystroke logged with millisecond precision
- **Human-Readable Formatting**: Special keys translated to readable format (e.g., [ENTER], [TAB])
- **Inactivity Detection**: Automatic detection and logging of idle periods
- **Session Tracking**: Automatic session start/end markers with duration
- **Unique Log Files**: Automatically generated timestamped log files
- **Graceful Shutdown**: Clean exit via ESC key or Ctrl+C
- **Robust Error Handling**: Comprehensive exception handling

## Prerequisites

- Python 3.7+
- pip package manager

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/advanced-keylogger.git
cd advanced-keylogger
```

2. Install dependencies:
```bash
pip install pynput
```

## Usage

```bash
python advanced_keylogger.py
```

**Controls:**
- Press `ESC` to stop logging and save the file
- Press `Ctrl+C` to gracefully exit the program

**Log File Example:**
```
Keylogger started at 2025-07-17 14:30:45.123
Inactivity threshold: 300 seconds
--------------------------------------------------

2025-07-17 14:30:46.452 > H
2025-07-17 14:30:46.678 > e
2025-07-17 14:30:46.891 > l
2025-07-17 14:30:47.102 > l
2025-07-17 14:30:47.305 > o
2025-07-17 14:30:47.521 > [SPACE]
2025-07-17 14:30:48.003 > [ENTER]

2025-07-17 14:35:48.003 > [INACTIVITY DETECTED - 300s]

--------------------------------------------------
Keylogger stopped at 2025-07-17 14:35:48.005
```

## Configuration

Modify these variables in the `AdvancedKeyLogger` class for customization:

```python
self.idle_threshold = 300  # Inactivity threshold in seconds
self.log_file = "custom_prefix_{timestamp}.txt"  # Custom filename pattern
```

## Ethical Considerations

**Important:** This tool should only be used:
- On systems you own
- With explicit permission from all monitored users
- In compliance with all applicable laws and regulations

Unauthorized use of this software may violate privacy laws and computer misuse statutes in many jurisdictions. The developers assume no liability for misuse of this tool.

## Technical Details

### Key Handling
- Alphanumeric keys: Logged as characters
- Special keys: Translated to human-readable format:
  - Space → " "
  - Enter → "[ENTER]"
  - Tab → "[TAB]"
  - Backspace → "[BACKSPACE]"
  - Other special keys → "[KEY_NAME]"

### Inactivity Monitoring
A separate thread checks for inactivity every 10 seconds. If no keys are pressed for the configured threshold (default 5 minutes), it logs an inactivity event with the duration.

### File Management
Log files are created with the pattern `keylog_YYYYMMDD_HHMMSS.txt` in the same directory as the script. The absolute path is displayed when the logger starts.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please open an issue to discuss proposed changes before submitting a pull request.

## Disclaimer

This software is provided for educational and ethical monitoring purposes only. The developers are not responsible for any misuse of this tool. Use at your own risk and always comply with applicable laws.
