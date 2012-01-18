
# juju demo

Use this charm to deploy juju local containers onto other providers.
I.e., an LXC container running in either an openstack or ec2 instance.

It also deploys byobu-classroom so you can drive from the console
and people can sit over your shoulder via ajaxterm.

login methods:
  - `juju ssh` read-write using deployment keys
  - `ssh` read-write using ?/?
  - `ssh` readonly using guest/guest
  - `ajaxterm` read-only using guest/guest

There's not much to it... just deploy, then log in.

    $ juju bootstrap
    $ charm get mysql charms/oneiric/mysql
    $ juju deploy --repository ~/charms local:mysql mydb

For charm schools, spread it out and create / hand out passwords
for each instance.
That should be a config option.

TODO:
- put /var/lib/lxc on an 8GB tmpfs partition
- maybe pre-cache lxc and some charm package dependencies?

