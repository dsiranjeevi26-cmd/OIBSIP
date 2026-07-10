# OIBSIP
# Basic Network Scanning with Nmap

## Objective

The objective of this project is to learn how to use Nmap to perform basic network scanning, identify open ports, detect running services, and identify the operating system of a target machine.

---

## What is Nmap?

Nmap (Network Mapper) is a free and open-source network scanning tool used by network administrators and cybersecurity professionals. It helps discover devices on a network, identify open ports, detect running services, and determine the operating system of a target host.

---

## Why Network Scanning Matters

Network scanning is important because it helps identify active devices, discover open ports, detect running services, and identify potential security risks. It is an essential step in network administration and security assessment.

---

## Installation Steps

1. Downloaded Nmap from https://nmap.org/download.html
2. Installed Nmap using the default installation settings.
3. Opened Zenmap after installation.
4. Verified that Nmap was installed successfully.

---

## Commands Used

Basic Scan

nmap 172.16.31.155

Service Version Scan

nmap -sV 172.16.31.155

OS Detection Scan

nmap -O 172.16.31.155

---

## Files Included

- README.md
- nmap_scan_results.txt
- Basic Scan Screenshot
- Service Version Scan Screenshot
- OS Detection Scan Screenshot

---

## Ethical Use

This project was performed only on a local machine within a private network for educational purposes. Nmap should only be used on systems that you own or have explicit permission to scan. Unauthorized scanning of public or production systems may be illegal and unethical.
