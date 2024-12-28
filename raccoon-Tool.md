![](/CYBERTOOLCHEATSHEET-images/Raccoon-command-cheatsheet.png)


# THE RACCOON TOOL
<br><br><br>
# How to Install The Raccoon Tool: 

https://youtu.be/k27Ixrpx6Xo?si=65P95Hcy1PEq8asr


**THE RACCOON TOOL BASIC COMMANDS**
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
| **COMMAND**                                          | **DESCRIPTION**                                                                                                           |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| raccoon --version                                    | Displays information of the current version of the tool.                                                                  |
| raccoon <target.com>                                 | Scans the target specified with the default configuration.                                                                |
| raccoon –T 50 <target.com>                           | Thread specification for URL fuzzing and sub-domain enumeration.                                                          |
| raccoon –sc <target.com>                             | Scans the target with the Nmap tool, and SC flag.                                                                         |
| raccoon –sv <target.com>                             | Scans the target with the Nmap tool, and SV flag.                                                                         |
| raccoon –f <target.com>                              | Scans the target with the Nmap tool, and a combination of both SC and SV flags.                                           |
| raccoon –p 20-65535 <target.com>                     | Scans the target across a range of ports specified. E.g., this command specifies a range of ports from 20 to 65535.       |
| raccoon -q -o <output_path> <target.com>             | Scans target quietly without stdout and creates a directory in the path and name specified to store all scan results.     |
| raccoon –fr <target.com>                             | Scans the target and follows every redirect that is valid.                                                                |
| raccoon --tls-port <specify_tls_port> <target.com>   | Scans target with the custom TLS port specified.                                                                          |
| raccoon --tor-routing <target.com>                   | Routes scanning through the Tor network. Ensure you have Tor installed and launched via your terminal.                    |
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



**THE RACCOON TOOL INTERMEDIATE COMMANDS**
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
| COMMAND                                                            | DESCRIPTION                                                                                                                    |
|--------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| raccoon --skip-health-check <target.com>                           | Scans the target and pulls every information about it, without checking if the domain is alive or not.                         |
| raccoon --no-url-fuzzing <target.com>                              | Scans the target using every other default configurations of the tool, without fuzzing the target for URL paths.               |
| raccoon --no-sub-enum <target.com>                                 | Scans the target using every other default configurations of the tool, without performing subdomain enumeration.               |
| raccoon --no-url-fuzzing --no-sub-enum <target.com>                | Scans the target using every other default configurations. Ignores both fuzzing the target and enumerating for subdomains.     |
| raccoon --skip-nmap-scan <target.com>                              | Skips nmap scan and performs the rest of the scanning using the default configurations.                                        |
| raccoon --ignored-response-codes <status_codes> <target.com>       | The specified status codes would be ignored when fuzzing for URLs. E.g., 301, 403, 404, 203 etc.                               |
| raccoon --subdomain-list <path_subdomain_list> <target.com>        | Continues the scan process, with the specified subdomain list, to uncover more subdomains belonging to the target.             |
| raccoon --subdomain-list <path_subdomain_list> -T 30 <target.com>  | Continues the scan process using the multiple threads specified, with the provided subdomain list, to uncover more subdomains. |
| raccoon --vulners-nmap-scan <target.com>                           | Performs vulnerability scanning using its default nmap scripts. Suitable for when scanning a target IP-addresses.              |
| raccoon -w <path_fuzz_list> <target.com>                           | The tool scans the target using default configurations, and fuzzes URL paths using the specified wordlist.                     |
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------								                                                                                                                                     



**THE RACCOON TOOL COMPLEX COMMANDS**
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
| COMMAND                                                                                 | DESCRIPTION                                                                                                                                                           |
|-----------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| raccoon -fr -w <path_fuzz_list> <target.com>                                            | Scans the target using default configurations, while fuzzing and following redirects with both its default fuzzing wordlist, and the user's specified wordlists.      |
| raccoon -d A,MX,NS,CNAME,SOA,TXT <target.com>                                           | Scans target to obtain the specified DNS records.                                                                                                                     |
| raccoon --proxy-list <path_to_proxylist> <target.com>                                   | Scans the specified target while concealing the user's identity, by routing the traffic and communications through the specified proxy-list by the users.             |
| raccoon --proxy http://127.0.0.1:8080 <target.com>                                      | Scans the entire target using the specified proxy for routing. This comes handy when you want to route your communication through burpsuite,      	       		        |   
|                                                                                         | or any other tool used for pentesting. 																                                                                                                |
| raccoon -f -d A,MX --proxy http://127.0.0.1:8080 <target.com>                           | Performs full nmap service detection scan, DNS record queries, on the target using the specified proxy for routing.  	                                                |  
|                                                                                         | This will route your communication through the tool. e.g., BURPSUITE.                                                                                                 |
| raccoon -d A,MX --tor-routing <target.com>                                              | Performs the specified DNS queries, while routing the scans being conducted through tor network. Ensure you have tor installed and launched via your terminal.        |
| raccoon -c PHPSESSID:12345,isMobile:false <target.com>                                  | Performs the scans with the specified cookie ID indicated. Good when target runs a php based web-application.                                                         |
| raccoon -c PHPSESSID:abc123,sessionToken:xyz123 <target.com>                            | Performs the scans with the specified cookie, and session ID indicated. Good when target runs a php based web-application.                                            |
| raccoon-w <path_fuzz_list> --subdomain-list <path_subdomain_list> -T 30 <target.com>    | Performs full scan on the target with default configurations. Then proceeds further                                                                                   |
|                                                                                         | with the target using the wordlist provided by the user, for url fuzzing, subdomain enumeration, with the specified thread number.                                    |
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
