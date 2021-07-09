#!/bin/bash

# Up -- Debian/Ubuntu Update Tool (Version 1.3)
# Advanced command to fully update system: "up" Adding the option "--clean" will
# remove orphaned packages and auto-clean the apt cache. (January, 2018)
# Adding the option "--remove" will just reomve orphaned packages.
# By Joe Collins www.ezeelinux.com (GNU/General Public License version 2.0)
#
# ...And way we go!

# Check for less utility and install if needed:

dpkg -l | grep -qw less || sudo apt install less -yyq

# Set BASH to quit script and exit on errors:

set -e

# Functions:

update() {

echo "Starting full system update..."
sudo apt update
sudo apt full-upgrade -yy

}

clean() {

echo "Removing apt cache packages that can no longer be downloaded..."
sudo apt autoclean

}

remove() {

echo "Removing orpahned packages..."
sudo apt autoremove -yy
sudo apt remove --purge $(dpkg -l | grep "^rc" | awk '{print $2}') -yy

}

leave() {

echo "--------------------"
echo "- Update Complete! -"
echo "--------------------"
exit

}

up_help() {

less << _EOF_

 Up -- Debian/Ubuntu Update Tool (Version 1.3)  -help

 Up is a tool that automates the update procedure for Debian and Ubuntu based
 Linux systems.

 Press "q" to exit this Help page.

 Commands:
    up = full system update.

    Running "up" with no options will update the apt cache and then perform a
    full distribution update automatically.

    up --remove = full system update with orphaned packages removed.
    up --clean = full system update with full cleanup.

    Adding the "--clean" option will invoke the apt commands to search for and
    remove locally cached packages that are no longer in the repositories and
    remove orphaned packages that are no longer needed by programs.

    The "--remove" option only removes orphaned packages, leaving the apt cache
    alone.

    up --help = shows this help page.

 By Joe Collins www.ezeelinux.com (GNU/General Public License version 2.0)

 Disclaimer:

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

_EOF_

}

# Execution.

# Tell 'em who we are...

echo "Up -- Debian/Ubuntu Update Tool (Version 1.3)"

# Update and clean:

if [ "$1" == "--clean" ]; then
    update
    remove
    clean
    leave
fi

# Update and remove orphaned packages:

if [ "$1" == "--remove" ]; then
    update
    remove
    leave
fi

if [ "$1" == "--help" ]; then
    up_help
    exit
fi

# Check for invalid argument

if  [ -n "$1"  ]; then
    echo "Up Error: Invalid argument. Try 'up --help' for more info." >&2
    exit 1
fi

update
leave
