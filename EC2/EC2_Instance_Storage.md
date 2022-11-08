EBS Overview 
  EBS Volume - Elastic Block Volume is a network drive you can attach 
                to your instances while they run
                network drive, uses the network to cimmunicate the instance (latency)
                it can be detached from an EC2 INstance and atatched to another one 

  it allows your instances to persist data, even after termination
  they can only be moiunted to one istance at a time (CCP level)
  there is a "multi attach feature"
    to move the volume over region, you need to snapshot it 
  they are bound to a specific availablity zone (AZ)

  analogy: think of them like a network "usb" stick 
  example: preserve the root volume of an instance when it is terminated 
EBS snapshots
  make a backup of your EBS Volume at a point in time 
  not necessary to detah volume to do snapshot, but recommended 
  can copy the snapshots across AZ or Region 
  EBS Snapshot features 
    archive 
      - move a snapshot to an archive tier that is 75% cheaper 
      - takes 24 to 72 hours to restore the archive 
    recycle bin
      - setup rules to retain deleted snapshots so you can recover them after an accidental
        deletion
      - specifiy retention
    fast snapshot restore 
      - force full init of snapshot to have no latency on the first uses
      - big money problems 
