```
@echo off
setlocal

REM Set network folder path and temporary folder path
set "networkFolderPath=S:\Applications\Shipping-Prod"
set "tempFolderPath=%homeFolder%\Desktop\ShippingUI"

REM Get the home folder of the currently logged-in user
set "homeFolder=%USERPROFILE%"

REM Download the folder from the network using robocopy
robocopy "S:\Applications\Shipping-Prod" "%homeFolder%\Desktop\ShippingUI" /E

REM Check if the executable file was successfully downloaded
if exist "%homeFolder%\Desktop\ShippingUI\" (
    echo Executable downloaded successfully.

    REM Run the executable from the temporary folder
    start /max "ShippingSample" "%homeFolder%\Desktop\ShippingUI\ShippingUI.exe" "--sample"

    REM Loop to check if the application is still running
    :LOOP
    tasklist | find /i "ShippingUI.exe" >nul 2>&1
    if errorlevel 1 (
        echo Application closed. Deleting temporary folder.
        rmdir /s /q "%homeFolder%\Desktop\ShippingUI"
    ) else (
        timeout /t 1 /nobreak >nul
        goto LOOP
    )
) else (
    echo Failed to download the executable.
)

echo Batch script completed.
REM Close the Command Prompt window
exit

pause
```
