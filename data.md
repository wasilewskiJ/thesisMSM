# RESULTS OF CONDUCTED MEASUREMENTS #

## FDELTA AND LINUX ## 


| CHANGES | DELTA SIZE | MEAN ENCODE TIME (s) | MEAN DECODE TIME (s) |   STDDEV  |   MEDIAN |
| ---     |   ---      |       :---:          |     ---              |   ---     |   ---    |
| A       |  558 KB    |       27.920         |       2.78               |  0.088    |  27.963  |
| B       |  570 KB    |       27.871         |       2.79               |  0.086    |  27.905  |
| C       |  13  MB    |       32.928         |       2.78               |  0.108    |  32.939  |
| D       |  185 MB    |       139.000        |       2.81               |  0.208    |  139.164 |
| E       |  100 MB    |       131.987        |       2.86               |  0.334    |  131.603 |
| F		  |  1.2 MB    |       28.319         |		3.06				 |  0.055    |  28.243  |
| G		  |  615 KB    |       27.728         |		2.78			     |  0.061    |  27.636  |
| H		  |  13  MB    |       173.895        |             2.81         |  0.329    |  174.576 |
| I		  |  596 KB    |       27.984         |             2.78         |  0.076    |   28.075 |
| J		  |  102 MB    |       132.967        |               6.29       |  0.234    |  133.019 |
| K		  |  573 KB    |       27.812         |               3.05       |  0.062    |   27.810 |
| L		  |  112 MB    |       277.929        |               2.78       |  0.320    |  277.557 |
| M       |  460 MB    |       310.893        |        6.26              | 0.045     |  311.002 |
| N       |  779 MB    |       479.887        |        6.17              | 0.112     |  478.289 |
| P       |  2.0 GB    |       912.797        |        14.138              | 0.091     |  913.251 |
| ~A      |  530 KB    |       27.741         |   2.78                   |  0.060    |  27.724  |
| ~B      |  568 KB    |       27.802         |   2.77                   |  0.080    |  27.797  |
| ~C      |  574 KB    |       27.825         |   2.77                   |  0.068    |  27.777  |
| ~D      |  762 KB    |       44.253         |   2.81                   |  0.086    |  44.260  |
| ~E      |  102 MB    |       130.620        |   3.06                   |  0.247    |  130.900 |
| ~F      |  577 KB    |       27.807         |   2.79				 |  0.063    |  27.838  |
| ~G      |  13 MB     |       32.274         |     2.79                 |  0.071    |  32.350  |
| ~H      |  608 KB    |       30.999         |       2.77               |  0.032    |  30.998  |
| ~I      |  570 KB    |       27.798         |      2.80                |  0.060    |  27.720  |
| ~J      |  113 MB    |       137.056        |      4.07                |  0.232    |  137.355 |
| ~K      |  1.2 MB    |       28.286         |      2.79                |  0.049    |  28.239  |
| ~L      |   96 MB    |       87.716         |      3.06                |  0.110    |  87. 596 |


CHANGES EXPLAINED:
* A - (main to motd) -> Adding one line of text to MOTD file (exactly 34 chars, which is    
	equal to 34 BYTES)
* B - (main to mockdriver) -> Adding a dummy mock driver, which .ko executable after compilation			 weighed exactly 5.3KB
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
* M - added ~366 MB .mp4 video, along with 3 gstreamer packages, ffmpeg, weston wayland and gtk+3.
* N - added ~735 MB .zip with images
* P - added 1.2GB Yolo model along with ~775 MB images dataset, compressed in zip
  
CHANGES WITH `~` mark, means that it's reversed version. Source file became target file
