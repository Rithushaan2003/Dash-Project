# Step 6 – iPerf TCP Connection with Traffic Prioritisation

## 1. Establishing a 1 Mbps TCP iPerf Connection

An iPerf3 TCP connection was created from the Client VM (192.168.0.202) to the Prometheus VM (192.168.0.252) using a bandwidth limit of 1 Mbps:
iperf3 -c 192.168.0.252 -b 1M -t 20


Screenshot 2 shows the successful 1 Mbps TCP connection.

---

## 2. Assigning Higher Priority to the iPerf Connection

Traffic control (tc) was configured on the Prometheus VM to give iPerf traffic (TCP port 5201) higher priority than other traffic such as video streams.

Commands used:
sudo tc qdisc add dev enp0s3 root handle 1: htb default 12 sudo tc class add dev enp0s3 parent 1: classid 1:1 htb rate 10mbit sudo tc class add dev enp0s3 parent 1:1 classid 1:10 htb rate 2mbit prio 0 sudo tc class add dev enp0s3 parent 1:1 classid 1:12 htb rate 1mbit prio 1 sudo tc filter add dev enp0s3 protocol ip parent 1:0 prio 1 u32 match ip dport 5201 0xffff flowid 1:10

Screenshot 3 shows the qdisc and class configuration confirming that iPerf traffic is assigned to the high‑priority class (1:10).

---

## 3. Result

- The iPerf TCP connection runs at 1 Mbps.
- It is assigned a higher priority than video traffic.
- Both requirements of Step 6 are fully met.
