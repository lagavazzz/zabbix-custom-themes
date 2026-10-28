The zip contains a separate build for each released line, each made from that version’s own source: 6.0, 7.0, 7.4 and 8.0. 
Each build has two files that go into the frontend folder (the one with zabbix.php, usually /usr/share/zabbix or /usr/share/zabbix/ui):

assets/styles/halloween-theme.css
include/classes/core/APP.php: replaces the stock, empty APP.php so “Halloween” appears in the theme list.

**To install:**

**Script:** run sudo sh install.sh. 
It finds the frontend folder, reads the Zabbix version, copies the right build and backs up APP.php. 
If your APP.php already has custom code, it leaves that file alone and tells you what to add by hand. 

sudo sh install.sh --uninstall removes the theme and restores the backup.

**By hand:** sudo cp -r 7.0/* /usr/share/zabbix/, using the folder for your version.

Then pick it under User settings → Profile → Theme, or set it for everyone under Administration → General → GUI.

Things to know:

Versions without their own build: 6.2/6.4 use the 6.0 build and 7.2 uses the 7.0 build.
They should be close, but I didn’t build those versions separately.
