# SNMP Simulation using GNS3
  Capturing the SNMPv2 agents logs details and activities on the window VM Manager

  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/whole_overview.png)

  ## Table of Contents
  
  -[Environment setup](#environment-setup)

  - [Network topology](#network-topology)
  - [configure IP to SNMP Manager](#configure-ip-to-snmp-manager)
  - [MIB browser setup](#mib-setup)
  - [Wireshark setup](#wireshark)


  ## Environment setup
  ### Network topology
  Create a networ topology with SNMP Manager and SNMP agent
  configure the Ip address and default Gateway
  After configuration, run the whole topology
  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/GNS3_%20topology.png)
  
  ## configure IP to SNMP Manager
  
  First configure the IP address of SNMP Manager(window vm)
   -Go to connection properties and in (IPv4/TCP)
 ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/ipv4.properties.png)
 
   Then configure the manual IP and DNS
  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/assign.IP.png)

  now, check the connectivity over the network topology in GNS3( ping the router)
  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/ping.192.168.1.1.png)

  ## MIB browser setup
  Open the mib browser as administration
  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/MIB.RUN.png)

  now, you are at the mib interface, go to tools and trap receiver
  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/MIB.interface.png)

  Go to the GNS3 and run the vlan command in S1 (SNMP AGNET)
  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/switch_assign_vlan.png)

  Again , go the MIB interface , where you will see the capture log from S1 agent
  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/expand_MIB.png)

To capture SNMP traffic in wireshark, go to tools section and then in options
 ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/tool_options.png)
  
Then select the defalut gateway in Address section , expand the MIB tree, select ip AddrTable
Next, go to Opertions sectiona nd select "Get Bulk"

![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/get_bulk().png)

YOU can get the same output in the wireshark  
  
  ## Wireshark setup
  Open the wireshark and filter to SNMP

  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/snmp-wireshark%2C().png)

  Expand the getBulkRequest 
  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/wireshar_expand.png)


  Now, you can compare the outcome of wireshark and MIB browser> wich is the same value

  ![Alt Text](https://github.com/santosholi01/SNMP-Simulation-Using-GNS3/blob/54fd46705fbf00a5d5cc761adc5d7e46f5034b27/compare_MIB-WIRESHARK.png)
  
    
