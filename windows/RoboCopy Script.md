`:: This program copies all files in the OLD FILES FOLDER on S: :: and copies it to NEW FILES FOLDER on SERVER2` 
`@ECHO OFF SETLOCAL`
`SET _source=\\SERVER\SHARE\OLD FILES` 
`SET _dest=\\SERVER2\SHARE\NEW FILES`
`SET _what=/MOV /MIR`
`:: /COPYALL` 
`:: COPY ALL file info` 
`:: /B` 
`:: copy files in Backup mode.` 
`:: /E` 
`:: copy Subfolders including Empty.` 
`:: /MIR` 
`:: MIRror a directory tree` 
`:: /MOVE` 
`:: Move files and dirs (delete from source after copying).` 
`:: /MOV` 
`:: MOVe files (delete from source after copying).`
`SET _options=/R:0 /W:0 /LOG:MyLogfile.txt /NFL /NDL` 
`:: /R:n :: number of Retries` 
`:: /W:n :: Wait time between retries` 
`:: /LOG :: Output log file` 
`:: /NFL :: No file logging` 
`:: /NDL :: No dir logging` 
`ECHO ********************************************************************` 
`ECHO ***** THIS WILL DELETE ALL FILES IN OLD FILES on SHARED DRIVE` 
`ECHO ***** TO THE NEW FILES FOLDER ON SERVER2 -CLOSE OUT NOW WITH X on WINDOW TO STOP THIS` 
`ECHO ***** OR FILES WILL BE DELETED.`
`TIMEOUT /T 20` 
`ROBOCOPY %_source% %_dest% %_what% %_options%`