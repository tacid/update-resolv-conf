Script to update resolv.conf
============================

This is shell sctipt to add/delete listed in command line IPs
to /etc/resolv.conf

Normaly this script is used in openvpn config to add DNS servers
to head of current resolv.conf

Common usage, add to your openvpn config:

    script-security 2
    up "/full/path/to/update-resolv-conf 1.1.1.1 2.2.2.2 3.3.3.3"
    down "/bin/sudo /full/path/to/update-resolv-conf -d 1.1.1.1 2.2.2.2 3.3.3.3"

Maybe you also should allow user of openvpn daemon to run script without password.
For this you can add following to sudoers:

    nobody ALL=NOPASSWD: /full/path/to/update-resolv-conf
