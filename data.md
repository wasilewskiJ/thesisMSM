# RESULTS OF CONDUCTED MEASUREMENTS #


## LIBRSYNC AND LINUX ## 

| CHANGES | DELTA SIZE | MEAN ENCODE TIME (s) | STDDEV (FOR ENC) | MEDIAN (FOR ENC) | MEAN DECODE TIME (s) | STDDEV (FOR DEC) | MEDIAN (FOR DEC) |
| ---     |   ---      |       :---:          |       :---:      |       :---:      |       :---:          |       :---:      |       :---:      |
| A       |  3.5 MB    |        14.508        |      0.013       |      14.519      |         0.5882       |      0.020       |      0.585       |
| B       |  4.0 MB    |        14.520        |      0.013       |      14.512      |         0.5961       |      0.017       |      0.599       |
| C       |  19 MB     |        14.958        |      0.036       |      15.007      |         0.5937       |      0.045       |      0.590       |
| D       |  212 MB    |        21.144        |      0.428       |      20.426      |         0.5833       |      0.480       |      0.578       |
| E       |  173 MB    |        19.760        |      0.294       |      19.838      |         0.5895       |      0.310       |      0.586       |
| F       |  5.2 MB    |        14.563        |      0.023       |      14.557      |         0.5790       |      0.030       |      0.575       |
| G       |  4.0 MB    |        14.528        |      0.020       |      14.518      |         0.6023       |      0.018       |      0.600       |
| H       |  20 MB     |        28.970        |      0.040       |      28.980      |         1.2376       |      0.050       |      1.242       |
| I       |  4.0 MB    |        14.523        |      0.018       |      14.524      |         0.5899       |      0.025       |      0.584       |
| J       |  175 MB    |        19.905        |      0.350       |      20.319      |         0.5986       |      0.390       |      0.594       |
| K       |  3.9 MB    |        14.526        |      0.020       |      14.560      |         0.5827       |      0.026       |      0.579       |
| L       |  190 MB    |        34.142        |      0.305       |      33.680      |         1.2385       |      0.280       |      1.245       |
| M       |  481 MB    |        43.402        |      0.400       |      43.000      |         1.8500       |      0.390       |      1.843       |
| N       |  782 MB    |        52.114        |      0.500       |      51.900      |         2.1221       |      0.420       |      2.095       |
| P       |  2.0 GB    |       123.711        |      0.800       |     123.500      |         5.1397       |      0.720       |      5.110       |
| ~A      |  3.5 MB    |        14.481        |      0.016       |      14.496      |         0.5953       |      0.023       |      0.598       |
| ~B      |  4.0 MB    |        14.501        |      0.014       |      14.497      |         0.6004       |      0.020       |      0.597       |
| ~C      |  19 MB     |        14.969        |      0.040       |      15.020      |         0.5867       |      0.052       |      0.585       |
| ~D      |  212 MB    |        21.127        |      0.430       |      20.420      |         0.5912       |      0.460       |      0.587       |
| ~E      |  173 MB    |        19.749        |      0.305       |      19.825      |         0.5938       |      0.320       |      0.592       |
| ~F      |  5.2 MB    |        14.578        |      0.028       |      14.570      |         0.5808       |      0.035       |      0.579       |
| ~G      |  4.0 MB    |        14.547        |      0.022       |      14.525      |         0.6062       |      0.021       |      0.608       |
| ~H      |  20 MB     |        28.975        |      0.045       |      29.000      |         1.2407       |      0.062       |      1.238       |
| ~I      |  4.0 MB    |        14.512        |      0.019       |      14.515      |         0.5842       |      0.028       |      0.586       |
| ~J      |  175 MB    |        19.908        |      0.350       |      20.315      |         0.6057       |      0.400       |      0.601       |
| ~K      |  3.9 MB    |        14.541        |      0.024       |      14.564      |         0.5789       |      0.032       |      0.582       |
| ~L      |  190 MB    |        34.160        |      0.310       |      33.668      |         1.2483       |      0.300       |      1.242       |






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



xdelta3 na P - 9minut 36 sekund, 2.0G delta


CHANGES WITH `~` mark, means that it's reversed version. Source file became target file
