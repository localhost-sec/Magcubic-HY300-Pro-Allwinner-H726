# Windows USB preparation

Open PowerShell as Administrator:

```powershell
Get-Disk | Format-Table Number,FriendlyName,Size,PartitionStyle
```

Verify the removable disk before formatting it. Use FAT32 only when the vendor recovery procedure specifies FAT32.

Verify firmware:

```powershell
$path = '.\Magcubic HY300 Pro Allwinner H726.img'
Get-Item $path | Select-Object Name,Length,LastWriteTime
Get-FileHash $path -Algorithm SHA256
```

Keep an unchanged master copy of the manufacturer image.

Never run destructive disk commands until the correct disk number is confirmed.