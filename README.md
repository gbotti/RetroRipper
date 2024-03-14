# RetroRipper

RetroRipper is a bash script designed to simplify the process of digitally archiving floppy disks. Utilizing the GreaseWeazle hardware and tools for accurate reads of floppy disks across various formats, it integrates optional scanning of the physical disk to capture images for comprehensive archival. RetroRipper provides an intuitive interface for selecting specific dumping profiles to accommodate different disk types.

## Features

- **Profile Selection**: Choose from predefined profiles for different floppy disk formats to ensure accurate dumping.
- **Multi-Disk Support**: Processes multiple disks sequentially with individual handling options.
- **Automatic Scanning**: Optionally scans the physical disk after dumping, if a scanner is configured, to facilitate visual archives.
- **Dependency Checks**: Ensures all required tools and dependencies are installed before starting operations.
- **Custom Configurations**: Allows for script configuration adjustments to meet specific needs.

## Prerequisites

Ensure the following dependencies are installed on your system before running RetroRipper:

- `gw` (GreaseWeazle software) - [GreaseWeazle GitHub](https://github.com/keirf/greaseweazle)
- `hxcfe` (HxC Floppy Emulator software) - [HxC Floppy Emulator](https://hxc2001.com/download/floppy_drive_emulator/)
- `7zz`
- `convert` (ImageMagick)
- `yq`
- `scanimage`
- `dialog`

## Hardware Requirements

To use RetroRipper, you'll need the following hardware:

- **GreaseWeazle Device**: Specifically, a GreaseWeazle V4 is used for interfacing with floppy drives to digitize the disks.
- **Floppy Drives**:
  - **3.5" Floppy Drive** configured as Drive A for 3.5-inch floppy disks.
  - **5.25" Floppy Drive** configured as Drive B for 5.25-inch floppy disks.
- **Flatbed Scanner**: A direct-attached, `scanimage`-compatible flatbed scanner for digitizing the physical appearance of the floppy disks. Ensure your scanner is supported by the `scanimage` tool for seamless integration.

Ensure your system meets these hardware specifications to fully utilize RetroRipper's capabilities for digital preservation.


## Configuration (most important variables)

1. **ScanImage**: Control whether the script attempts to scan the floppy disk post-dumping. Set to `1` to enable, `0` to disable.
2. **Scanner**: Specify the scanner device identifier (found using `scanimage -L`).
3. **OutputPath**: Define where the floppy dumps and scans are saved.

## Usage

1. Adjust the script's configuration section to your needs.
2. Connect your GreaseWeazle device and prepare the scanner if scanning is enabled.
3. Run the script: `./retroripper`

RetroRipper guides you through selecting a dumping profile, inserting disks, and optionally scanning them.

## Profiles

Supported profiles for different types of floppy disks include:

- **IBM 3.5" Floppy with 1.44 MB** (`ibm.1440`): Standard 3.5-inch, 1.44 MB floppy disks.
- **IBM 3.5" Floppy with 720 KB** (`ibm.720`): Standard 3.5-inch, 720 KB floppy disks.
- **IBM 5.25" Floppy with 360 KB** (`ibm.360`): Older 5.25-inch, 360 KB floppy disks, requiring double stepping.
- **IBM 5.25" Floppy with 1.2 MB** (`ibm.1200`): High-density 5.25-inch, 1.2 MB floppy disks.
- **IBM 5.25" Floppy with 160 KB** (`ibm.160`): Early 5.25-inch, 160 KB floppy disk formats, requiring double stepping.

Select the corresponding profile when prompted to ensure the correct parameters are used for disk dumping.

## Customizing Profiles

Profiles are defined in a YAML file. Edit or add profiles in this file to accommodate various disk types.

## Acknowledgments

Special thanks to Keir Fraser ([keirf](https://github.com/keirf)) for the creation of the GreaseWeazle tool, providing essential technology for digital preservation enthusiasts. Heartfelt gratitude also to Jean-François Del Nero for developing the HxC Floppy Emulator software ([HxC Floppy Emulator](https://hxc2001.com/download/floppy_drive_emulator/)), a cornerstone in the retro computing community for floppy disk emulation and preservation. Additionally, a shoutout to Tech Tangents ([AkBKukU](https://github.com/AkBKukU)) for the idea of creating a bitmap of the raw rip to accompany the digital archive. Your contributions significantly enhance our ability to preserve digital history.

## Contributions

Contributions to RetroRipper are welcome! Feel free to fork, enhance, and submit pull requests.

## License

RetroRipper is distributed under the MIT License. See LICENSE for more information.

## Disclaimer

RetroRipper comes with no warranty. It is used at your own risk, and the authors are not responsible for any hardware damage or data loss.
