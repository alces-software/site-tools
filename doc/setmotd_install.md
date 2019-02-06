### MOTD Configuration Tool `setmotd` Installation

This script should work on most modern Alces Flight clusters that have a Site Administrator sudo rule configured within IPA. To enable this script:

1. Copy the script into the appropriate Tools directory (usually `/opt/service/site`).
2. Modify the path to $MOTDFILE, which is the MOTD file in use on the cluster
3. Modify the path to $LOG, for logs of when the script is executed.
4. Set the script to be owned by `root:root` with permissions set to `700`.
5. Add the script to the sudo rule within IPA to allow site administrators to run the script
 - `ipa sudocmd-add “/opt/service/site/setmotd”`
 - `ipa sudorule-add-allow-command –sudocmds “/opt/service/site/setmotd” SiteCommands`
6. Check the tool is runnable via sudo as the `siteadmin` user.
7. Add the `setmotd.md` documentation to the Alces Flight Center documentation for the cluster and provide the Site Administrators with a link to this documentation after installation.
