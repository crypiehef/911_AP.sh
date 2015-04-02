# 911_AP.sh
Update to Em3rgency's awesome Fake AP script he made for Backtrack. Now updated for Kali. Should work also with ISC_DHCP_Server instead of just DHCP3


You just install the prerequistes and chmod 775 911_AP.sh. You can run the script from any directory on your PC. You can even place it inside /usr/bin and just type 911_AP in terminal and it will be part of your system!!

You Have to ALSO CHANGE /etc/default/dhcp3-server!!!!!!
put “at0″ and save

It should be fully functional. The script has everything you need on a fresh install of BT5r3 to make it compatible and ready to run.

1. Prerequsites and Updates
2. Run FAKE AP Static
3. Run EVIL TWIN AP
4. Run Standard ARP poison
5. Netdiscover connected clients
6. EXIT

It will not work with ISC_DHCP_SERVER. You will need to do the following. (Should work. Try it first with ISC)

THIS IS FOR any other OS besides BT5
apt-get purge dhcp3-server
apt-get purge dhcp3-common

You will need to use this version of DHCP3 server (might not need to anymore. Should work with ISC. Let me know.)
http://www.mediafire.com/?oxgkgdio8ndjq5l
http://www.mediafire.com/?p3g4maize6p60dy

tar xzvf <FILENAME>
tar xzvf <FILENAME>

Enjoy!!! you can seriously pwn anyone on a network with this script. IT is fast!!! and reliable, I have had my FAKE_AP running for days without a crash!!!

THANKS,

TO GET THE ARP POISONING TO WORK CORRECTLY YOU HAVE TO

make sure you commented out your etter.conf file so you dont have the # sign in front of the lines that say

Open terminal and type

gedit /etc/etter.conf ——–> When done editing these lines save the file

#If you are using IP tables, Like below

# if you use iptables:
#redir_command_on = “iptables -t nat -A PREROUTING -i %iface -p tcp –dport %port -j REDIRECT %rport”
#redir_command_off = “iptables -t nat -D PREROUTING -i %iface -p tcp –dport %port -j REDIRECT %rport”
to this “Just remove the # signs from the front of each line”

# if you use iptables:
redir_command_on = “iptables -t nat -A PREROUTING -i %iface -p tcp –dport %port -j REDIRECT %rport”
redir_command_off = “iptables -t nat -D PREROUTING -i %iface -p tcp –dport %port -j REDIRECT %rport”
And also edit these lines to look like this

[privs]
ec_uid = 65534 # nobody is the default
ec_gid = 65534 # nobody is the default

Change the 65534 to 0′s in each of the 2 lines..

[privs]
ec_uid = 0 # nobody is the default
ec_gid = 0 # nobody is the default

AND ENJOY YOUR WIRELESS PWNING!!!
