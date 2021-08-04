# LineCounter, just run the below at the root of the folder you want to count the lines on. <br/>
You can always adjust the filters of take out the **-Recurse**  parameter

``` Javascript
$CountInFile  = @()
 $files       = Get-ChildItem -File -Recurse -Include ('*.ps1', '*.csv')
 foreach ($file in $files) {
    $fileCount    = (get-content $file.FullName).count
    $CountInFile += $fileCount
}

for ($index = 0; $index -le  $CountInFile.Length ; $index++) {
    $TotalSum +=  $CountInFile[$index]
}
$TotalSum 
```
