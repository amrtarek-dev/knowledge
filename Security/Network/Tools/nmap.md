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


## Scan network

Scan network hosts:
Nmap offers the `-sn` option, i.e., ping scan. However, don’t expect this to be limited like `ping`.

``` shell
nmap -sn 192.168.66.0/24
```
This will report the live hosts in the subnet 1-255 that responded to the ping (ICMP) request.
You can use `-PS[portlist]`, `-PA[portlist]`, `-PU[portlist]` for TCP SYN, TCP ACK, and UDP discovery via the given ports.

You can check the list that nmap will scan it (without scanning) by `-sL` option.

### TCP ports
`-sT` Scan network port hosts by Sync-Ack (complete TCP handshake)
``` shell
nmap -sT 192.168.124.148
```

`-sS` Scan network port Stealth (Only first SYN in TCP handshake)
``` shell
nmap -sS 192.168.124.148
```


### UDP ports
``` shell
nmap -sU 192.168.124.148
```


### Limit the ports `-p`
Rather than scanning all TCP and UDP ports (common 1000 ports) you can use:
- `-F` for fast, Only 100 most common
- `-p[range]`, for a range of ports `-p10-200`, or -p-25 which from 1 to 25 or all ports `-p-` which will be from 1 to 65535

### Version and service `-sV`
``` shell
nmap -sU -sV 192.168.124.148
```

### OS detection
the OS detection option triggers Nmap to rely on various indicators to make an educated guess about the target OS
``` shell
nmap -sU -O 192.168.124.148
```


### OS and Version `-A`
``` shell
nmap -sU -A 192.168.124.148
```

### Forcing scan `-Pn`
When we run our port scan, such as using `-sS`, there is a possibility that the target host does not reply during the host discovery phase (e.g. a host doesn’t reply to ICMP requests). Consequently, Nmap will mark this host as down and won’t launch a port scan against it. We can ask Nmap to treat all hosts as online and port scan every host, including those that didn’t respond during the host discovery phase. This choice can be triggered by adding the `-Pn` option.

``` shell
nmap -Pn -A 192.168.124.148
```


## Timing
Nmap gives you six timing templates, and the names say it all: paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5). 

You can pick the timing template by its name or number. For example, you can add `-T0` (or `-T 0`) or `-T paranoid` to opt for the slowest timing.

| Timing          | Total Duration |
| --------------- | -------------- |
| T0 (paranoid)   | 9.8 hours      |
| T1 (sneaky)     | 27.53 minutes  |
| T2 (polite)     | 40.56 seconds  |
| T3 (normal)     | 0.15 seconds   |
| T4 (aggressive) | 0.13 seconds   |
- The number of parallel probes can be controlled with `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>`.
- A similar helpful option is the `--min-rate <number>` and `--max-rate <number>`
- `--host-timeout <time>`. This option specifies the maximum time you are willing to wait, and it is suitable for slow hosts or hosts with slow network connections.

| Option                                                              | Explanation                                                                                        |
| ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `-T<0-5>`                                                           | Timing template – paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5) |
| `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>` | Minimum and maximum number of parallel probes                                                      |
| `--min-rate <number>` and `--max-rate <number>`                     | Minimum and maximum rate (packets/second)                                                          |
| `--host-timeout`                                                    | Maximum amount of time to wait for a target host                                                   |

## Saving scan
Nmap gives us various formats. The three most useful are normal (human-friendly) output, XML output, and grepable output, in reference to the `grep` command. You can select the scan report format as follows:

- `-oN <filename>` - Normal output
- `-oX <filename>` - XML output
- `-oG <filename>` - `grep`-able output (useful for `grep` and `awk`)
- `-oA <basename>` - Output in all major formats

## Verbose and Debug
`-v` or `-vv`/`-v2` or `-vvv`/`-v3`, or `-vvvv`/`-v4`
or pressing v key while scanning

and the debugging from `-d` to level 9 `-d9`


| Option                                                              | Explanation                                                                                        |
| ------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `-sL`                                                               | List scan – list targets without scanning                                                          |
| **_Host Discovery_**                                                |                                                                                                    |
| `-sn`                                                               | Ping scan – host discovery only                                                                    |
| **_Port Scanning_**                                                 |                                                                                                    |
| `-sT`                                                               | TCP connect scan – complete three-way handshake                                                    |
| `-sS`                                                               | TCP SYN – only first step of the three-way handshake                                               |
| `-sU`                                                               | UDP Scan                                                                                           |
| `-F`                                                                | Fast mode – scans the 100 most common ports                                                        |
| `-p[range]`                                                         | Specifies a range of port numbers – `-p-` scans all the ports                                      |
| `-Pn`                                                               | Treat all hosts as online – scan hosts that appear to be down                                      |
| **_Service Detection_**                                             |                                                                                                    |
| `-O`                                                                | OS detection                                                                                       |
| `-sV`                                                               | Service version detection                                                                          |
| `-A`                                                                | OS detection, version detection, and other additions                                               |
| **_Timing_**                                                        |                                                                                                    |
| `-T<0-5>`                                                           | Timing template – paranoid (0), sneaky (1), polite (2), normal (3), aggressive (4), and insane (5) |
| `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>` | Minimum and maximum number of parallel probes                                                      |
| `--min-rate <number>` and `--max-rate <number>`                     | Minimum and maximum rate (packets/second)                                                          |
| `--host-timeout`                                                    | Maximum amount of time to wait for a target host                                                   |
| **_Real-time output_**                                              |                                                                                                    |
| `-v`                                                                | Verbosity level – for example, `-vv` and `-v4`                                                     |
| `-d`                                                                | Debugging level – for example `-d` and `-d9`                                                       |
| **_Report_**                                                        |                                                                                                    |
| `-oN <filename>`                                                    | Normal output                                                                                      |
| `-oX <filename>`                                                    | XML output                                                                                         |
| `-oG <filename>`                                                    | `grep`-able output                                                                                 |
| `-oA <basename>`                                                    | Output in all major formats                                                                        |