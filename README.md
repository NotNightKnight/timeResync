# timeRsync
Time rsync bat file for rsyncing time automatically for older computers.

This thing builded from several website forums comments.Unfortunately
I didn't take notes of where did I took :( So I can't reference.

"net start W32Time" ->  starts windows32 Time service

"w32tm /config /manualpeerlist:"time.windows.com,0x1"
/syncfromflags:manual /reliable:yes /update"
-> connects the time server, could change site if wish.

"w32tm /config /update" ->  updates settings.

"net stop w32time && net start w32time" ->  restarting time service.

"w32tm /resync /force"  ->  syncs time, "/force" is important. 
In some cases an error occurs for time 
that need syncing is too long. It avoids it.

"w32tm /config /syncfromflags:domhier /update"  ->  domain controller
