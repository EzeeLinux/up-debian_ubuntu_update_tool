# up-debian_ubuntu_update_tool


1. Description:

 Up is a tool that automates the update procedure for Debian and Ubuntu based
 Linux systems.

2. Installation:

 Unzip the "up" bash script from the zip archive and move it to either
 /usr/local/bin or ~/bin. You can either do this from a command line or simply
 drag the file out of Archive Manager to wherever you'd like it to go.

 Note: scripts that are run from the ~/bin directory cannot be prefixed with
 'sudo' as the system will fail to find them. Those who intend to run up from
 a script for cron, anacron or systemd timers should place it in /usr/local/bin
 This is also the best practice if there are more than one administrator
 accounts on the machine.

3. License.

 Up is free softare. You can redistribute it and/or modify it under the
 terms of the GNU General Public License Version 2.0. as published by
 the Free Software Foundation. A copy of the GNU GPL 2.0 is provided with the
 software.

4. Contents of Help Page:

 Up is a tool that automates the update procedure for Debian and Ubuntu based
 Linux systems.

 Commands:
    up = full system update.

    Running "up" with no options will update the apt cache and then perform a
    full distribution update automatically.

    up --clean = full system update with cleanup.

    Adding the "--clean" option will invoke the apt commands to search for and
    remove locally cached packages that are no longer in the repositories and
    remove orphaned packages that are no longer needed by programs.

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

