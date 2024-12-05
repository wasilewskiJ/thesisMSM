# RESULTS OF CONDUCTED MEASUREMENTS #


## XDELTA AND LINUX ## 


| CHANGES | DELTA SIZE | MEAN ENCODE TIME (s) | MEAN DECODE TIME (s) |   STDDEV  |   MEDIAN |
| ---     |   ---      |       :---:          |     ---              |   ---     |   ---    |
| A       |  47  KB    |        01.298        |                      |   0.013   |  14.519  |
| B       |  58  KB    |        01.867        |                      |   0.013   |  14.512  |
| C       |  5.9 MB    |		04.490        |                      |   0.036   |  15.007  |
| D       |   90 MB    |        39.157        |                      |   0.428   |  20.426  |
| E       |   33 MB    |        16.470        |                      |   0.294   |  19.838  |
| F       |  320 KB    |        01.962        |                      |   0.023   |  14.557  |
| G		  |   65 KB    |        01.881        |						 |    0.02   |  14.518  |
| H		  |   71 MB    |        36.018        |					     |   0.040   |  28.980  |
| I		  |   57 KB    |        01.845        |                      |   0.018   |  14.524  |
| J		  |   32 MB    |        16.732        |                      |   0.350   |  20.319  |
| K		  |   57 KB    |        01.882        |                      |   0.020   |  14.560  |
| L	      |   71 MB    |        35.971        |                      |   0.305   |  33.680  |
| M       |   469 MB   |        148.589
| P       |  2.0 GB    |        576.432             |         
| ~A	  |            |                |                      |   0.016   |  14.494  |
| ~B      |            |                |                      |   0.015   |  14.493  |
| ~C      |            |                |                      |   0.017   |  14.527  |
| ~D      |            |                |                      |   0.015   |  14.551  |
| ~E      |            |                |                      |   0.313   |  19.339  |
| ~F      |            |                |                      |   0.020   |  14.485  |
| ~G      |            |                |						 |   0.035   |  14.875  |
| ~H      |            |                |                      |   0.020   |  18.636  |
| ~I      |            |                |                      |   0.028   |  14.490	|
| ~J      |            |                |                      |   0.248   |  20.127  |
| ~K      |            |                |                      |   0.023   |  14.562  |
| ~L      |            |                |                      |   0.227   |  24.360  |


CHANGES EXPLAINED:
* A - (main to motd) -> e of text to MOTD file (exactly 34 chars, which is    
	equal to 34 BYTES)
* B - (main to mockdriver) -> Adding a dummy mock driver, which .ko executable after compilation			 weighed exactly 5.3MB
* C - (main to packages) -> adding several packages to kernel (exactly 6 packages - openssl, iptables,
	gdb, strace, mosquitto, lsof)
* D - (main to packages big) adding several packages to kernel (exactly 28 different packages, 
	more details in repo on packages-big branch)
* E - (kernel to main) -> linux kernel update (linux-mainline 5.15.0 -> linux-mainline 5.17.0)
* F - (main to packets_mockdriver) -> added mockdriver from scenario B and two packages (openssl and 
	iptables)
* G - (packages to packets_mockdriver) -> removed few packages and added mockdriver from scenario B
* H - (main to fewpackages) -> added 1GB bubary and 3 packages ( opennsl, iptables, gdb)
* I - (mock_driver to motd) -> removed mock driver and added one line of text to MOTD (34 B)
* J - (packages to kernel) -> removed 6 packages and downgraded kernel 5.17 -> 5.15
* K -  (packets_mockdriver to mock_driver) removed 2 packages (openssl and iptables) 
* L - (kernel to fewpackages) upgrade kernel 5.15 -> 5.17 and add 3 packages (openssl, iptables, gdb)



xdelta3 na P - 9minut 36 sekund, 2.0G delta


CHANGES WITH `~` mark, means that it's reversed version. Source file became target file
