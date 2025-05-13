# TestInternetConnectionIperf

I've establised an iperf3-Server. You can accecc the server with "202.61.247.117 tcp\31415" or ""202.61.247.117 udp\31415" to check the bandwith and latency of any given iperf3 client. The IP Adress is also useful for the Monitoring-Gateway adress on your router via ICMP\echo

#TestUploadSpeedTCP
#iperf3 -c 202.61.247.117 -p 31415 -P 10 |grep -E "sender|receiver"

#TestDownloadSpeedTCP
#iperf3 -c 202.61.247.117 -p 31415 -P 10 -R |grep -E "sender|receiver"

#TestJitterDatagramUDP
#iperf3 -c 202.61.247.117 -p 31415 -P 10 -u -t 10 -b 1M -l 1000 |grep -E "sender|receiver|Lost"
