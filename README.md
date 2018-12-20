# New Drive Install Guide

This is a quick reference guide on installing a new drive with a new or copied OS to a new machine.

Sometimes we get errors like:

```error
"Your PC needs to be repaired. The application or operating system couldn’t be loaded because a required file is missing or contains errors. File: \windows\system32\winload.efi Error code: 0xc000***"
```


1. Utilize the recovery drive (Windows 10 install USB)
2. Access command prompt through the recovery drive (Windows 10 install USB)
3. Determine new drive through the Windows diskpart utility
  1. `diskpart`
  2. `select disk 0`
  3. `select volume`
4. Change directories into the drive that has broken boot loader (type `C:` to change current directory)
5. Execute bootfix commands
6. `bootrec /fixboot`
`bootrec /scanos`
`bootrec /fixmbr`
`bootrec /rebuildbcd`


You can verify your installed product key by using the below command:

```powershell
(Get-WmiObject -query 'select * from SoftwareLicensingService').OA3xOriginalProductKey
```

