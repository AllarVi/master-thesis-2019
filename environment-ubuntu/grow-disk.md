grow-disk.md


sudo lsblk
NAME        MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
loop0         7:0    0    97M  1 loop /snap/core/9289
loop1         7:1    0    18M  1 loop /snap/amazon-ssm-agent/1566
loop2         7:2    0  96.5M  1 loop /snap/core/9436
loop3         7:3    0  28.1M  1 loop /snap/amazon-ssm-agent/2012
nvme0n1     259:0    0 116.4G  0 disk
nvme1n1     259:1    0    64G  0 disk
└─nvme1n1p1 259:2    0    64G  0 part /

sudo growpart /dev/nvme1n1 1


sudo resize2fs /dev/nvme1n1p1

sudo df -h