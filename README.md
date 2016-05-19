# ganesha-munin-plugins
nfs-ganesha plugins for munin

TIP: in ubuntu/GNU-Linux just add the scripts to the /etc/munin/plugins directory and do a 'service munin-node restart'

NOTE: check for problems in /var/log/munin/munin-node.log

NOTE2: if necessary, edit your dbus /etc/dbus-1/system.d/org.ganesha.nfsd.conf configuration file to add permission (\<allow send_destination="org.ganesha.nfsd" send_interface="org.ganesha.nfsd.exportstats"/\>) and restart dbus service (if needed)

NOTE3: if, despite the above, you find errors in munin-node.log like this:
dbus.exceptions.DBusException: org.freedesktop.DBus.Error.AccessDenied: Failed to connect to socket /var/run/dbus/system_bus_socket: Permission denied
check your selinux policy audit.log and allow the connections needed for munin-node to work:
grep -e munin_t -e dbus -e ganesha /var/log/audit/audit.log | audit2allow -M munin-ganesha_stats && semodule -i munin-ganesha_stats.pp
