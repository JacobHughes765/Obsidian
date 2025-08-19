#!/bin/bash

  

# Check if the user provided an IP range

if [ "$#" -ne 3 ]; then

    echo "Usage: $0 <start_ip> <end_ip> <output_file>"

    exit 1

fi

  

start_ip=$1

end_ip=$2

output_file=$3

  

# Convert IP addresses to decimal for comparison

ip_to_decimal() {

    local a b c d

    IFS=. read -r a b c d <<< "$1"

    echo $((a * 256 ** 3 + b * 256 ** 2 + c * 256 + d))

}

  

start_dec=$(ip_to_decimal "$start_ip")

end_dec=$(ip_to_decimal "$end_ip")

  

echo "Scanning IPs from $start_ip to $end_ip..."

  

# Clear the output file if it already exists

> "$output_file"

  

# Function to ping an IP address

ping_ip() {

    local ip="$1"

    if ping -c 1 -W 1 "$ip" &> /dev/null; then

        echo "$ip" >> "$output_file"

    fi

}

  

# Loop through IPs and run ping in the background

for (( ip=$start_dec; ip<=$end_dec; ip++ )); do

    # Convert decimal back to IP

    a=$(( (ip >> 24) & 255 ))

    b=$(( (ip >> 16) & 255 ))

    c=$(( (ip >> 8) & 255 ))

    d=$(( ip & 255 ))

    current_ip="$a.$b.$c.$d"

  

    # Call the ping function in the background

    ping_ip "$current_ip" &

  

    # Limit the number of background processes

    if (( $(jobs -r -p | wc -l) >= 100 )); then

        wait -n  # Wait for any background job to finish

    fi

done

  

# Wait for all background jobs to finish

wait

  

echo "Scanning completed. Reachable IPs are saved in $output_file."