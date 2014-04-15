cgminer modified for the Jaguar FPGA miner project.
The miner is developed on xilinx KC705 board.

how to use:
1. download the cgminer from: https://github.com/ckolivas/cgminer
2. replace the driver-icarus.c with this file in the project
3. run ./autogen & ./configure.sh --enable-icarus & make
4. sudo make install
5. install the CP210x USB-UART bridge driver, downloaded from SiliconImage web
6. to mine btc, here we go: cgminer --config cgminer.conf --usb 1
7. cgminer.conf:
{
"pools" : [
        {
                "url" : "stratum.btcguild.com:3333",
                "user" : "shingbo_a",
                "pass" : "x"
        }
]
,
   "api-listen" : true,
   "api-port" : "4028",
   "expiry" : "120",
   "failover-only" : true,
   "log" : "5",
   "no-pool-disable" : true,
   "queue" : "2",
   "scan-time" : "60",
   "worktime" : true,
   "shares" : "0",
   "kernel-path" : "/usr/local/bin",
   "api-allow" : "0/0",
   "icarus-options" : "115200:1:1",
   "icarus-timing" : "2.5=100"
}

