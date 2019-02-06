1 -  Login to admin01 as a user authorised to make siteadmin changes
2 - Edit the master slurm config files as required:
```
    sudo vim /opt/apps/alces/slurm/slurm.conf
``` 
```
    sudo vim /opt/apps/alces/slurm/gres.conf
```
```
    sudo vim /opt/apps/alces/slurm/topology.conf
```
3a - Sync the new config to a single node
```
  pdsh -w node001 "sudo /opt/service/site/setslurm"
```
3b - Sync the new config to all compute nodes
```
   pdsh -g slurm "sudo /opt/service/site/setslurm"
```

_NB_ The sync process will restart the slurm daemon on the nodes., if config files are not valid - slurmd will fail to start. 
