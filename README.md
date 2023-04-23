<p align-items="center"><img width="512" height="350" src="https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fcdn0.iconfinder.com%2Fdata%2Ficons%2Fit-components%2F24%2Fethernet_plug_network_port_2-512.png&f=1&nofb=1&ipt=1cc0d589eae1256d4c0e9fd4fb2ffb0b7da16ca3b9def582180d006679718f1f&ipo=images
"></p>




Sneaf-X
------
Sneaf-X is an Advanced Network traffic sniffer

### Aim
Proof of concept of detecting Network traffic. Could be used for the improvement of the network security. Or, for the censorship against Sneaf-X. Either way, it is better to expose the vulnerabilities in advance and take the initiative.

### Usage
```
# install libpcap first, then
pip install -r requirements.txt
sudo ./sneafx.py
```
Finally, browse the web via your favourable proxy/proxies. When the script detects more than 15 suspicious connections to/from one source, it will flag it to be a vulnerable server and print to the terminal.

### Method
Sneaf-X is famous for its randomness feature; however, the first packet of a connection is usually not expected to be random. Even in a TLS session, we expect to see some plaintext sections in the handshake stage. Therefore, one can detect insecure Network traffic by simply looking at the first few packets and calculating their entropy (as a measure of randomness). Together with some minor adjustments, this method suffices to detect the current ShadowSocks protocol at a high accuracy.

### TODO
* Develop a more general method to detect proxy traffic.
* Test for false-positive results.

### Credits
* [scapy](http://www.secdev.org/projects/scapy/) for packet sniffing/manipulation
* [dpkt](https://github.com/kbandla/dpkt) for packet parsing/creation
