## Veranstaltung Programmierung 2, UIB
### Dozent: Prof. Dr. Frank Dopatka

[zurück zur Hauptseite...](https://informatik-mannheim.github.io/iExpo-Sommer-2021/)

## Secuteel
The secuteel app is a command-prompt-based auditing tool, with multi-platform support, written in go.
- [Introduction](#Introduction)
- [Installation](#Installation)
	- [Compile](#Compile)
		- [Git](#Git)
		- [Go](#Go)
- [Help](#Help)
- [Documentation](#Documentation)
	- [Command overview](#Command-overview)
	- [Create a config file](#Create-a-config-file)
	- [Note](#Note)
	- [Additional JavaScript functions](#Additional-JavaScript-functions)
	- [Supported Commands through wrapper](#Supported-Commands-through-wrapper)
	- [Start a scan](#Start-a-scan)
- [Example usage](#Example-usage)
	- [Config to get started](#Config-to-get-started)
		- [Windows](#Windows)
		- [Linux](#Linux)
- [License](#License)
### Introduction
We are Team Seculeet and as part of the Cyber Security Development Project (CEP), it was our task to develop an audit framework on behalf of ERNW Enno Rey Netzwerk GmbH. 
Our tool which is called secuteel automatically checks the configuration of systems for their security and hardening standards. 
The goal of this tool is to process a given set of test points with a minimum manual effort and to provide the output of the results for further processing.
## Installation
- You can download our pre-compiled binaries [here](https://github.com/Seculeet/secuteel/tree/main/binaries)
- On Linux you may want to run `chmod +x secuteel`, before executing it
#### Compile
- *secuteel* reguieres Go 1.16 or higher
##### Git
- You can get and compile it from scratch using the following command:
- `git clone https://github.com/seculeet/secuteel.git`; `cd secuteel`; `go get`; `go build`
##### Go
- You can also get it using go:
- `go get -u github.com/seculeet/secuteel`
### Help
- If you have issues running a command, activate the `-debug` flag at startup
- You can also activate the verbose mode using the `-v` flag
### Documentation
- This will get you started on running your first audit. If you are running into problems check the `error.log`
#### Command overview
- `-input`, `--input=` 'expects path to config file (.json)'
- `-output`, `--output=` 'specify your output file (.zip)'
- `-add`, `--add=` 'add a list of allowed commands'
- `-v` 'toggle verbose mode for console'
- `-s` 'skip sanity check'
- `-h` 'help'
- `-debug` 'activate debug mode for log files'
- `-p` 'set password to encrypt output zip folder'

#### Create a config file
{  \
&nbsp;&nbsp;&nbsp;`"system"`:\
&nbsp;&nbsp;&nbsp;{\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"systemName"`: "The current operating system",\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"version"`: "The OS version",\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"shell"`: "A system shell (e.g. CMD, Powershell), optional",\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"argument"`: "The argument used to execute commands (e.g. /C), optional",\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;` "root"`: "Specify if the audit has to be run as root, optional (default false)"\
&nbsp;&nbsp;&nbsp;},\
&nbsp;&nbsp;&nbsp;`"commands"`: [\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"name"`: "Example Audit Step",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"command"`: "You can script in JavaScript and add your audit command in here",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"dontSaveArtefact"`: true,  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"blackenContent"`: "Regex pattern",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"typeExpected"`: "containsReg",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"expected"`: "Regex pattern",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"description"`: "This is just for taking notes of what is happening"  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}\
&nbsp;&nbsp;&nbsp;]\
}
#### Note
- `name` Has to be unique and without special characters (required)
- `command` You can use everything JavaScript has to offer and additionaly our own implemented functions (required)
- `dontSaveArtefact` Default is false, if set to true no artefacts for this Auditstep will be saved (optional)
- `blackenContent` Censor the saved artefacts with the given pattern. Can't be used if `dontSaveArtefact` is toggled true (optional)
- `typeExpected` Default is `==`, (optional)
	- Supported operators for Strings: `==, !=, contains, containsReg, nil`
	- Supported operators for integers: `==, !=, <, <=, >, >=, nil`
- `expected` Default is an empty string, it is compared with the ``command`` output using the chosen operator in `typeExpected` (optional)
- `description` Is just for taking notes of what is happening (optional)

#### Additional JavaScript functions 
- `call('command')` Specify your command type (e.g. ls, grep), additionaly add arguments (e.g. -la, -e). You can also specify a file to directly save it to the artefacts (e.g. Â§fileÂ§pathToFile).
- `callCompare('command', 'string to compare to') bool` Can be used in a JavaScript if statement. If command output == string it return true
- `callContains('command', 'string') bool` Can be used in a JavaScript if statement. If command output contains string return true
- `shell('command without Wrapper')` The command gets directly executed on the shell, without further checking if its valid or harmful to the system. Only use if necessary, try `call()` Instead, because this will deliver better debugging output.
- `regQuery('registry','value')` This is our own function to query the registry on windows.
	- The format has to be: `regQuery('HKLM:\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion', 'ProductID')`
- `printToConsole('string')` Prints the string to your stdout (Good for debugging)
- `printToLog('string')` Prints the string to your log file (Good for taking notes)

#### Supported Commands through wrapper
Here is a list of all supported Commands you can use in `Call()`,  `CallCompare()` and `CallContains()`. If the command you want to use is not included you might want to add it through `-add` instead of using `shell()`.

`"Get-MpComputerStatus"`, `"Get-ItemPropertyValue"`, `"Get-NetFirewallProfile"`, `"type"`, `"echo"`, `"reg"`, `"findstr"`,
`"dir"`, `"ls"`, `"cat"`, `"grep"`, `"find"`, `"useradd"`, `"stat"`, `"mount"`, `"systemctl"`, `"egrep"`, `"test"`, `"call"`, `"ps"`,
`"Select-String"`, `"%"`, `"modprobe"`, `"df"`, `"rpm"`, `"zypper"`, `"crontab"`, `"stat"`, `"sysctl"`, `"journalctl"`, `"sestatus"`,
`"apparmor_status"`, `"timedatectl"`, `"ss"`, `"lsof"`, `"iw"`, `"ip"`, `"lsmod"`, `"firewall-cmd"`, `"nmcli"`, `"iptables"`,
`"ip6tables"`, `"nft"`, `"auditctl"`, `"sshd"`, `"useradd"`, `"rmmod"`, `"awk"`, `"xargs"`, `"subscription-manager"`, `"dnf"`, `"authselect"`

**Keep in mind, that some commands only work on Windows and others only on Linux. Some are multi-platform but might behave differently.**

#### Start a scan
- When starting the tool via command line you have to provide an input file. Everything else is optional.
- `./secuteel -input 'path/to/config(.json)'`
### Example usage
- Run an audit on Linux with an custom output file (.zip), verbose output and debugging enabled.
- `./secuteel -input 'path/to/config(.json)' -output 'name' -v -debug`  
#######
- Add new commands for the current audit.
- `./secuteel -input 'path/to/config(.json)' -add 'custom,command,here'`
#######
- Run the help command on Windows.
- `secuteel.exe -h`
#### Config to get started
##### Windows
{  \
&nbsp;&nbsp;&nbsp;`"system"`:\
&nbsp;&nbsp;&nbsp;{\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"systemName"`: "Windows",\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"version"`: "10.0.19042"\
&nbsp;&nbsp;&nbsp;},\
&nbsp;&nbsp;&nbsp;`"commands"`: [\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"name"`: "get_bluetooth_status",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"command"`: "regQuery('HKLM:\\SYSTEM\\CurrentControlSet\\Services\\bthserv', 'Start')",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"typeExpected"`: "==",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"expected"`: "3",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"description"`: "Checking bluetooth enabled"  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}\
&nbsp;&nbsp;&nbsp;]\
}
##### Linux
{  \
&nbsp;&nbsp;&nbsp;`"system"`:\
&nbsp;&nbsp;&nbsp;{\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"systemName"`: "Linux",\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"version"`: "20.04.1-Ubuntu"\
&nbsp;&nbsp;&nbsp;},\
&nbsp;&nbsp;&nbsp;`"commands"`: [\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"name"`: "get_password_expiration",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"command"`: "useradd -D | grep INACTIVE",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"typeExpected"`: "==",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"expected"`: "INACTIVE=-1",  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`"description"`: "Check for the default time an account gets disabled after password expires"  \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}\
&nbsp;&nbsp;&nbsp;]\
}
### License
Copyright &copy; 2021 Seculeet

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

[zurück zur Hauptseite...](https://informatik-mannheim.github.io/iExpo-Sommer-2021/)