# RESULTS OF CONDUCTED MEASUREMENTS #


### images explained (in relation to main image) ###

- fewpackages is 5.17 kernel with binary file and 3 packages added ( openssl, iptables, gdb )
- packets_mockdriver contains mock_driver and 2 packages (openssl, iptables)


## LIBRSYNC AND LINUX ## 

(zaokraglalem do 3 liczb znaczacych, czyli zawsze w gore ostatnie liczbe, np 23.432432 do 23.433)

| CHANGES | DELTA SIZE | MEAN ENCODE TIME (s) | MEAN DECODE TIME (s) |   STDDEV  |   MEDIAN |
| ---     |   ---      |       :---:          |     ---              |   ---     |   ---    |
| A       |  3.5 MB    |       27.920         |                      |  0.088    |  27.963  |
| B       |  4.0 MB    |       27.871         |                      |  0.086    |  27.905  |
| C       |  19  MB    |                      |                      |           |          |
| D       |  212 MB    |       32.928         |                      |  0.108    |  32.939  |
| E       |  173 MB    |       139.000        |                      |  0.208    |  139.164 |
| F       |  5.2 MB    |       131.987        |                      |  0.334    |  131.603 |
| G		  |  4.0 MB    |       28.319         |						 |  0.055    |  28.243  |
| H		  |  20 MB     |       27.728         |					     |  0.061    |  27.636  |
| I		  |  4.0  MB   |       173.895        |                      |  0.329    |  174.576 |
| J		  |  175 MB    |       27.984         |                      |  0.076    |   28.075 |
| K		  |  3.9 MB    |       132.967        |                      |  0.234    |  133.019 |
| L	      |  190 MB    |       27.812         |                      |  0.062    |   27.810 |
| ~A	  |  3.5 MB    |       277.929        |                      |  0.320    |  277.557 |
| ~B      |  4.0 MB    |       27.741         |                      |  0.060    |  27.724  |
| ~C      |  4.0 MB    |       27.802         |                      |  0.080    |  27.797  |
| ~D      |  4.0 MB    |       27.825         |                      |  0.068    |  27.777  |
| ~E      |  174 MB    |       44.253         |                      |  0.086    |  44.260  |
| ~F      |  4.0 MB    |       130.620        |                      |  0.247    |  130.900 |
| ~G      |  17  MB    |       27.807         |						 |  0.063    |  27.838  |
| ~H      |  4.1 MB    |       32.274         |                      |  0.071    |  32.350  |
| ~I      |  4.0 MB    |       30.999         |                      |  0.032    |  30.998  |
| ~J      |  188 MB    |       27.798         |                      |  0.060    |  27.720  |
| ~K      |  5.2 MB    |       137.056        |                      |  0.232    |  137.355 |
| ~L      |  175 MB    |       28.286         |                      |  0.049    |  28.239  |


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
