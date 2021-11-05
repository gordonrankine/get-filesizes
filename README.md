# Get-FileSizes

The PowerShell script gets file sizes from a specified directory and outputs results to a .csv file. Details gathered include File Path, Directory Name, File Name, Size (Bytes), Size (MB), Size (GB), Extension, Creation Time (UTC), Last Write Time (UTC) and Read Only.

## Parameters

.PARAMETER outDir
This is the directory where the csv report will be saved to. If the directory doesn't exist it will be created.

.PARAMETER scanDir
This is the directory to scan to generate the report for file sizes.

.PARAMETER roundTo
[OPTIONAL] This is the number of decimal points the file sizes will be calculated to. The default is 0 and the choices are 0, 1, 2, 3 & 4 decimal places.

.PARAMETER filesBiggerThan
[OPTIONAL] This parameter is used to limit the scan to files bigger than the set size in GB. Cannot be used with the -filesLessThan parameter.

.PARAMETER filesLessThan
[OPTIONAL] This parameter is used to limit the scan to files less than the set size in GB. Cannot be used with the -filesBiggerThan parameter.

.PARAMETER sortBy
[OPTIONAL] This parameter is used to specify the sort order for the report, the default is File Patch. The choices are File Path, Big Files & Small Files.

## Examples

.EXAMPLE
.\Get-FileSizes.ps1 -outDir "c:\temp" -scanDir "C:\Windows"
Scans C:\Windows and saves the .csv report to c:\temp

.EXAMPLE
.\Get-FileSizes.ps1 -outDir "c:\temp" -scanDir "C:\Windows" -fileBiggerThan 1 -roundTo 2
Scans C:\Windows for files larger than 1 GB and saves the .csv report to c:\temp. The file sizes will be rounded to 2 decimal places.

.EXAMPLE
.\Get-FileSizes.ps1 -outDir "c:\temp" -scanDir "C:\Windows" -fileLessThan 5
Scans C:\Windows for files less than 5 GB and saves the .csv report to c:\temp

.EXAMPLE
.\Get-FileSizes.ps1 -outDir "c:\temp" -scanDir "C:\Windows" -fileBiggerThan 1 -orderBy BigFiles
Scans C:\Windows for files larger than 1 GB and saves the .csv report to c:\temp. The report will be ordered by the biggest files.

## Why This Script

Simple script instead of having to install utilites such as TreeSize and I don't get to write many scripts nowadays so I thought I would try to keep my hand in and write this one.

## Script Info

Scanning for files can be sorted and limited to files bigger/smaller than a certain size.

## Future Updates

- Exclude directories.
- Calculate File Hash (useful for finding duplicate files).

## Feedback

Please use GitHub Issues to report any, well.... issues with the script.
