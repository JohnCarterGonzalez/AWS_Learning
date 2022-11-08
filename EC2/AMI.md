AMI Overview 
  Amazon Machine Image
  AMI are a customization of an EC2 Instance 
    - you add yoiur own software, config, OS, monitoring
    - faster boot/config time b/c all your software is prepackaged 
  AMIs are buitl for a specific region ( can be copied across regions )
  You can launch EC2 instances from: 
    - public AMIS: aws provided 
    - your own AMI: you make and maintain them yourself 
    - an AWS marketplace AMI: an AMI someone else made 
  AMI Process 
    - start an EC2 instance and customize it 
    - stop the instance ( for data integrity )
    - build an AMI - this will also create EBS snapshots 
    - launch instances from other AMI's 
  EC2 Instance Storage
    - EBS VOlumes are network drives w/limited performance 
    - if you need a high-performance, use EC2 instance store 
    - better  i/o performance
    - EC2 instance store lose their Storage if they're stoppped 
    - good for buffer/cache/scratch data/temp content
    - risk of data loss if hardware fails
    - backups and replication are your responsibility
  EBS Volume Types 
    - 6 Types:
      > gp2/gp3 (ssd): gen purpose SSD volume that balances price and performance
                       for a wide variety of workloads, can be used for boot, 
                       cost effective, low latency
                         -> gp3: can increase IOPS and throughput independently
                         -> gp2: IOPS and throughput are linked 
      > io/io2 (ssd): highest performance SSD for mission critical, low-latency
                      or high throuhgput workloads, can be used for boot, on 
                      apps that need more than 16,000 IOPS, great for DB workloads
                         -> io1/io2: max PIOPS ( Provisioned IOPS ) 64000 for 
                                     nitro EC2 & 32000 for other instances
                                     can increase PIOPS independently from storage 
                                     size, io2 has more durability and more IOPS
                                     per GiB (same price as io1)
                         -> io2: Block Express ( 4 GiB - 64 TiB ): sub milisecond latency
                                 max PIOPS 256000 w/ an IOPS:GiB ratio of 1000:1
                                 supports EBS Multi Attach
      > st1 (hdd): low cost HDD designed for frequently accessd, throughput 
                    intensive workloads, great for big data, data warehouses  
      > sc1 (hdd): lowest cost HDD designed for less frequently accessed workloads
                    perfect for low cost designs

    - EBS Volumes are characterized in size | throughput | IOPS ( I/O OPs per sec )
    - when in doubt consult AWS dox
  EBS Multi Attach
    - io1/io2 family
    - Attach the same EBS Volume to mutiple EC2 instances in the same AZ
    - each instance has full read & write permissions to the high performance
      volume 
    - use cases:
        achieve higher application availablity in clusterd linux applications 
        apps must manage concurrent write operations 
    - IMPORTANT: up to 16 EC2 Instances at one time 
                 must use a file system that is cluster aware
