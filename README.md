<p align-items="center"><img width="512" height="350" src="http://pluspng.com/img-png/png-hd-magnifying-glass-a-simple-magnifying-glass-2400.png![image](https://user-images.githubusercontent.com/75828293/233865515-b81fc7d2-5404-4eb8-a73d-cde73f9723fa.png)
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

