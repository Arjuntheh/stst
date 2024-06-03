pwd 
csh
source /home/install/cshrc
mkdir inv
cd inv
vi inv.v
vi inv_tb.v
vi cds.lib
	define inv_lib ./inv.lib
mkdir inv.lib
vi hdl.var
	define WORK inv_lib
ncvlog inv.v -mess 
ncvlog inv_tb.v -mess 
ncelab inv_tb -access +rwc -mess
ncsim inv_tb -gui
