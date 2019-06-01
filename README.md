# Python-CRC32-Forcer
===================

### Introduction ###

A command-line tool that lets you change the CRC-32 checksum to any value you want.
Mostly for cool filename like  `No Game No Life Zero [00000000].mkv`

### How it works ###

It appends 4 bytes at the end of the file so that the final checksum matches the desired value.
The additional contents are calculated via the algebraic approach presented in the following paper:

[Reversing CRC – Theory and Practice, HU Berlin Public Report, SAR-PR-2006-05.
Authors: Martin Stigge, Henryk Plötz, Wolf Müller, Jens-Peter Redlich](https://sar.informatik.hu-berlin.de/research/publications/SAR-PR-2006-05/SAR-PR-2006-05_.pdf)

Most video, audio, archive formats (mkv, mp4, avi, mp3, aac, wav, zip, rar, 7z, etc.) should have no problem with some unknown data at the end of files.

### Requirements ###

- Python 2.7+, or 3.3+ [recommended]
- A terminal

### Usage ###

Syntax: `python python_crc32_forcer.py <filename> <target CRC-32>`

Examples: `python python_crc32_forcer.py "D:\Code\FakeCRC32\Video.mp4" 1234ABCD`
