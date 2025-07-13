# Chrome-Force-Manifest-V2

- Run the code below in powershell to automatically create and set `ExtensionManifestV2Availability` with a value of `2` to keep using it.

```ps1
$registryPath="HKCU:\Software\Policies\Google\Chrome";$valueName="ExtensionManifestV2Availability";$valueData=2;if(-not(Test-Path "HKCU:\Software\Policies\Google")){New-Item -Path "HKCU:\Software\Policies\Google"|Out-Null};if(-not(Test-Path $registryPath)){New-Item -Path $registryPath|Out-Null};New-ItemProperty -Path $registryPath -Name $valueName -Value $valueData -PropertyType DWord -Force|Out-Null
```
