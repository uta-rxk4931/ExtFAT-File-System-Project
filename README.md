# ExtFAT File System Project 

This project is a simplified implementation of the Extended File Allocation Table (ExtFAT) system, created for educational purposes as part of the CSE 3310 course at the University of Texas at Arlington. It includes tools for file system operations, image handling, and example programs demonstrating access and manipulation of image files.

---

## Project Structure

```
Extfat_3310_project-main/
├── include/               # Header files for file system and utility routines
├── common/                # Shared source files and helper functions
├── examples/              # Example programs and bash scripts to test the file system
├── .vscode/               # VS Code configuration files
├── .devcontainer/         # Docker Dev Container setup (optional)
├── complex.image          # Sample file system image
├── Makefile               # Build configuration
├── README.md              # Project documentation
```

---

## extfat utils

`extfat` is a utility to manipulate ExtFAT image files.

### Command Options

```
-i xxx    Input file name (default: test.image)
-o xxx    Output file name (default: same as input file)
-c        Copy input to output
-m        Use mmap for file access (default if -f and -m are not specified)
-f        Use fread for file access
-v        Verify ExtFAT image
-h        Display help message
-d        Print root directory structure
-x xxx    Extract a file named xxx from the image
```

### Example Invocations

```
extfat -c -i inputFile.image -o outputFile.image
extfat -c -f -i inputFile.image -o outputFile.image
extfat -v -f -i inputFile.image
extfat -v -i inputFile.image
extfat -d -i inputFile.image
extfat -x extractFile.image -i inputFile.image -o outputFile.image
```

---

## Build Instructions

```bash
make clean
make
```

To run tests:

```bash
make tests
```

---

## Run Examples

Navigate to the examples folder and create an image before running:

```bash
bash examples/create_image.bash
./examples/fread
./examples/mmap
```

To mount and unmount:

```bash
bash examples/mount_image.bash
bash examples/unmount_images.bash
```

---

## Development Environment (Optional)

To use the included VS Code Dev Container:

1. Install Docker and Visual Studio Code
2. Open the folder in VS Code
3. Choose "Reopen in Container" when prompted

---

## Author
Rency Kansagra (Group Member 11) 
University of Texas at Arlington




















## Misc notes, eventually delete.
```
dd if=/dev/zero of=zzz count=1 bs=1G
yum install -y exfat-utils fuse fuse-exfat
losetup /dev/loop0 diskimage 
mount /dev/loop0 /mnt
umount /mnt
```
## References


https://pawitp.medium.com/notes-on-exfat-and-reliability-d2f194d394c2


https://learn.microsoft.com/en-gb/windows/win32/fileio/exfat-specification


https://uta.service-now.com/selfservice?id=ss_kb_article&sys_id=KB0011414


https://nemequ.github.io/munit/#download


https://www.gnu.org/software/libc/manual/html_node/Example-of-Getopt.html


https://www.freecodecamp.org/news/how-to-use-git-and-github-in-a-team-like-a-pro/


https://en.wikipedia.org/wiki/ExFAT


https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax
