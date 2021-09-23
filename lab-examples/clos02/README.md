# SRL Containerlab (clos02)

### 5-stage CLOS
https://containerlab.srlinux.dev/lab-examples/min-5clos/

### Execution
```
$ containerlab deploy --topo setup.clos02.clab.yml

$ chmod +x setup.sh
$ ./setup.sh 
```

### Setup Configures
1. NEs with Management, System and Ethernet IP Addresses. 
2. Clients with eth0 (Management) and eth1 interface.
3. NEs and Clients with both IPv4 and IPv6 addresses.
4. NEs with BGP, ISIS & OSPF Network Interface (under default).

### IP Connectivity

| Source      | Interface      | Towards     | IPv4             | IPv4 Prefix | IPv6                   | IPv6 Prefix |
| ----------- | -------------- | ----------- | ---------------- | ----------- | ---------------------- | ----------- |
| leaf1       | mgmt0.0        | -           | `172.100.100.2 ` | 24          | `2001:172:100:100::2 ` | 64          |
|             | system0.0      | -           | `30.0.0.1      ` | 32          | `3000:30:0:0::1      ` | 128         |
|             | ethernet-1/1.0 | spine1      | `10.0.0.0      ` | 31          | `1000:10:0:0::0      ` | 127         |
|             | ethernet-1/2.0 | spine2      | `10.0.0.2      ` | 31          | `1000:10:0:0::2      ` | 127         |
|             | ethernet-1/3.0 | client1     | `10.0.0.24     ` | 31          | `1000:10:0:0::24     ` | 127         |
| leaf2       | mgmt0.0        | -           | `172.100.100.3 ` | 24          | `2001:172:100:100::3 ` | 64          |
|             | system0.0      | -           | `30.0.0.2      ` | 32          | `3000:30:0:0::2      ` | 128         |
|             | ethernet-1/1.0 | spine1      | `10.0.0.4      ` | 31          | `1000:10:0:0::4      ` | 127         |
|             | ethernet-1/2.0 | spine2      | `10.0.0.6      ` | 31          | `1000:10:0:0::6      ` | 127         |
|             | ethernet-1/3.0 | client2     | `10.0.0.26     ` | 31          | `1000:10:0:0::26     ` | 127         |
| leaf3       | mgmt0.0        | -           | `172.100.100.4 ` | 24          | `2001:172:100:100::4 ` | 64          |
|             | system0.0      | -           | `30.0.0.3      ` | 32          | `3000:30:0:0::3      ` | 128         |
|             | ethernet-1/1.0 | spine3      | `10.0.0.12     ` | 31          | `1000:10:0:0::12     ` | 127         |
|             | ethernet-1/2.0 | spine4      | `10.0.0.14     ` | 31          | `1000:10:0:0::14     ` | 127         |
|             | ethernet-1/3.0 | client3     | `10.0.0.28     ` | 31          | `1000:10:0:0::28     ` | 127         |
| leaf4       | mgmt0.0        | -           | `172.100.100.5 ` | 24          | `2001:172:100:100::5 ` | 64          |
|             | system0.0      | -           | `30.0.0.4      ` | 32          | `3000:30:0:0::4      ` | 128         |
|             | ethernet-1/1.0 | spine3      | `10.0.0.16     ` | 31          | `1000:10:0:0::16     ` | 127         |
|             | ethernet-1/2.0 | spine4      | `10.0.0.18     ` | 31          | `1000:10:0:0::18     ` | 127         |
|             | ethernet-1/3.0 | client4     | `10.0.0.30     ` | 31          | `1000:10:0:0::30     ` | 127         |
| spine1      | mgmt0.0        | -           | `172.100.100.6 ` | 24          | `2001:172:100:100::6 ` | 64          |
|             | system0.0      | -           | `30.0.0.5      ` | 32          | `3000:30:0:0::5      ` | 128         |
|             | ethernet-1/1.0 | leaf1       | `10.0.0.1      ` | 31          | `1000:10:0:0::1      ` | 127         |
|             | ethernet-1/2.0 | leaf2       | `10.0.0.5      ` | 31          | `1000:10:0:0::5      ` | 127         |
|             | ethernet-1/3.0 | superspine1 | `10.0.0.8      ` | 31          | `1000:10:0:0::8      ` | 127         |
| spine2      | mgmt0.0        | -           | `172.100.100.7 ` | 24          | `2001:172:100:100::7 ` | 64          |
|             | system0.0      | -           | `30.0.0.6      ` | 32          | `3000:30:0:0::6      ` | 128         |
|             | ethernet-1/1.0 | leaf1       | `10.0.0.3      ` | 31          | `1000:10:0:0::3      ` | 127         |
|             | ethernet-1/2.0 | leaf2       | `10.0.0.7      ` | 31          | `1000:10:0:0::7      ` | 127         |
|             | ethernet-1/3.0 | superspine2 | `10.0.0.10     ` | 31          | `1000:10:0:0::10     ` | 127         |
| spine3      | mgmt0.0        | -           | `172.100.100.8 ` | 24          | `2001:172:100:100::8 ` | 64          |
|             | system0.0      | -           | `30.0.0.7      ` | 32          | `3000:30:0:0::7      ` | 128         |
|             | ethernet-1/1.0 | leaf3       | `10.0.0.13     ` | 31          | `1000:10:0:0::13     ` | 127         |
|             | ethernet-1/2.0 | leaf4       | `10.0.0.17     ` | 31          | `1000:10:0:0::17     ` | 127         |
|             | ethernet-1/3.0 | superspine1 | `10.0.0.20     ` | 31          | `1000:10:0:0::20     ` | 127         |
| spine4      | mgmt0.0        | -           | `172.100.100.9 ` | 24          | `2001:172:100:100::9 ` | 64          |
|             | system0.0      | -           | `30.0.0.8      ` | 32          | `3000:30:0:0::8      ` | 128         |
|             | ethernet-1/1.0 | leaf3       | `10.0.0.15     ` | 31          | `1000:10:0:0::15     ` | 127         |
|             | ethernet-1/2.0 | leaf4       | `10.0.0.19     ` | 31          | `1000:10:0:0::19     ` | 127         |
|             | ethernet-1/3.0 | superspine2 | `10.0.0.22     ` | 31          | `1000:10:0:0::22     ` | 127         |
| superspine1 | mgmt0.0        | -           | `172.100.100.10` | 24          | `2001:172:100:100::10` | 64          |
|             | system0.0      | -           | `30.0.0.9      ` | 32          | `3000:30:0:0::9      ` | 128         |
|             | ethernet-1/1.0 | spine1      | `10.0.0.9      ` | 31          | `1000:10:0:0::9      ` | 127         |
|             | ethernet-1/2.0 | spine3      | `10.0.0.21     ` | 31          | `1000:10:0:0::21     ` | 127         |
| superspine2 | mgmt0.0        | -           | `172.100.100.11` | 24          | `2001:172:100:100::11` | 64          |
|             | system0.0      | -           | `30.0.0.10     ` | 32          | `3000:30:0:0::10     ` | 128         |
|             | ethernet-1/1.0 | spine2      | `10.0.0.11     ` | 31          | `1000:10:0:0::11     ` | 127         |
|             | ethernet-1/2.0 | spine4      | `10.0.0.23     ` | 31          | `1000:10:0:0::23     ` | 127         |
| client1     | eth0           | -           | `172.100.100.12` | 24          | `2001:172:100:100::12` | 64          |
|             | eth1           | leaf1       | `10.0.0.25     ` | 31          | `1000:10:0:0::25     ` | 127         |
| client2     | eth0           | -           | `172.100.100.13` | 24          | `2001:172:100:100::13` | 64          |
|             | eth1           | leaf2       | `10.0.0.27     ` | 31          | `1000:10:0:0::27     ` | 127         |
| client3     | eth0           | -           | `172.100.100.14` | 24          | `2001:172:100:100::14` | 64          |
|             | eth1           | leaf3       | `10.0.0.29     ` | 31          | `1000:10:0:0::29     ` | 127         |
| client4     | eth0           | -           | `172.100.100.15` | 24          | `2001:172:100:100::15` | 64          |
|             | eth1           | leaf4       | `10.0.0.31     ` | 31          | `1000:10:0:0::31     ` | 127         |