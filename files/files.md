# Filesystems

HPCS offers two main file storages. A home directory, which is backed up, but  offers only 40GB of storage space and a shared `scratch` directory, which offers 1TB of quota, but no backups. 

> **Info** Always use the `/scratch/ab123` directory as your working directory when running your analysis as it has a faster infini-band connection with the compute nodes.

Summary of available filesystems

|Directory|Explanation|	Backed up|Disk quotas?|	Files removed?|
|---------|-----------|-----------------------|---------------|
|/home/user_name/ | 	User home directory*	|Yes (daily)	|Yes (40GB)	|No
|/scratch/user_name/|  	Scratch user directories*	|No	|Yes (1TB)	|No automatic deletion currently
|/local/  |	Per-node local disk**	|No	|Limited by partition size (33GB or 108GB)	|Deleted after job completion
|/ramdisks/ | 	Per-node tmpfs (in-memory)**	|No	|Limited by physical RAM (3.9GB or 18GB)	|Deleted after job completion
|/usr/local/| Cluster-wide software|	Yes	|N/A (not for user storage)	|N/A (not for user storage)

More information is available [here](http://www.hpc.cam.ac.uk/using-clusters/filesystems)
