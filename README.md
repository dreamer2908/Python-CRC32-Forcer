# Python CRC32 Forcer

### Introduction ###

A command-line tool that lets you change the CRC-32 checksum of a file to any value you want.

Mostly for cool filenames like  `No Game No Life Zero [00000000].mkv`

### How it works ###

It appends 4 bytes at the end of the file so that the final checksum matches the desired value.

The additional contents are calculated via the algebraic approach presented in the following paper:

[Reversing CRC – Theory and Practice, HU Berlin Public Report, SAR-PR-2006-05.
Authors: Martin Stigge, Henryk Plötz, Wolf Müller, Jens-Peter Redlich](https://sar.informatik.hu-berlin.de/research/publications/SAR-PR-2006-05/SAR-PR-2006-05_.pdf)

Steps:
1. Read the file and calculate the original checksum.
2. Calculate the 4 additional bytes.
3. Append them at the end of the file.
4. Read the file and calculate the final checksum and show the result.

The function for step 2 were adapted from the C code in `Listing 6: Implementation of data adjustment at the end for a chosen CRC` (page 20). It runs at 40000 ops on my Core i3-3240 so step 2 shouldn't take more than 0.000025 seconds on newer PCs.

Most video, audio, and archive formats (mkv, mp4, avi, mp3, aac, wav, zip, rar, 7z, etc.) should have no problem with some unknown data at the end of files. So don't worry, it won't ruin your files.

### Requirements ###

- Python 2.7+ or 3.3+
- A terminal

Tested on Linux Mint 19 32-bit XFCE edition with Python 2.7.15rc1 & Python 3.7.6, and Windows 10 Pro version 1809 with Python 3.7.0.

### Usage ###

Syntax: `python python_crc32_forcer.py <filename> <target CRC-32>`

Examples: `python python_crc32_forcer.py "D:\Code\FakeCRC32\Video.mp4" 1234ABCD`

![2019-06-01_154340](https://user-images.githubusercontent.com/1423237/58746095-6fef1600-8484-11e9-8afa-0243dbb8ffa1.png)

![Screenshot_2019-06-01_16-07-17](https://user-images.githubusercontent.com/1423237/58746338-73d06780-8487-11e9-821b-7ad29a52d32a.png)
