# ganesha-munin-plugins
nfs-ganesha plugins for munin

TIP: in ubuntu/GNU-Linux just add the scripts to the /etc/munin/plugins directory and do a 'service munin-node restart'

NOTE: check for problems in /var/log/munin/munin-node.log
NOTE2: if necessary, edit your dbus /etc/dbus-1/system.d/org.ganesha.nfsd.conf configuration file to add permission (\<allow send_destination="org.ganesha.nfsd" send_interface="org.ganesha.nfsd.exportstats"/\>) and restart dbus service
