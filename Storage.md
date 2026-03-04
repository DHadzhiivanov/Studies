# ToC

- [[#NAS|NAS]]
- [[#SAN|SAN]]
- [[#RAID Redundant Array of Independent Disks]]
- [[#File-based storage|File-based storage]]
- [[#Block storage|Block-based storage]]
- [[#Object storage|Object storage]]

# NAS

No dedicated network for them. Often a lot of disks arranged into [[#RAID Redundant Array of Independent Disks|RAID]].

# RAID: Redundant Array of Independent Disks

- A storage virtualization technology which is used to organize multiple drives into various arrangements to meet certain goals.
- Uses a dedicated RAID controller

RAID 0 : Striping

- Performance boost
- space not wasted
- No redundancy, if 1 disk fails all is gone

Raid 1: Mirroring

- Data redundancy on other disk
- Increased read operations
- Slow writing, wait on OK for both disk
- Wasted storage space

Raid 5: Stripe with divided parity

- Can keep running even if 1 drive fails
- Most space with least amount of disks
- Performance boost by striping (RAID 0 with parity*)
- Writing is too slow for high demanding operations (Databases)
- Only 1 disk may fail

Parity is a calculated value thats used to restore data from the other drives if one of the drives in the set fails.
It determines the number of odd and even bits in a number

Raid 10: Mirroring and Stripe

- Minimum 4 drives and the total number must be even
- 

# SAN

Unlike a NAS which is basically a file server, a SAN is like a remote disk which acts to your operating system like a DAS.

Like a clump of NAS in one, easy for backups since it backs them all up at once. Its a separate network.

# File-based storage

You need a path to access it

# Block storage

Chops data into blocks and stores them as separate pieces
Each block is given a unique identifier which allows a storage system to place the smallest pieces of data wherever is most convenient
That means that some thata can be stored in a Linux env and some on a Windows env

Used by SAN, databases email servers RAID VMs and others

# Object storage

Object based storage
- Flat structure in which files are broken into pieces and spread out among hardware
- In object storage, the data is broken into discrete units called objects and is kept in a single repository, instead of being kept as files in folders or as blocks on servers.

Used in cloud storage, Big data, Web apps, backup archives.

