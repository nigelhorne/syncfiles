# syncfiles

## Overview
This script automates the backup of files from a specified directory into a date-organized hierarchy across multiple backup locations.
It ensures that timestamps (access and modification times) are preserved and that files are stored in read-only mode to prevent accidental modifications.

## Features
- Organizes files into `Year/Month/Day` structure
- Supports multiple backup destinations
- Preserves file timestamps
- Ensures backup directories exist before copying
- Implements logging for tracking operations
- Skips existing files to prevent redundant copies

## Requirements
- Perl 5+
- Required Perl modules:
  - `File::Util`
  - `File::stat`
  - `File::Copy`
  - `File::Spec`
  - `DateTime`
  - `File::Path`
  - `Try::Tiny`
  - `Log::Log4perl`

## Installation
1. Install Perl and required modules using CPAN:
   ```sh
   cpan install File::Util File::stat File::Copy File::Spec DateTime File::Path Try::Tiny Log::Log4perl
   ```
2. Copy the script to a desired location.
3. Ensure the script has executable permissions:
   ```sh
   chmod +x syncfiles
   ```

## Usage
Run the script with the directory to be backed up as an argument:
```sh
./syncfiles /path/to/source/directory
```

Copy all files in a given directory to a date-based hierachy in a number of places (@targets).
The dates of last access and modification are preserved.

For example "syncfiles /tmp/foo" will copy all of the files last modified on
22/8/18 in /tmp/foo to /target1/2018/August/22, /target2/2018/August/22
and so on.

I use this to take lots of copies of photographs to many disks for backup,
and have them sorted by date.

## Logging
- Logs are saved in `/tmp/syncfiles.log`.
- Errors and successful operations are recorded for review.

## Error Handling
- If a file cannot be copied, an error message is logged instead of stopping execution.
- If a directory cannot be created, the script logs the failure and continues.

## License
- Personal single user, single computer use: GPL2
- For commercial, charity, educational, or government use, a license is required.

## Contact
For licensing inquiries, contact: **Nigel Horne** (njh@bandsman.co.uk).
