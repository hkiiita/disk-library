# disk-library
A disk library for a simple file system. 

As of now , build a disk emulation library that will emulate a disk on top of a single file. Its interface includes functions to read, write, and flush disk blocks.

This shall provide as the persistent medium for the file system which reads and writes 4-Kbyte disk blocks.
Disk library will use a single (large) Unix file to emulate a disk. It will divide the file into 4-Kbyte blocks. Blocks will be written using a ``block number.'' You will use this number to compute the offset into the Unix file. For instance, disk block 10 will be at byte offset 10 * 4096 = 40960.

Disk Interface:
openDisk()
ReadDisk()
WriteDisk()
SyncDisk()

The calls return an error if the underlying Unix system calls fail.

```openDisk``` opens a file ( filename) for reading and writing and returns a descriptor used to access the disk. The file size is fixed at nbytes. If filename does not already exist, openDisk creates it.

```readBlock``` reads disk block blocknr from the disk pointed to by disk into a buffer pointed to by block.

```writeBlock``` writes the data in block to disk block blocknr pointed to by disk.

```syncDisk``` forces all outstanding writes to disk.

