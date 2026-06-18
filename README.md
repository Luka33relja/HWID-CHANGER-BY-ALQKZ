🛠️ How It Works
HWID (Hardware ID) is a composite identifier generated from various hardware components during Windows installation. This tool modifies the underlying registry keys and device identifiers that Windows uses to calculate the HWID.

Methods used:

Registry Modification — Direct editing of registry values that Windows reads for HWID calculation
WMI Override — Intercepting WMI queries to return spoofed values
Device Driver Interaction — IOCTL calls to storage and network devices to modify serials
Backup & Restore — All original values are backed up before modification
📁 File Structure



hwid-changer/
├── src/
│   ├── spoofers/
│   │   ├── motherboard.py
│   │   ├── disk.py
│   │   ├── mac.py
│   │   └── registry_ids.py
│   ├── backup.py
│   ├── utils.py
│   └── main.py
├── backups/           # Auto-generated backups
├── requirements.txt
└── README.md
💾 Backup System
All original values are automatically saved to backups/ before any modification:

backup_YYYYMMDD_HHMMSS.json — Timestamped backup
restore.bat — Generated batch file for manual restoration
Backup contains: original registry keys, serials, MACs, and volume IDs
❗ Known Limitations / Caveats
Antivirus flags: Some AV software may flag HWID modification as suspicious — this is expected behavior
Windows Update: Major Windows updates may regenerate some identifiers
TPM / Secure Boot: TPM-bound identifiers cannot be spoofed without TPM reset
Some software stores HWID server-side: Spoofing locally may not bypass server-side HWID checks
🤝 Contributing
Pull requests are welcome. For major changes, open an issue first.

Areas needing work:

GUI frontend (PyQt / Tkinter / web-based)
Linux support
EFI / UEFI variable spoofing
Better AMI BIOS UUID handling
📜 License
MIT — Free for educational and personal use.

🧪 Tested On
Windows 10 22H2 ✅
Windows 11 23H2 ✅
Windows 11 24H2 ✅
 How TO use start the .exe click 1 for windows 10 click 2 for windows 11 select if you only want to change HWID or HWID and ip 
