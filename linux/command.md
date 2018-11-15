Copy directories recursively:
rsync -a source_dir/ dest_dir/

Comparing 2 files (graphical):
gvimdiff file1 file2
tkdiff file1 file2
meld file1 file2

Show the total size on disk of files or directories (disk usage):
du -sh dir1 dir2 file1 file2

Number of bytes, words and lines in file:
wc file (word count)

Tell more information about user:
finger user

Basic command-line calculator
bc -l

Define a default gateway for packets to machines outside the local network:
sudo route add default gw 192.168.0.1

Delete the default route:
sudo route del default

Create (format) an ext3 filesystem:
mkfs.ext3 /dev/hda1

Create (format) a FAT32 filesystem:
mkfs.vfat -v -F 32 /dev/hda2

Mount a filesystem image (loop device):
sudo mount -o loop fs.img /mnt/fs

Check the system kernel version:
uname -a