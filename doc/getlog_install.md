### Log Viewing Tool `getlogs` Installation Guide

The cluster that requires this tool to be installed on must be a modern Alces Flight cluster using an IPA Directory server with a site admin sudo rule configured. 

Copy the script to the appropriate directory on the cluster for Alces Flight Center Tools - on most modern clusters this will be at `/opt/service/site`. Ensure that the configuration directory is available (usually `/opt/service/site/etc`) and copy in the `available_logs` file and modify the script to reflect this location.

Once these two files are in place, ensure they are both owned by `root:root`, with `getlog` set to `700` and `available_logs` set to `744`.

Add the script to the sudo rule within IPA that allows site administrators to run the script:

 - `ipa sudocmd-add “/opt/service/site/getlogs”`
 - `ipa sudorule-add-allow-command –sudocmds “/opt/service/site/getlogs” SiteCommands`

To add additional log files to be available to be viewed by site administrators, modify the `available_logs` file and add the log file allowed to be viewed to the array. Confirm that the log can then be viewed by the `siteadmin` user.

Once the script has been installed, add the `getlog.md` documentation to the Alces Flight Center documentation for the cluster and provide the Site Administrators with a link to this documentation after installation.
