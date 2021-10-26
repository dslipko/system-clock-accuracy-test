# system-clock-accuracy-test
System clock accuracy test.
<ol>
<li class="has-line-data" data-line-start="0" data-line-end="1">
<p class="has-line-data" data-line-start="0" data-line-end="1">Boot from Ubuntu LiveCD or use any Unix OS.</p>
</li>
<li class="has-line-data" data-line-start="1" data-line-end="3">
<p class="has-line-data" data-line-start="1" data-line-end="3">Install chrony:<br>
$ sudo apt install chrony -y</p>
</li>
<li class="has-line-data" data-line-start="3" data-line-end="7">
<p class="has-line-data" data-line-start="3" data-line-end="6">Run:<br>
$ sysctl start chronyd<br>
$ chronyc tracking</p>
</li>
<li class="has-line-data" data-line-start="7" data-line-end="22">
<p class="has-line-data" data-line-start="7" data-line-end="21">Output example:<br>
Reference ID    : 3E95001E (<a href="http://ntp.time.in.ua">ntp.time.in.ua</a>)<br>
Stratum         : 2<br>
Ref time (UTC)  : Tue Oct 26 13:24:19 2021<br>
System time     : 0.000057122 seconds slow of NTP time<br>
Last offset     : -0.000021978 seconds<br>
RMS offset      : 0.000132849 seconds<br>
Frequency       : 28.697 ppm fast<br>
Residual freq   : -0.000 ppm<br>
Skew            : 0.078 ppm<br>
Root delay      : 0.002510945 seconds<br>
Root dispersion : 0.001537560 seconds<br>
Update interval : 1030.8 seconds<br>
Leap status     : Normal</p>
</li>
<li class="has-line-data" data-line-start="22" data-line-end="26">
<p class="has-line-data" data-line-start="22" data-line-end="26">You may have to wait up to 5 minutes to get more accurate results.<br>
Frequency       : 28.697 ppm fast [1]<br>
This value means that our system clock is 0.0028697 % faster than reference clock on ntp server (<a href="http://ntp.time.in.ua">ntp.time.in.ua</a>), with measurement error (skew) 0.078 ppm (0.0000078 %). In a 24 hours our system clock runs on:<br>
84600(seconds per day) * 0.0028697 % = 2.43 seconds faster than reference clock.  [2]</p>
</li>
</ol>
<p class="has-line-data" data-line-start="28" data-line-end="32">Notes:<br>
[1] -  Frequency - The ‘frequency’ is the rate by which the system’s clock would be wrong if chronyd was not correcting it. It is expressed in ppm (parts per million). For example, a value of 1 ppm would mean that when the system’s clock thinks it has advanced 1 second, it has actually advanced by 1.000001 seconds relative to true time.<br>
Skew - This is the estimated error bound on the frequency.<br>
(<a href="https://chrony.tuxfamily.org/doc/2.4/chronyc.html">https://chrony.tuxfamily.org/doc/2.4/chronyc.html</a>)</p>
<p class="has-line-data" data-line-start="33" data-line-end="34">[2] -  <a href="http://www.ntp.org/ntpfaq/NTP-s-sw-clocks-quality.htm">http://www.ntp.org/ntpfaq/NTP-s-sw-clocks-quality.htm</a></p>
