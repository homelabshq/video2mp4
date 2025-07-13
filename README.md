# VIDEO2MP4
This is a Bash script that converts various video file formats (e.g., `.avi`, `.mkv`, `.mov`, `.wmv`, `.flv`, `.webm`, `.m4v`, `.3gp`, `.ts`, `.mts`, `.m2ts`) to `.mp4`. The script supports converting a single file or multiple video files in a directory, with options for recursive directory search, skipping already existing files, and preserving metadata. It also includes a "no confirmation" mode for automatic overwriting of files.

## Versions
**Current version**: 0.0.1

## Table of Contents

- [Badges](#badges)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)
- [Contributing](#contributing)

## Badges

![Version](https://img.shields.io/badge/Version-0.0.1-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## Installation
1. Ensure you have [FFmpeg](https://ffmpeg.org/download.html) installed on your system. FFmpeg is used for video file processing.
    - On Ubuntu/Debian:  
      ```bash
      sudo apt install ffmpeg
      ```
    - On Mac (using Homebrew):  
      ```bash
      brew install ffmpeg
      ```
    - On Windows:  
      Download FFmpeg from [here](https://ffmpeg.org/download.html) and follow the instructions to set it up.
- Recommended installation approach
    ```bash
    curl -fsSL https://kanishkk.me/video2mp4 | bash
    ```

- Manual installation: Download the script from this repository and make it executable:
    ```bash
    chmod +x video2mp4.sh
    ```

## Usage
You can use the script to convert individual video files or entire directories of video files. Below are the command options and examples of usage:

### Command Options
```txt
Usage: ./video2mp4.sh -f <input_file> [-o <output_path>] | -d <directory> [-o <output_directory>] [-r] [-c] [-s] [-nc]

Options:
  Required Flags (Must provide either -f or -d):
    -f, --file <input_file>       Convert a single file.
    -d, --directory <directory>   Convert all supported files in a directory.

  Optional Flags:
    -o, --output <output_path>    Specify output file (if using -f) or output directory (if using -d).
    -r, --recursive               Process directories recursively.
    -c, --copy                    Convert without re-encoding if possible (faster but larger files).
    -s, --skip-existing           Skip existing files without prompt.
    -nc, --no-confirm             Automatically overwrite existing files without asking.
    -h, --help                    Show this help message.
```

### Examples
Convert a single video file to MP4:
```bash
./video2mp4.sh -f input.avi -o output.mp4
```

Convert all supported video files in a directory:
```bash
./video2mp4.sh -d /path/to/video/files
```

Recursively search and convert all video files in a directory and subdirectories:
```bash
./video2mp4.sh -d /path/to/video/files -r
```

Convert a video file without re-encoding (if container conversion is sufficient):
```bash
./video2mp4.sh -f input.mkv -c
```

Skip existing files during conversion:
```bash
./video2mp4.sh -d /path/to/video/files -s
```

Automatically overwrite files without confirmation:
```bash
./video2mp4.sh -d /path/to/video/files -nc
```

Convert with specific output directory:
```bash
./video2mp4.sh -d /path/to/source/videos -o /path/to/converted/videos
```

## License
This project is licensed under the MIT License. See [LICENSE](LICENSE) for more details.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change. Make sure to update tests as appropriate.

