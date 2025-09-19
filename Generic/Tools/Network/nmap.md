(Network Mapper) is a powerful open-source tool widely used in network security.

Its main function is to perform network scans to detect the existence of devices on the network, the services they run and open ports.

It is used by cybersecurity experts to find vulnerabilities, map network structures and test security defenses.

Nmap has a command-line based interface and offers a flexible and wide range of scanning options.

``` bash
namp <TARGET>

-sS : It scans the ports of the target machine with TCP SYN packets. 
	nmap -sS <TARGET>
	
-sT : It scans the ports of the target machine with TCP Connect packets. 
	nmap -sT <TARGET>
	
-sV : Detects the versions of services running on the target machine. 
	nmap -sV <TARGET>
	
-A : Aggressive scanning. Performs a comprehensive scan on the target. Performs service version, operating system detection and script scanning. 
	nmap -A <TARGET>
	
-O : It tries to detect the operating system running on the target system. 
	nmap -O <TARGET>
	
-p : Used to scan specific ports or a range of ports. 
	nmap -p 80,443 // Scans ports 80 and 443. 
	nmap -p 1-2000 // Scans ports between 1 and 2000. 
	nmap -p- // Scans all ports (65,536).
```