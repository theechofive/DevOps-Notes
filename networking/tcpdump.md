# tcpdump Notes

## 📡 Live capture and simultaneous read
Capture packets, save them to a file, and analyze in real-time:

```
tcpdump -w - -U | tee somefile.pcap | tcpdump -r -
```
Explanation:
- -w - → write raw packet data to stdout
- -U → write packets as they arrive (unbuffered)
- tee somefile.pcap → save packets to somefile.pcap and pass them to stdout
- -r - → read packets from stdin (in this case, the output of tee)

👉 This way you both record traffic to a file and see it live at the same time.


## 🌐 Capture on a specific interface

```
tcpdump -i eth0
```

## 🎯 Capture traffic on a specific port

```
tcpdump -i eth0 port 80
```

## 🎯 Capture traffic from/to a specific host

```
tcpdump -i eth0 host 192.168.1.10
```

## 🎯 Capture traffic for specific protocol

```
tcpdump -i eth0 tcp
tcpdump -i eth0 udp
tcpdump -i eth0 icmp
```

## 💾 Save capture to a file

```
tcpdump -i eth0 -w capture.pcap
```

## 📖 Read packets from a file

```
tcpdump -r capture.pcap
```