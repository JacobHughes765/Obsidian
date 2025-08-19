from scapy.all import ARP, Ether, srp

import ipaddress

  

def scan_ip_range(start_ip, end_ip):

    # Create a list to hold active IPs

    active_ips = []

  

    # Create an ARP request packet

    arp = ARP()

    ether = Ether(dst="ff:ff:ff:ff:ff:ff")

  

    # Iterate through the specified IP range

    for ip in ipaddress.summarize_address_range(ipaddress.IPv4Address(start_ip), ipaddress.IPv4Address(end_ip)):

        for addr in ip:

            arp.pdst = str(addr)

            packet = ether / arp

            # Send the packet and receive responses

            result = srp(packet, timeout=1, verbose=False)[0]

            # Parse the results

            for sent, received in result:

                active_ips.append(received.psrc)

  

    return active_ips

  

if __name__ == "__main__":

    # Input start and end IP addresses

    start_ip = input("Enter the starting IP address (e.g., 192.168.1.1): ")

    end_ip = input("Enter the ending IP address (e.g., 192.168.1.254): ")

  

    try:

        print(f"Scanning IP range: {start_ip} - {end_ip}")

        active_ips = scan_ip_range(start_ip, end_ip)

  

        print("Active IPs in the range:")

        for ip in active_ips:

            print(ip)

  

    except ValueError as e:

        print(f"Invalid IP range input: {e}")