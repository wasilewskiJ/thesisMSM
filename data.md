# RESULTS OF CONDUCTED MEASUREMENTS #


### images explained (in relation to main image) ###

- fewpackages is 5.17 kernel with binary file and 3 packages added ( openssl, iptables, gdb )
- packets_mockdriver contains mock_driver and 2 packages (openssl, iptables)


## LIBRSYNC AND LINUX ## 

(zaokraglalem do 3 liczb znaczacych, czyli zawsze w gore ostatnie liczbe, np 23.432432 do 23.433)

| CHANGES | DELTA SIZE | MEAN ENCODE TIME (s) | MEAN DECODE TIME (s) |   STDDEV  |   MEDIAN |
| ---     |   ---      |       :---:          |     ---              |   ---     |   ---    |
| A       |  3.5 MB    |        14.508        |                      |   0.013   |  14.519  |
| B       |  4.0 MB    |        14.520        |                      |   0.013   |  14.512  |
| C       |  19  MB    |        14.958        |                      |   0.036   |  15.007  |
| D       |  212 MB    |        21.144        |                      |   0.428   |  20.426  |
| E       |  173 MB    |        19.760        |                      |   0.294   |  19.838  |
| F       |  5.2 MB    |        14.563        |                      |   0.023   |  14.557  |
| G		  |  4.0 MB    |        14.528        |						 |    0.02   |  14.518  |
| H		  |  20 MB     |        28.970        |					     |   0.040   |  28.980  |
| I		  |  4.0  MB   |        14.523        |                      |   0.018   |  14.524  |
| J		  |  175 MB    |        19.905        |                      |   0.350   |  20.319  |
| K		  |  3.9 MB    |        14.526        |                      |   0.020   |  14.560  |
| L	      |  190 MB    |        34.142        |                      |   0.305   |  33.680  |
| ~A	  |  3.5 MB    |        14.503        |                      |   0.016   |  14.494  |
| ~B      |  4.0 MB    |        14.521        |                      |   0.015   |  14.493  |
| ~C      |  4.0 MB    |        14.516        |                      |   0.017   |  14.527  |
| ~D      |  4.0 MB    |        14.544        |                      |   0.015   |  14.551  |
| ~E      |  174 MB    |        19.821        |                      |   0.313   |  19.339  |
| ~F      |  4.0 MB    |        14.517        |                      |   0.020   |  14.485  |
| ~G      |  17  MB    |        14.921        |						 |   0.035   |  14.875  |
| ~H      |  4.1 MB    |        18.639        |                      |   0.020   |  18.636  |
| ~I      |  4.0 MB    |        14.533        |                      |   0.028   |  14.490	|
| ~J      |  188 MB    |        20.166        |                      |   0.248   |  20.127  |
| ~K      |  5.2 MB    |        14.559        |                      |   0.023   |  14.562  |
| ~L      |  175 MB    |        24.145        |                      |   0.227   |  24.360  |


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
