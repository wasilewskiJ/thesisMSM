# RESULTS OF CONDUCTED MEASUREMENTS #

## FDELTA AND LINUX ## 


| CHANGES | DELTA SIZE | MEAN ENCODE TIME (s) | STDDEV (FOR ENC) | MEDIAN (FOR ENC) | MEAN DECODE TIME (s) | STDDEV (FOR DEC) | MEDIAN (FOR DEC) |
| ---     |   ---      |       :---:          |       :---:      |       :---:      |       :---:          |       :---:      |       :---:      |
| A       |  558 KB    |       27.920         |      0.088       |      27.963      |         2.780        |      0.090       |      2.785       |
| B       |  570 KB    |       27.871         |      0.086       |      27.905      |         2.790        |      0.085       |      2.795       |
| C       |   13 MB    |       32.928         |      0.108       |      32.939      |         2.780        |      0.100       |      2.790       |
| D       |  185 MB    |      139.000         |      0.208       |     139.164      |         2.810        |      0.220       |      2.805       |
| E       |  100 MB    |      131.987         |      0.334       |     131.603      |         2.860        |      0.360       |      2.870       |
| F       |   1.2 MB   |       28.319         |      0.055       |      28.243      |         3.060        |      0.058       |      3.050       |
| G       |  615 KB    |       27.728         |      0.061       |      27.636      |         2.780        |      0.065       |      2.775       |
| H       |   13 MB    |      173.895         |      0.329       |     174.576      |         2.810        |      0.340       |      2.800       |
| I       |  596 KB    |       27.984         |      0.076       |      28.075      |         2.780        |      0.070       |      2.790       |
| J       |  102 MB    |      132.967         |      0.234       |     133.019      |         6.290        |      0.250       |      6.300       |
| K       |  573 KB    |       27.812         |      0.062       |      27.810      |         3.050        |      0.065       |      3.040       |
| L       |  112 MB    |      277.929         |      0.320       |     277.557      |         2.780        |      0.310       |      2.790       |
| M       |  460 MB    |      310.893         |      0.045       |     311.002      |         6.260        |      0.050       |      6.255       |
| N       |  779 MB    |      479.887         |      0.112       |     478.289      |         6.170        |      0.115       |      6.150       |
| P       |   2.0 GB   |      912.797         |      0.091       |     913.251      |        14.138        |      0.095       |     14.150       |
| ~A      |  530 KB    |       27.741         |      0.060       |      27.724      |         2.780        |      0.062       |      2.775       |
| ~B      |  568 KB    |       27.802         |      0.080       |      27.797      |         2.770        |      0.085       |      2.765       |
| ~C      |  574 KB    |       27.825         |      0.068       |      27.777      |         2.770        |      0.070       |      2.780       |
| ~D      |  762 KB    |       44.253         |      0.086       |      44.260      |         2.810        |      0.090       |      2.800       |
| ~E      |  102 MB    |      130.620         |      0.247       |     130.900      |         3.060        |      0.260       |      3.050       |
| ~F      |  577 KB    |       27.807         |      0.063       |      27.838      |         2.790        |      0.065       |      2.785       |
| ~G      |   13 MB    |       32.274         |      0.071       |      32.350      |         2.790        |      0.075       |      2.795       |
| ~H      |  608 KB    |       30.999         |      0.032       |      30.998      |         2.770        |      0.035       |      2.765       |
| ~I      |  570 KB    |       27.798         |      0.060       |      27.720      |         2.800        |      0.058       |      2.805       |
| ~J      |  113 MB    |      137.056         |      0.232       |     137.355      |         4.070        |      0.240       |      4.080       |
| ~K      |   1.2 MB   |       28.286         |      0.049       |      28.239      |         2.790        |      0.050       |      2.800       |
| ~L      |   96 MB    |       87.716         |      0.110       |      87.596      |         3.060        |      0.115       |      3.070       |



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
