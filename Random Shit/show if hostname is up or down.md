# Define the input CSV file and output file
$InputCsvFile = 'C:\Users\spadmin\OneDrive - stoneplasticsmfg.com\Desktop\All.csv'
$OutputFile = 'C:\Users\spadmin\OneDrive - stoneplasticsmfg.com\Desktop\ipStatus.txt'

# Clear previous contents of the output file
Clear-Content -Path $OutputFile -ErrorAction SilentlyContinue

# Import the CSV file
$csvData = Import-Csv -Path $InputCsvFile

foreach ($entry in $csvData) {
    # Assuming the IP address is in a column named 'IP'
    $ipAddress = $entry.IP

    # Try to get the hostname
    try {
        $hostname = [System.Net.Dns]::GetHostEntry($ipAddress).HostName
    } catch {
        $hostname = "Hostname not found"
    }

    # Test connection to the IP address
    if (Test-Connection -ComputerName $ipAddress -Count 1 -ErrorAction SilentlyContinue) {
        # Write to the output file if the IP is up
        "$hostname,$ipAddress,up" | Out-File -FilePath $OutputFile -Append
        Write-Host "$hostname,$ipAddress,up" -ForegroundColor Green
    } else {
        # Write to the output file if the IP is down
        "$hostname,$ipAddress,down" | Out-File -FilePath $OutputFile -Append
        Write-Host "$hostname,$ipAddress,down" -ForegroundColor Red
    }
}