## nagios-plugins

Hope to build a collection of useful plugins

### check_disk_hr

The standard disk check plugin works fine, but with larger disks or volumes the
output can be difficult to read in the default MB units.

Yes you can choose units but as size values get truncated, you can get some strange results.
I've seen:

freespace 0 TB (38%)

So the disk is fine, but that '0 TB' looks odd.

This script automatically chooses units to give a human readable output.
It gathers data for the mount point using df.
bc is used to calculate values to 2 decimal places. It is an oddity to use
decimal places in a base 1024 system, but nevertheless gives a good picture
of the situation.
