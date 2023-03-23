# PowerShell

reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\WINEVT\Channels\Microsoft-Windows-Sysmon/Operational# Live Examination

\| Command | Description |

\| --------------------------------------------- | ----------------------------------------------------------- |

\| \`Get-Process\` | Get brief information about running processes |

\| \`Get-Process 'powersh\*'\` | Get brief information about a named process with a wildcard |

\| \`Get-Process 'powershell' \\| Select-Object \*\` | Detailed information about a running process |

\| \`Get-Process -ComputerName MartianPC\` | Information about processes on a remote system |

\| Command | Description |

\| ------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |

\| \`Get-CimInstance -Class Win32\_Process \\| Select-Object ProcessId, ProcessName, CommandLine\` | Returns an object with Windows process information |

\| \`Get-CimInstance -Class Win32\_Process \\| Where-Object -Property ParentProcessId -EQ 1337\` | Returns an object with Windows process information where ParentProcessId is 1337 |

\| Command | Description |

\| ------------------------------------------------------------------------------------------------------ | ----------------------------------------------- |

\| \`Get-NetTCPConnection\` | Displays several network connection information |

\| \`Get-NetTCPConnection -State Listen\` | Display listening connections |

\| \`Get-NetTCPConnection -State Listen \\| Select-Object -Property LocalAddress, LocalPort, OwningProcess\` | Display listening connections by property |

\| Command | Description |

\| ------------------------------------------------ | ------------------------------------- |

\| \`Get-Service nginx\` | Get information about running servies |

\| \`Get-Service nginx \\| Select-Object -Property \*\` | Display the properties of a service |

Get-LocalUser and Get-LocalGroup

\| Command | Description |

\| ------------------------------------------------------------ | --------------------------------------------- |

\| \`Get-LocalUser\` | List all local users |

\| \`Get-LocalUser Martian\` | List user information by username |

\| \`Get-LocalUser \\| Where-Object -Property Enabled -EQ $true\` | List local users with enabled accounts |

\| \`Get-LocalUser \\| Where-Object -Property Enabled -EQ $false\` | List local users with disabled accounts |

\| \`Get-LocalGroup\` | List all local groups |

\| \`Get-LocalGroup Administrators\` | Lists the Administrators group |

\| \`Get-LocalGroupMember Administrators\` | Lists the members of the Administrators Group |# Live Examination

\| Command | Description |

\| --------------------------------------------- | ----------------------------------------------------------- |

\| \`Get-Process\` | Get brief information about running processes |

\| \`Get-Process 'powersh\*'\` | Get brief information about a named process with a wildcard |

\| \`Get-Process 'powershell' \\| Select-Object \*\` | Detailed information about a running process |

\| \`Get-Process -ComputerName MartianPC\` | Information about processes on a remote system |

\| Command | Description |

\| ------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |

\| \`Get-CimInstance -Class Win32\_Process \\| Select-Object ProcessId, ProcessName, CommandLine\` | Returns an object with Windows process information |

\| \`Get-CimInstance -Class Win32\_Process \\| Where-Object -Property ParentProcessId -EQ 1337\` | Returns an object with Windows process information where ParentProcessId is 1337 |

\| Command | Description |

\| ------------------------------------------------------------------------------------------------------ | ----------------------------------------------- |

\| \`Get-NetTCPConnection\` | Displays several network connection information |

\| \`Get-NetTCPConnection -State Listen\` | Display listening connections |

\| \`Get-NetTCPConnection -State Listen \\| Select-Object -Property LocalAddress, LocalPort, OwningProcess\` | Display listening connections by property |

\| Command | Description |

\| ------------------------------------------------ | ------------------------------------- |

\| \`Get-Service nginx\` | Get information about running servies |

\| \`Get-Service nginx \\| Select-Object -Property \*\` | Display the properties of a service |

Get-LocalUser and Get-LocalGroup

\| Command | Description |

\| ------------------------------------------------------------ | --------------------------------------------- |

\| \`Get-LocalUser\` | List all local users |

\| \`Get-LocalUser Martian\` | List user information by username |

\| \`Get-LocalUser \\| Where-Object -Property Enabled -EQ $true\` | List local users with enabled accounts |

\| \`Get-LocalUser \\| Where-Object -Property Enabled -EQ $false\` | List local users with disabled accounts |

\| \`Get-LocalGroup\` | List all local groups |

\| \`Get-LocalGroup Administrators\` | Lists the Administrators group |

\| \`Get-LocalGroupMember Administrators\` | Lists the members of the Administrators Group |# Live Examination

\| Command | Description |

\| --------------------------------------------- | ----------------------------------------------------------- |

\| \`Get-Process\` | Get brief information about running processes |

\| \`Get-Process 'powersh\*'\` | Get brief information about a named process with a wildcard |

\| \`Get-Process 'powershell' \\| Select-Object \*\` | Detailed information about a running process |

\| \`Get-Process -ComputerName MartianPC\` | Information about processes on a remote system |

\| Command | Description |

\| ------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |

\| \`Get-CimInstance -Class Win32\_Process \\| Select-Object ProcessId, ProcessName, CommandLine\` | Returns an object with Windows process information |

\| \`Get-CimInstance -Class Win32\_Process \\| Where-Object -Property ParentProcessId -EQ 1337\` | Returns an object with Windows process information where ParentProcessId is 1337 |

\| Command | Description |

\| ------------------------------------------------------------------------------------------------------ | ----------------------------------------------- |

\| \`Get-NetTCPConnection\` | Displays several network connection information |

\| \`Get-NetTCPConnection -State Listen\` | Display listening connections |

\| \`Get-NetTCPConnection -State Listen \\| Select-Object -Property LocalAddress, LocalPort, OwningProcess\` | Display listening connections by property |

\| Command | Description |

\| ------------------------------------------------ | ------------------------------------- |

\| \`Get-Service nginx\` | Get information about running servies |

\| \`Get-Service nginx \\| Select-Object -Property \*\` | Display the properties of a service |

Get-LocalUser and Get-LocalGroup

\| Command | Description |

\| ------------------------------------------------------------ | --------------------------------------------- |

\| \`Get-LocalUser\` | List all local users |

\| \`Get-LocalUser Martian\` | List user information by username |

\| \`Get-LocalUser \\| Where-Object -Property Enabled -EQ $true\` | List local users with enabled accounts |

\| \`Get-LocalUser \\| Where-Object -Property Enabled -EQ $false\` | List local users with disabled accounts |

\| \`Get-LocalGroup\` | List all local groups |

\| \`Get-LocalGroup Administrators\` | Lists the Administrators group |

\| \`Get-LocalGroupMember Administrators\` | Lists the members of the Administrators Group |
