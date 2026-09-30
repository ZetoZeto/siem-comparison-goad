# Suricata (network IDS)

Suricata is the network intrusion detection engine that gives Wazuh and ElasticSearch their network visibility. It inspects traffic and raises signatures for events such as port scans, which is why those two collectors surface network-based attacks while OpenWEC (host events only, no Suricata) does not.

In this lab Suricata is integrated with the ElasticSearch SIEM stack and feeds Wazuh, so that:

- Nmap scans are detected and reported (see [attacks.md](attacks.md), section 2)
- Network anomalies are correlated with host events for a fuller picture

This is the key reason OpenWEC scored lower for detection breadth: without a network IDS component it only reports host-level Windows events (process creation, logon events), and misses scans and denial-of-service traffic.
