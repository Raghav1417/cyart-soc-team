## Response and Containment

The attacker IP address was blocked using CrowdSec:

Command:
sudo cscli decisions add --ip 192.168.56.102 --type ban

Verification:
The decision was successfully added and listed using:
sudo cscli decisions list

This confirms that the attacker was blocked.
