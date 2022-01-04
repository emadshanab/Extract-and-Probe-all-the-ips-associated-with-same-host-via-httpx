
Extract and Probe all the ips associated with same host via httpx:-


httpx -l /root/urls.txt -pa -o urls_ips.txt

Extract the IPS

cat urls_ips.txt | grep -E -o '(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)' >ips.txt


Scan all the ports via httpx.

httpx -l ips.txt -ports - -o ips_ports.txt

Run nuclei.

nuclei -l ips_ports.txt -t nuclei-templates/

Good luck.

Emad Shanab - أبو عبد الله

@Alra3ees
