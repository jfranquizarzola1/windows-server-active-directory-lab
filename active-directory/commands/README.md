# Active Directory Commands

These are some commands I used while building and testing my Active Directory lab.

## Group Policy

```cmd
gpupdate /force
```

Updates Group Policy.

```cmd
gpresult /r
```

Shows which Group Policies were applied.

## Network Drives

```cmd
net use
```

Shows mapped network drives.

```cmd
net use I: /delete
```

Removes the I: drive.

```cmd
net use * /delete
```

Removes all mapped drives.

## Local Administrators

```cmd
net localgroup administrators
```

Shows the users and groups in the local Administrators group.

## Network Information

```cmd
ipconfig
```

Shows basic IP information.

```cmd
ipconfig /all
```

Shows detailed network and DNS information.

## Time Sync

```cmd
w32tm /query /status
```

Checks the Windows time status.

```cmd
w32tm /query /source
```

Shows the current time source.

```cmd
w32tm /resync /rediscover
```

Resynchronizes the computer with the domain time source.

## Share Testing

```cmd
dir \\DC01\IT
```

Tests access to the IT shared folder.

```cmd
dir \\DC01\HR
```

Tests access to the HR shared folder.
