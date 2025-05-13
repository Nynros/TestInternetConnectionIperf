# TestInternetConnectionIperf

I've establised an iperf3-Server. You can accecc the server with "202.61.247.117 tcp\31415" to check the bandwith and latency of any given iperf3 client 
The IP Adress is also useful for the Monitoring-Gateway adress on your router

#TestUploadSpeedTCP
#iperf3 -c 202.61.247.117 -p 31415 -P 10 

[nynros@deepthought ~]$ iperf3 -c 202.61.247.117 -p 31415 -P 10 |grep -E "sender|receiver"
[  5]   0.00-10.00  sec  4.98 MBytes  4.17 Mbits/sec   17             sender
[  5]   0.00-10.26  sec  3.25 MBytes  2.66 Mbits/sec                  receiver
[  7]   0.00-10.00  sec  5.33 MBytes  4.47 Mbits/sec   16             sender
[  7]   0.00-10.26  sec  3.12 MBytes  2.56 Mbits/sec                  receiver
[  9]   0.00-10.00  sec  4.87 MBytes  4.09 Mbits/sec   13             sender
[  9]   0.00-10.26  sec  3.12 MBytes  2.56 Mbits/sec                  receiver
[ 11]   0.00-10.00  sec  3.54 MBytes  2.97 Mbits/sec   15             sender
[ 11]   0.00-10.26  sec  3.12 MBytes  2.56 Mbits/sec                  receiver
[ 13]   0.00-10.00  sec  4.58 MBytes  3.84 Mbits/sec   10             sender
[ 13]   0.00-10.26  sec  3.12 MBytes  2.56 Mbits/sec                  receiver
[ 15]   0.00-10.00  sec  4.96 MBytes  4.16 Mbits/sec    8             sender
[ 15]   0.00-10.26  sec  3.12 MBytes  2.56 Mbits/sec                  receiver
[ 17]   0.00-10.00  sec  3.22 MBytes  2.70 Mbits/sec   14             sender
[ 17]   0.00-10.26  sec  3.12 MBytes  2.56 Mbits/sec                  receiver
[ 19]   0.00-10.00  sec  3.58 MBytes  3.00 Mbits/sec   12             sender
[ 19]   0.00-10.26  sec  3.12 MBytes  2.56 Mbits/sec                  receiver
[ 21]   0.00-10.00  sec  5.06 MBytes  4.25 Mbits/sec   10             sender
[ 21]   0.00-10.26  sec  3.12 MBytes  2.56 Mbits/sec                  receiver
[ 23]   0.00-10.00  sec  4.21 MBytes  3.53 Mbits/sec   12             sender
[ 23]   0.00-10.26  sec  3.12 MBytes  2.56 Mbits/sec                  receiver
[SUM]   0.00-10.00  sec  44.3 MBytes  37.2 Mbits/sec  127             sender
[SUM]   0.00-10.26  sec  31.4 MBytes  25.7 Mbits/sec                  receiver
[nynros@deepthought ~]$ 


#TestDownloadSpeedTCP
#iperf3 -c 202.61.247.117 -p 31415 -P 10 -R

[nynros@deepthought ~]$ iperf3 -c 202.61.247.117 -p 31415 -P 10 -R |grep -E "sender|receiver"
[  5]   0.00-10.09  sec  56.6 MBytes  47.0 Mbits/sec  3391             sender
[  5]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[  7]   0.00-10.09  sec  66.6 MBytes  55.3 Mbits/sec  1511             sender
[  7]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[  9]   0.00-10.09  sec  60.1 MBytes  50.0 Mbits/sec  2818             sender
[  9]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[ 11]   0.00-10.09  sec  70.9 MBytes  59.0 Mbits/sec  3706             sender
[ 11]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[ 13]   0.00-10.09  sec  68.4 MBytes  56.8 Mbits/sec  3706             sender
[ 13]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[ 15]   0.00-10.09  sec  60.2 MBytes  50.1 Mbits/sec  2876             sender
[ 15]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[ 17]   0.00-10.09  sec  60.0 MBytes  49.9 Mbits/sec  3013             sender
[ 17]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[ 19]   0.00-10.09  sec  62.9 MBytes  52.3 Mbits/sec  3871             sender
[ 19]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[ 21]   0.00-10.09  sec  71.1 MBytes  59.1 Mbits/sec  4119             sender
[ 21]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[ 23]   0.00-10.09  sec  67.8 MBytes  56.4 Mbits/sec  1663             sender
[ 23]   0.00-10.01  sec  27.8 MBytes  23.3 Mbits/sec                  receiver
[SUM]   0.00-10.09  sec   645 MBytes   536 Mbits/sec  30674             sender
[SUM]   0.00-10.01  sec   278 MBytes   233 Mbits/sec                  receiver
[nynros@deepthought ~]$ 

#TestJitterDatagramUDP
#iperf3 -c 202.61.247.117 -p 31415 -P 10 -u -t 10 -b 1M -l 1000 |grep -E "sender|receiver|Lost"

[nynros@deepthought ~]$ iperf3 -c 202.61.247.117 -p 31415 -P 10 -u -t 10 -b 1M -l 1000 |grep -E "sender|receiver|Lost"
[ ID] Interval           Transfer     Bitrate         Jitter    Lost/Total Datagrams
[  5]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[  5]   0.00-10.08  sec  1.19 MBytes   990 Kbits/sec  2.409 ms  3/1250 (0.24%)  receiver
[  7]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[  7]   0.00-10.08  sec  1.19 MBytes   991 Kbits/sec  2.212 ms  2/1250 (0.16%)  receiver
[  9]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[  9]   0.00-10.08  sec  1.19 MBytes   991 Kbits/sec  2.230 ms  2/1250 (0.16%)  receiver
[ 11]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[ 11]   0.00-10.08  sec  1.19 MBytes   991 Kbits/sec  2.366 ms  2/1250 (0.16%)  receiver
[ 13]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[ 13]   0.00-10.08  sec  1.19 MBytes   991 Kbits/sec  2.680 ms  2/1250 (0.16%)  receiver
[ 15]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[ 15]   0.00-10.08  sec  1.19 MBytes   991 Kbits/sec  2.629 ms  2/1250 (0.16%)  receiver
[ 17]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[ 17]   0.00-10.08  sec  1.19 MBytes   991 Kbits/sec  2.574 ms  2/1250 (0.16%)  receiver
[ 19]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[ 19]   0.00-10.08  sec  1.19 MBytes   991 Kbits/sec  2.979 ms  2/1250 (0.16%)  receiver
[ 21]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[ 21]   0.00-10.08  sec  1.19 MBytes   991 Kbits/sec  2.662 ms  2/1250 (0.16%)  receiver
[ 23]   0.00-10.00  sec  1.19 MBytes  1000 Kbits/sec  0.000 ms  0/1250 (0%)  sender
[ 23]   0.00-10.08  sec  1.19 MBytes   991 Kbits/sec  3.301 ms  2/1250 (0.16%)  receiver
[SUM]   0.00-10.00  sec  11.9 MBytes  10.0 Mbits/sec  0.000 ms  0/12500 (0%)  sender
[SUM]   0.00-10.08  sec  11.9 MBytes  9.91 Mbits/sec  2.604 ms  21/12500 (0.17%)  receiver
[nynros@deepthought ~]$ 
