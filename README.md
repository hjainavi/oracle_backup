# Oracle Auto Backup

A Windows desktop application for automated Oracle database schema backups. Built with Python Tkinter, it creates scheduled backups and optionally moves them to USB or network drives.

## Features

- GUI-based configuration for backup settings
- Automated daily backups using Windows Task Scheduler
- Export multiple Oracle schemas/users
- Configurable backup and destination paths
- Move backups to USB/external drives on schedule
- UNC path support for network drives
- User validation before backup configuration

## Technologies Used

- **Python 2.7** - Core programming language
- **Tkinter/ttk** - GUI framework
- **cx_Oracle** - Oracle database connectivity
- **win32wnet** - Windows network path handling
- **Windows Task Scheduler** - Backup scheduling
- **Inno Setup** - Windows installer creation (.iss files)

## Prerequisites

- Windows OS
- Python 2.7
- Oracle Client installed
- cx_Oracle library
- pywin32 library
- Administrative privileges (for Task Scheduler)

## Installation

1. Install Python dependencies:
```bash
pip install cx_Oracle pywin32
```

2. Run the GUI configuration:
```bash
python oracle_backup_gui.py
```

3. Or build the executable using py2exe:
```bash
python setup.py py2exe
```

## Configuration

The GUI allows you to configure:

| Setting | Description |
|---------|-------------|
| Default Oracle Backup Path | Directory where Oracle exports dumps |
| Your Backup Path | Destination for backup copies (USB/Network) |
| Folders to Backup | Additional folders to include |
| Backup Time | Time to run daily backup |
| Move Backup Time | Time to move files to destination |
| DBA Users To Backup | Comma-separated list of Oracle schemas |

## Usage

1. Launch `oracle_backup_gui.exe` or run `python oracle_backup_gui.py`
2. Configure backup paths and Oracle users
3. Set backup and move times
4. Click OK to create Windows scheduled tasks

The application creates two scheduled tasks:
- **oracle_backup** - Runs the backup at specified time
- **oracle_move_backup** - Moves files to destination path

## Files

| File | Description |
|------|-------------|
| `oracle_backup_gui.py` | Main GUI for configuration |
| `python_oracle_auto_backup.py` | Backup execution script |
| `setup.py`, `setup_*.py` | py2exe setup scripts for different configurations |
| `oracle_gui.iss` | Inno Setup installer script |
| `Backup_Users/` | Default user configuration files |

## License

This project is proprietary software developed for internal business use.
