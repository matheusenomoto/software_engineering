# RAID - Redundant Array of Independent Disks

RAID, or , is a technology that combines multiple hard drives (HDDs or SSDs) to function as a single logical unit. The goal is to achieve one or more of the following benefits:

1.Redundancy: Protect data against the failure of one or more disks. If one disk fails, the system continues to function and the data can be recovered.
2.Performance: Increase read and write speed by distributing operations across multiple disks.
3.Capacity: Combine the storage space of multiple disks into a single, larger volume.

RAID is not a backup. RAID protects against hardware failure (a disk stopping), but it does not protect against accidental file deletion, data corruption by software, ransomware attacks, or physical disasters (fire, theft). A proper backup policy is still essential.

## fundamental

Striping: Data is split into blocks and sequentially distributed across the disks in the array. This drastically improves performance, as multiple disks can read and write different parts of the same file simultaneously.

Mirroring: Data is fully duplicated across two or more disks. Everything written to one disk is immediately written to the other. This provides excellent redundancy but “cuts in half” the total usable storage capacity.

Parity: A more space-efficient data protection technique. Parity consists of error-checking bits calculated from the original data blocks. If a disk fails, the system can use the data from the remaining disks plus the parity information to reconstruct the lost data.

## Standard RAID Levels

**RAID 0 (Striping)**

<img width="238" height="391" alt="raid_0" src="https://github.com/user-attachments/assets/22509e66-5116-42f4-bd12-8f69ca949815" />

How it works: Uses only the striping technique. Data is split and distributed across all disks.

Minimum disks: 2.

Advantages:
* Exceptional performance: Fastest RAID level for read/write, as all disks work in parallel.
* 100% capacity usage: Total capacity equals the sum of all disks.

Disadvantages:
* Zero redundancy: If any disk fails, all data is lost. The chance of failure increases with each added disk.

Use case: Video editing, temporary file caching, or applications needing extreme speed where data loss is not catastrophic.

**RAID 1 (Mirroring)**

<img width="238" height="388" alt="raid_1" src="https://github.com/user-attachments/assets/10f10396-c88c-4894-9b59-aa5d28d989a1" />

How it works: Uses only mirroring. Data is fully duplicated across each disk in the pair.

Minimum disks: 2.

Advantages:
* High redundancy: The system can survive the failure of one disk (in a 2-disk pair) with no data loss.
* Good read speed: Reading can be done from both disks simultaneously, almost doubling speed in some controllers.

Disadvantages:
* Low capacity efficiency: Usable capacity equals the smallest disk in the array (50% efficiency in a 2-disk pair).
* Write speed: Limited to the slowest disk since data must be written to both.

Use case: Small file servers, server OS disks, small databases, and applications where data protection is top priority.

**RAID 5 (Striping with Distributed Parity)**

<img width="497" height="394" alt="raid_5" src="https://github.com/user-attachments/assets/7e05364b-40b2-440b-ad22-f849c58f9661" />

How it works: Uses striping for data and distributes parity blocks across all disks.

Minimum disks: 3.

Advantages:
* Balanced: Good compromise between performance, capacity, and redundancy.
* Good capacity efficiency: Only the equivalent of one disk is lost to parity. (e.g., 4 × 1TB = 3TB usable).
* Good read speed: Reads are distributed across multiple disks.

Disadvantages:
* Write penalty: Writes are slower since the system must read old data, read old parity, calculate new parity, then write both new data and parity.
* Rebuild vulnerability: If a disk fails, the array becomes “degraded.” During rebuild (hours or days), if another disk fails, all data is lost.

Use case: File servers and general-purpose storage where cost, performance, and safety must be balanced.

**RAID 6 (Striping with Dual Parity)**

<img width="628" height="395" alt="raid_6" src="https://github.com/user-attachments/assets/cef73bd9-47fd-44ad-8efd-180763b859b0" />

How it works: Similar to RAID 5, but calculates and distributes two independent parity blocks for each data stripe.

Minimum disks: 4.

Advantages:
* Very high redundancy: Can survive the failure of up to two disks simultaneously, making it safer than RAID 5, especially for large arrays.

Disadvantages:
* Higher write penalty: Dual parity calculation makes writes slower than RAID 5.
* Lower capacity efficiency: The equivalent of two disks is lost to parity.

Use case: Large storage servers, data archiving, and mission-critical applications where downtime or double-disk failure risk is unacceptable.

## Nested (Hybrid) RAID Levels

These levels combine two or more standard RAID levels to get the best of both worlds.

**RAID 10 (or RAID 1+0)**

<img width="498" height="507" alt="raid_10" src="https://github.com/user-attachments/assets/9f73d692-f87f-4012-84c9-1af005c38045" />

How it works: A stripe of mirrors. First, disks are grouped in RAID 1 pairs (mirroring). Then data is striped across these pairs.

Minimum disks: 4 (in pairs of 2).

Advantages:
* Excellent performance and redundancy: Combines RAID 0 speed with RAID 1 safety. Write operations are very fast since no parity calculations are needed.
* Fast rebuilds: If one disk fails, only its mirrored partner needs to be copied—much faster than rebuilding from parity.

Disadvantages:
* High cost / low efficiency: Like RAID 1, only 50% of total disk capacity is usable.

Use case: High-performance databases, application servers, and environments requiring high write performance with fault tolerance.

**RAID 50 (or RAID 5+0)**

<img width="1110" height="473" alt="raid_50" src="https://github.com/user-attachments/assets/80a6db4b-17da-42a9-b204-7aa53b0c811a" />

How it works: A stripe of RAID 5 arrays. Multiple RAID 5 groups are created, and data is striped across them.

Minimum disks: 6.

Advantages:
* Better write performance than a single large RAID 5.
* Higher fault tolerance than RAID 5 (can survive multiple failures if they’re in different subgroups).

Disadvantages:
* Higher cost and complexity.

Use case: Applications needing better performance and safety than RAID 5 but at lower cost than RAID 10.

## Hardware RAID vs. Software RAID

RAID can be implemented in two main ways:

**Hardware RAID**

What it is: A dedicated RAID controller card (PCI-Express) manages the disk array independently of the OS.

Pros:
* Superior performance: Has its own processor (ROC – RAID-on-Chip) and often dedicated cache memory (with BBU – Battery Backup Unit for power loss protection).
* OS-independent: The OS sees only one disk, simplifying management.
* Advanced features: Usually more configuration and monitoring options.

Cons:
* Cost: Controller cards can be expensive.
* Vendor lock-in: If the controller fails, you usually need an identical or compatible model from the same vendor to recover the array.

**Software RAID**

What it is: The operating system (Windows, Linux, macOS) or a dedicated program manages the RAID array using system CPU and RAM.

Pros:
* Low or no cost: Included in most modern OSs.
* Flexibility: Not tied to specific hardware. You can move disks to another machine (with the same OS) and reactivate the array.

Cons:
* Resource usage: Consumes CPU cycles and system RAM, which may impact overall performance, especially for parity arrays (RAID 5/6).
* OS dependency: The array depends on the OS. Boot or OS failures may affect RAID access.

| Priority | Recommended RAID Level |
| :------:| :---------------------: |
| maximum performance (non-critical data) | RAID 0 |
| maximum data protection (cost not an issue) | RAID 1 or 10 |
| balance (general use, file servers) | RAID 5 |
| advanced protection (large volumes, critival data)  | RAID 6 |
| high performance + high protection | RAID 10 |
