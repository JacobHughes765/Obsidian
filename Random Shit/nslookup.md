#!/bin/bash

  

# Check if the input file and output file are provided

if [ "$#" -ne 2 ]; then

    echo "Usage: $0 input_file output_file"

    exit 1

fi

  

input_file="$1"

output_file="$2"

  

# Check if the input file exists

if [ ! -f "$input_file" ]; then

    echo "Input file does not exist: $input_file"

    exit 1

fi

  

# Clear the output file or create it if it doesn't exist

> "$output_file"

  

# Read each line (domain name) from the input file

while IFS= read -r domain; do

    if [[ -n "$domain" ]]; then  # Check if the line is not empty

        echo "Performing nslookup for: $domain"

        # Use nslookup to resolve the domain and append the output to the output file

        nslookup "$domain" >> "$output_file"

        echo "" >> "$output_file"  # Add a blank line for better readability

    fi

done < "$input_file"

  

echo "DNS resolution results have been written to: $output_file"