# Define variables
$networkDrive = "\\stonedrive\stone\Engineering\Product Documentation"  # Change to your network drive path
$username = "stone\cdykstra"              # Change to the user you want to set permissions for

# Set Modify permissions
try {
    # Grant Modify permissions
    icacls $networkDrive /grant "$username :(M)" /T /C

    # Check if the command was successful
    if ($LASTEXITCODE -eq 0) {
        Write-Host "Successfully set Modify permissions for $username on $networkDrive."
    } else {
        Write-Host "Failed to set permissions. Please check the user and network drive path."
    }

    # Display current permissions 
    Write-Host "Current permissions for $networkDrive :"
    icacls $networkDrive
} catch {
    Write-Host "An error occurred: $_"
}