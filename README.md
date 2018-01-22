# up-debian_ubuntu_update_tool

Table of contents
---------------------------

  * [Table of contents](#table-of-contents)
  * [Description](#description)
  * [Usage](#usage)
  * [Installation](#installation)
  * [License](#license)
  * [Dependencies](#dependencies)
  * [Package Lists](#package-lists)
  * [Return codes](#return-codes)
  * [Contents of Help Page](#contents-of-help-page)
  * [Disclaimer](#disclaimer)
 

Description
------------------

 Up is a tool that automates the update procedure for Debian and Ubuntu based
 Linux systems.
 
Usage
-----------------

Run in terminal
 
up --[options][arguments]

Options list:

| Option          | Description     |
| --------------- | --------------- |
| up              | system update |
| up --help | Print help information and exit |
| up --clean | system clean |
| up --extraclean  | extended system clean |
| up --list [path] | print the package lists at path,.default /tmp/ |

See help section below for more details

Installation
----------------------

 Unzip the "up" bash script from the zip archive and move it to either
 /usr/local/bin or ~/bin. You can either do this from a command line or 
 simply drag the file out of Archive Manager to wherever you'd like it to go.

 Note: scripts that are run from the ~/bin directory cannot be prefixed with
 'sudo' as the system will fail to find them. Those who intend to run up from
 a script for cron, anacron or systemd timers should place it in /usr/local/bin
 This is also the best practice if there are more than one administrator
 accounts on the machine.

License
-----------------

 Up is free software. You can redistribute it and/or modify it under the
 terms of the GNU General Public License Version 2.0. as published by
 the Free Software Foundation. A copy of the GNU GPL 2.0 is provided with the
 software.

Dependencies
-------------------------

Some functions require optional dependencies packages to be installed.
These functions are run under the --extraclean command and the --list
command. If the user is not using these commands they do not need these
dependencies. If uninstalled and if users uses the above commands the
script skips relevant sections with a warning.

These optional dependencies are left to user discretion.

| Dependencies | Usage |
| ------ | ------ |
| aptitude | High-level interface to the package manager APT |
| deborphan | Orphaned package finder |

To install these Dependencies  find them in software manager or 
run these commands in terminal:

```sh
sudo apt install aptitude
sudo apt install deborphan
```

Package Lists
--------------- 

The package files list generator provides a snapshot of system 
by producing a group of 12 files
which describe the system.
These lists can be very useful, for example:
Reporting bugs, discussing installed packages, maintenance, freeing 
space on your hard drive, backing up, restoring or migrating system etc.

| Index | Contents | Filename |
| -------- | -------- | ----- |
| 1 | All installed | All_PKG |
| 2 | All native, explicitly installed | Exp_PKG |
| 3 | List orphaned packages  | noinstall_PKG |
| 4 | List packages not required by any other package | non-Dep_PKG |
| 5 | Get a dump of the whole system information | stats_PKG |
| 6 | List packages that were recently added to one of the installation sources | Recent_add_PKG |
| 7 | List of non-standard repositories in use | non_standard_PKG |
| 8 | List Installed packages by size | install_size_PKG |
| 9 | List packages installed automatically (as dependencies) | auto_Dep_PKG |
| 10 | Prints a list of all installation source |  Info_Source_PKG|
| 11 | List packages by install date  | Install_date_1_PKG |
| 12 | List packages by install date less data | Install_date_2_PKG |


Return codes
---------------------

* 0 - Normal non-error controlled exit.
* 1 - General error occurred
* 2 - Failed to find path specified by user , --list [path]  


Contents of Help Page
----------------------

	Up is a tool that automates the update procedure 
	for Debian and Ubuntu based Linux systems.

	Commands:
	up = full system update.

	Running "up" with no options will update the 
	apt cache and then perform a
	full distribution update automatically.

	up --clean = system update with cleanup.

	Adding the "--clean" option will invoke the 
	apt commands to search for and remove locally 
	cached packages that are no longer 
	in the repositories and remove orphaned packages 
	that are no longer needed by programs.

	up --extraclean = system update with cleanup 
	and extra options
	
	This option will run the full system update and 
	then the --clean option. It will then run two extra 
	options using optional dependencies deborphan and 
	aptitude. These remove obsolete packages no longer
	included in any repositories and orphaned packages. 
	
	up --list = generate the package list
	
	This option generates a list of 12 files useful for system 
	maintenance. A folder is created with following 
	time/date stamp syntax HHMM-DDMONYY-pkglist.
	If no path is passed the lists are placed in this folder at /tmp/
	The user can pass a path as an argument 
	for example: up --list "/home/userme/foo" 
	
	up --help = shows this help page.

	By Joe Collins www.ezeelinux.com 
	(GNU/General Public License version 2.0)



Disclaimer
-----------------------------
 
 THIS SOFTWARE IS PROVIDED BY EZEELINUX “AS IS” AND ANY EXPRESS OR IMPLIED
 WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
 MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
 EVENT SHALL EZEELINUX BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL,
 EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
 PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR
 BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER
 IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
 ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
 POSSIBILITY OF SUCH DAMAGE.

