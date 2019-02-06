### MOTD Configuration Tool `setmotd`


Your cluster has now been configured with the `setmotd` tool to enable authorised site administrators to configure the MOTD shown on the cluster access nodes.

For reference, the MOTD in use on login nodes is stored at `/opt/flight-direct/etc/motd.d/00-site.txt`

The MOTD will be updated only on the node that it is run on - this allows the MOTD to be different between different nodes. To update the MOTD, create a new MOTD file in a location that can be accessed and run the tool as follows:

```
[siteadmin@admin01 [mycluster] ~]# ssh login1
 -[ alces flight ]-
[root@login1(mycluster) ~]# sudo /opt/service/site/setmotd /tmp/new_motd_login1 
Successfully set new MOTD
```

Once the MOTD has been updated, the tool should respond with "Successfully set new MOTD" if the operation completed successfully. If you experience any issues, contact Alces Flight support.
