  

$Csvfile = "C:\users\jhughes\Desktop\ExportDGs.csv"

$Groups = Get-DistributionGroup -ResultSize Unlimited

  
$Results=@()

foreach ($Group in $Groups) {

    # Get the group members

    try{

    $Members = Get-ADGroupMember -Identity $Group.Name -Recursive

    }

    catch{

    Write-Output "Error: $"

    }

    # Loop through each member

    foreach ($Member in $Members) {

        # Get the member's details

                $User = Get-ADUser -Identity $Member.SamAccountName -Properties DisplayName, EmailAddress

        # Create a custom object to store the results

        $Result = [PSCustomObject]@{

            GroupName = $Group.Name

            MemberName = $User.DisplayName

            EmailAddress = $User.EmailAddress

        }

         $Results += $Results

  

    }

}

        $Results | Export-CSV -Path $Csvfile -NoTypeInformation -Encoding UTF8 -Append