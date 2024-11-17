# RESULTS OF CONDUCTED MEASUREMENTS #


### images explained (in relation to main image) ###

- fewpackages is 5.17 kernel with binary file and 3 packages added ( openssl, iptables, gdb )
- packets_mockdriver contains mock_driver and 2 packages (openssl, iptables)


## LIBRSYNC AND LINUX ## 

(zaokraglalem do 3 liczb znaczacych, czyli zawsze w gore ostatnie liczbe, np 23.432432 do 23.433)

| CHANGES | DELTA SIZE | MEAN ENCODE TIME (s) | MEAN DECODE TIME (s) |   STDDEV  |   MEDIAN |
| ---     |   ---      |       :---:          |     ---              |   ---     |   ---    |
| A       |  3.5 MB    |        14.508        |                      |   0.012   |  14.518  |
| B       |  4.0 MB    |        14.519        |                      |   0.012   |  14.511  |
| C       |  19  MB    |        14.957        |                      |   0.036   |  15.006  |
| D       |  212 MB    |        21.143        |                      |   0.428   |  20.426  |
| E       |  173 MB    |        19.759        |                      |   0.293   |  19.838  |
| F       |  5.2 MB    |        14.563        |                      |   0.022   |  14.556  |
| G		  |  4.0 MB    |        14.527        |						 |    0.02   |  14.518  |
| H		  |  20 MB     |        28.97         |					     |   0.039   |  28.98   |
| I		  |  4.0  MB   |        14.522        |                      |   0.017   |  14.524  |
| J		  |  175 MB    |        19.904        |                      |   0.349   |  20.318  |
| K		  |  3.9 MB    |        14.525        |                      |   0.019   |  14.55   |
| L	      |  190 MB    |        34.141        |                      |   0.304   |  33.679  |
| ~A	  |  3.5 MB    |        14.533        |                      |   0.028   |  14.49   |
| ~B      |  4.0 MB    |        14.503        |                      |   0.015   |  14.494  |
| ~C      |  4.0 MB    |       27.802         |                      |  0.080    |  27.797  |
| ~D      |  4.0 MB    |       27.825         |                      |  0.068    |  27.777  |
| ~E      |  174 MB    |       44.253         |                      |  0.086    |  44.260  |
| ~F      |  4.0 MB    |       130.620        |                      |  0.247    |  130.900 |
| ~G      |  17  MB    |        14.527        |						 |    0.02   |  14.518  |
| ~H      |  4.1 MB    |       32.274         |                      |  0.071    |  32.350  |
| ~I      |  4.0 MB    |        14.519        |                      |   0.012   |  14.511  |
| ~J      |  188 MB    |        19.904        |                      |   0.349   |  20.318  |
| ~K      |  5.2 MB    |        14.517        |                      |    0.02   |  14.485  |
| ~L      |  175 MB    |        34.141        |                      |   0.304   |  33.679  |


CHANGES EXPLAINED:
* A - (main to motd) -> Adding one line of text to MOTD file (exactly 34 chars, which is    
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

CHANGES WITH `~` mark, means that it's reversed version. Source file became target file
