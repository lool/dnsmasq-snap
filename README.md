This is a quick and dirty snap of dnsmasq!  :-)

Wondering what snaps are? Learn all about them at http://snapcraft.io.

Usage
=====

To install:
`snap install dnsmasqd`

To test the binary, run it in the foreground as a DNS proxy on port 8053:
`/snap/bin/dnsmasqd.dnsmasq -d -p 8053`

Query it with dig:
`dig -p 8053 snapcraft.io @127.0.0.1`

To use the daemon, just put a dnsmasq.conf in `/var/snap/dnsmasq/common/`; it
should start automatically after some seconds.

If you need privileged operations such as to answer BOOTP/DHCP requests, make
sure you connect the network-control interface:
`snap connect dnsmasqd:network-control ubuntu-core:network-control`

To check the output of the daemon, use:
`sudo journalctl -u snap.dnsmasqd.dnsmasqd.service`


Sources and CI
==============

The homepage of this snap is at https://github.com/lool/dnsmasq-snap and it
should be built by Launchpad at https://code.launchpad.net/~lool/+snap/dnsmasqd
based on a mirrored branch of the snap. Because Launchpad didn't allow
pulling sources from random locations, snapcraft.yaml points at a GitHub
copy of the upstream code at https://github.com/lool/dnsmasq.
