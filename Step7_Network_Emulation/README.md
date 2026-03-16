# Step 7 - Network Artifact Emulation Using Linux Traffic Control

This step demonstrates three different traffic‑control mechanisms to emulate network artifacts between the VM Server (Prometheus) and VM Client. All configurations were applied using Linux  and verified with screenshots

## 1 Token Bucket Filter (TBF) – Server Egress

A Token Bucket Filter (TBF) was applied on the Prometheus VM to limit outgoing traffic with the following characteristics:
• 	Rate: 2.5 Mbps
• 	Burst: 20 KB
• 	Latency: 50 ms
## Commands used
sudo tc qdisc del dev enp0s3 root

sudo tc qdisc add dev enp0s3 root tbf rate 2.5mbit burst 20kb latency 50ms

tc qdisc show dev enp0s3

Screenshot 1 shows the TBF configuration applied to the server

---

## 2 Hierarchical Token Bucket (HTB) – Server Egress
HTB was configured on the Prometheus VM to guarantee a minimum bandwidth while allowing a higher maximum bandwidth when available.
• 	Guaranteed minimum: 2.5 Mbps
• 	Maximum bandwidth: 5 Mbps
• 	Burst: 20 KB
## Commands used
sudo tc qdisc del dev enp0s3 root

sudo tc qdisc add dev enp0s3 root handle 1: htb default 10

sudo tc class add dev enp0s3 parent 1: classid 1:1 htb rate 5mbit ceil 5mbit

sudo tc class add dev enp0s3 parent 1:1 classid 1:10 htb rate 2.5mbit ceil 5mbit burst 20kb

tc qdisc show dev enp0s3

tc class show dev enp0s3

Screenshot 2 shows the HTB hierarchy and class configuration

---

## 3 Traffic Policing – Client Ingress
Traffic policing was applied on the Client VM to drop incoming traffic that exceeds 3.5 Mbps, simulating congestion control at the receiver.
## Commands used
sudo tc qdisc del dev enp0s3 ingress

sudo tc qdisc add dev enp0s3 handle ffff: ingress

sudo tc filter add dev enp0s3 parent ffff: protocol ip prio 1 u32 match ip src 0.0.0.0/0 police rate 3.5mbit burst 20kb drop flowid :1

tc qdisc show dev enp0s3

tc filter show dev enp0s3 parent ffff:

Screenshot 3 shows the ingress policing rule with the drop action.

---

## Result
All three network‑emulation scenarios were successfully implemented:
• 	TBF limiting bandwidth and latency on server egress
• 	HTB guaranteeing and capping bandwidth on server egress
• 	Policing dropping excessive traffic on client ingress
This completes Step 7.
