The process killer tool is now available on your cluster for site admins to be able to kill user processes that are problematic. 

The tool requires the same parameters as the Linux `kill` or `pkill` command, these are:

`-n` - The signal to be sent to the process.
with either
`-p` - The PID to send the signal to.
OR
`-u` - Any processes on a system owned by this user to be sent a signal.

Only one of `-p` or `-u` are to be used at one time. Using the `-u` functionality will kill all processes for that user on the system, this is equivalent to the `pkill -u` command. Usage of the `-p` switch will allow one PID to be sent a signal.  An example of usage is as follows:

To kill all processes owned by a particular user on a node:

```
[siteadmin@login1 [mycluster1] ~]$ sudo /opt/service/site/killproc -u user1234 -n 9
Now running pkill -9 -u user1234
```

To kill a single process on a node:

```
[siteadmin@login1 [mycluster1] ~]$ sudo /opt/service/site/killproc -p 3879 -n 9
Found the PID 3879 from looking at ps
Found the User that owns this process is user1234 from looking at ps
The UID of the user user1234 from ps is 1433200099
Everything checks out OK before killing this process, suspect it's probably a non-critical user
Now attempting to kill it...
Running kill -9 3879
```

If there are any issues running this command on your cluster, please contact Alces Flight support.
