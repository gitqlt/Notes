tcpdump: Command-line packet analyzer
====
### capture all TCP/IP traffic to and from a specific host (-v or -V not needed)
    $ tcpdump -i <interface> -s 0     host <target_host> -w <output_file.pcap>
    $ tcpdump -i <interface> -s 0 src host <target_host> -w <output_file.pcap>
    $ tcpdump -i <interface> -s 0 dst host <target_host> -w <output_file.pcap>

      
### Analyze
                          $ tcpdump -vv -r traffic.pcap host 192.168.1.100
    Content in ASCII:     $ tcpdump -A -r traffic.pcap port 80
    Content in ASCII+HEX: $ tcpdump -X -r traffic.pcap host 192.168.1.100
    First 10 packets:     $ tcpdump -c 10 ...
    Save filtered         $ tcpdump -r traffic.pcap -w filtered.pcap host 192.168.1.100
    Wireshark:            $ wireshark traffic.pcap &
