# system-clock-accuracy-test
System clock accuracy test.
1. Boot from Ubuntu LiveCD or use any Unix OS.
2. 
3. Install chrony:
$ sudo apt install chrony -y

3. Run:
$ sysctl start chronyd
$ chronyc tracking

4. Output example:
Reference ID    : 3E95001E (ntp.time.in.ua)
Stratum         : 2
Ref time (UTC)  : Tue Oct 26 13:24:19 2021
System time     : 0.000057122 seconds slow of NTP time
Last offset     : -0.000021978 seconds
RMS offset      : 0.000132849 seconds
Frequency       : 28.697 ppm fast
Residual freq   : -0.000 ppm
Skew            : 0.078 ppm
Root delay      : 0.002510945 seconds
Root dispersion : 0.001537560 seconds
Update interval : 1030.8 seconds
Leap status     : Normal

5. You may have to wait up to 5 minutes to get more accurate results. 
Frequency       : 28.697 ppm fast
This value means that our system clock is 0.0028697 % faster than reference clock on ntp server (ntp.time.in.ua), with measurement error (skew) 0.078 ppm (0.0000078 %). In a 24 hours our system clock runs on:
84600(seconds per day) * 0.0028697 % = 2.43 seconds faster than reference clock.






