Automated testing framework
===========================

This document provides detailed information on the Automated testing framework
we use to evaluate the efficiency and performance of PEP-DNA of PEP-DNA.
The framework consists of 6 bash scripts:

* 'param.sh' contains all the necessary information about testing environments.
   The user can setup a physical or virtual testbed. Variables in this files store
   the information about the IP addresses of the nodes, connected interfaces, TCP
   listening port of PEP-DNA and applications, etc. This file contains the only input
   that the user should enter to run the experiments.

* 'config.sh' contains the functions that are called to configure Linux hosts in the network.
   Configurations include static routes, iptables, ethernet speeds, TCP MSS, buffer sizes,
   sysctl variables, etc.

* 'util.sh' prepares the hosts by calling the functions defined in 'config.sh',
   loads RINA modules, starts the enrollment phase if necessary, load PEP-DNA module, etc.

* 'apps.sh' contains functions that start the client and server applications. For the experiments
   in the paper, 3 main applications are used:
   - CPUMEMPERF(): measures the CPU Utilization and Memory Usage.
   - UPLOAD(): measures the throughput during a file transfer from the client to the server
   - MYHTTTPING(): measure all latency results.

* 'run.sh' contains the setup of the different scenarios used in the paper.
   - TCP
   - TCP - TCP (using PEPDNA)
   - TCP - TCP (using a User-Space Proxy)
   - TCP - RINA (using PEPDNA)

* 'main.sh' has the main functions that the user need to run. Enable or Disable an experiment
   by commenting or uncommenting a line in this file.


Testing environments and Topologies
====================================
====================================

Here...
