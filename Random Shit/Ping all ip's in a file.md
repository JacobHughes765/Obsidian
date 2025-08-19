
$InputFile is where the directory of the file you want to scan
Make sure you pipe | both up and down's

```
$InputFile = 'C:\Users\spadmin\OneDrive - stoneplasticsmfg.com\Desktop\ip.txt'
$machines = Get-content $InputFile

foreach ($machine in $machines){
 if (Test-Connection -ComputerName $machine -Count 1 -ErrorAction SilentlyContinue){
   Write-Host "$machine,up" -ForegroundColor Green | Out-file -FilePath 'C:\Users\spadmin\OneDrive - stoneplasticsmfg.com\Desktop\ipUP.txt'
 }
 else{
   Write-Host "$machine,down" -ForegroundColor Red | Out-File -FilePath 'C:\Users\spadmin\OneDrive - stoneplasticsmfg.com\Desktop\ipDOWN.txt'
     } 
 }
 ```