# YoloCompute
Yolo Cloud Computing Platform™

## Add a new VM
1. Add a new entry to the boxes section at `host_vars/compute`
2. Run `./deploy --tags boxes`

ProTip™: There are online MAC address generators, e.g. [this one](https://justynshull.com/macgen/macgen.php).

## Accessing remote desktop™
1. Get a [spice](http://www.spice-space.org/) client. Your favorite Linux distribution probably has one in it's repositories
2. Run `virsh domdisplay [boxname]` on the VM host
3. Dig an SSH tunnel onto the spice port using `ssh -L [port]:localhost:[port] [user]@[host]`
4. Start spicy or whatever your favorite client is: `spicy`

## Deploy all changes onto the VM host(s)
1. Get a local copy on your laptop/toaster/whatever using `git clone`
2. Run `./deploy` and watch it burn.

The deploy script takes care of downloading requirements from the [Ansible Galaxy](https://galaxy.ansible.com/) and adds some reasonable default options.

You can add arbitrary arguments to the `./deploy` script which all get passed to `ansible-playbook`. See next section

## Adding a new VM host
1. Add it to the `inventory` file
2. Run `./deploy`

Basic requirement is a running Debian installation. Eventually you might want to run the mdadm/lvm stuff separated.

