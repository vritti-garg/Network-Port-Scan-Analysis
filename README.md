# Network-Port-Scan-Analysis

## Objective
The goal of this project is to use Nmap to discover open ports on devices within a local network and analyze the potential security exposure from those services.

## Tool Used
* **Nmap:** The tool used for performing the TCP SYN port scan.

## Process Followed
1.  The local network's IP range was identified to define the scan target.
2.  A TCP SYN scan was executed using the command `nmap -sS <Your_IP_Range>` to discover hosts and their open ports.
3.  The raw scan results were saved to a text file for documentation.
4.  The open ports were researched to identify running services and analyze potential security risks.

## Scan Results and Analysis

The Nmap scan discovered a host on the local network with several open TCP ports. The full, unfiltered output from the Nmap command is saved in the `scan_results.txt` file in this repository.

Below is a summary and analysis of the open ports that were discovered on the device:

* **Port 135/tcp (msrpc):** This port is used for Microsoft's Remote Procedure Call (RPC) service, a core component of Windows networking that allows programs to communicate with each other over the network. If not properly secured, it has historically been a target for remote attacks.

* **Port 139/tcp (netbios-ssn):** This port corresponds to the NetBIOS Session Service, an older protocol used for file and printer sharing in Windows environments.

* **Port 445/tcp (microsoft-ds):** This port is used by the Server Message Block (SMB) protocol, the modern standard for Windows file and printer sharing. While essential for local networking, this port is a very high-value target for attackers and was famously exploited by ransomware like WannaCry.

* **Port 4343/tcp (unicall):** This port is officially assigned to a service called "UNICALL," which is related to PC-to-phone telecommunications. It may be in use by a specific voice or video chat application.

* **Port 4449/tcp (privatewire):** This is a non-standard port without a commonly known service. The "privatewire" name is a placeholder. An open, non-standard port like this could belong to a specific application, a game, or something that warrants further investigation to identify the listening process.

**Overall Security Risk Assessment:**
The open ports `135`, `139`, and `445` strongly indicate that the scanned device is a Windows machine configured for network file sharing. On a trusted local network, this can be normal. However, these services represent a significant security risk if the device is not kept up-to-date with security patches, is not protected by a firewall, or uses weak passwords.

## Screenshots of a Live Scan

*(This is where you will embed your screenshot images.)*

---

## Key Concepts Encountered
This project involves practical application of several important cybersecurity concepts:
* The function and risks of open ports.
* The mechanics of a TCP SYN scan.
* The difference between TCP and UDP protocols in scanning.
* The role of a firewall in securing ports.
* The definition and purpose of a port scan from an attacker's perspective.
* Methods for securing open ports on a network.
