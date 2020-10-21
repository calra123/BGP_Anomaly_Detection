BGP_datasets_for_anomaly_detection_csv_revised.zip
----------------------------------------------------------------------
Authors: Zhida Li, Ana Laura Gonzalez Rios, and Ljiljana Trajkovic
Email: {zhidal, anag, ljilja}@sfu.ca
Date: July 30, 2020
Title: Border Gateway Protocol routing records from Reseaux IP Europeens (RIPE) and BCNET
Description: 
Three well-known Border Gateway Anomalies (BGP) anomalies Slammer, Nimda, and Code Red I occurred in January 2003, September 2001, and July 2001, respectively. The Reseaux IP Europeens (RIPE) BGP update messages are publicly available from the Network Coordination Centre (NCC)
and contain Slammer, Nimda, Code Red I, and regular data: https://www.ripe.net/analyse/. Regular data are also collected from BCNET: http://www.bc.net/.

Slammer infected Microsoft SQL servers through a small piece of code that generated IP addresses at random. The number of infected machines doubled approximately every 9 seconds. Nimda exploited vulnerabilities in the Microsoft Internet Information Services (IIS) web servers for Internet Explorer 5. The worm propagated by sending an infected attachment that was automatically downloaded once the email was viewed. The Code Red I worm attacked Microsoft IIS web servers by replicating itself through IIS server weaknesses Unlike the Slammer worm, Code Red I searched for vulnerable servers to infect. The rate of infection was doubling every 37 minutes. 

37 features are extracted from BGP update messages that originated from AS 513 (route collector rrc 04). The data collected during periods of Internet anomalies include: five-day period for Slammer and Code Red I (the day of the attack as well as two days prior and two days after the attack); seven-day period for Nimda (two and a half days of the attack as well as two and a half days prior and two days after the attack). Note that there are 31 missing data points in the Nimda dataset. 

http://www.sfu.ca/~ljilja/cnl/projects/BGP_datasets/index.html

----------------------------------------------------------------------
Raw data from the "route collector rrc 04" are organized in folders labeled by the year and month of the collection date. 
Complete datasets for Slammer, Nimda, and Code Red I are available from the RIPE route collector rrc 04 site: 
	RIPE NCC: https://www.ripe.net
	Analyze: https://www.ripe.net/analyse
	Internet Measurements: https://www.ripe.net/analyse/internet-measurements
	Routing Information Service (RIS): https://www.ripe.net/analyse/internet-measurements/routing-information-service-ris
	RIS Raw Data: https://www.ripe.net/analyse/internet-measurements/routing-information-service-ris/ris-raw-data
	rrc04.ripe.net: data.ris.ripe.net/rrc04/
The date of last modification and the size of the datasets are also included. 

BGP update messages are originally collected in multi-threaded routing toolkit (MRT) format.
"Zebra-dump-parser" written in Perl is used to extract to ASCII the BGP updated messages.
The 37 BGP features were extracted using a C# tool to generate uploaded datasets (csv files). 
Labels have been added based on the periods when data were collected.

Content of the csv files:
Columns 1-4: time (column 1: hour+minute; column 2: hour; column 3: minute; column 4: second)
Columns 5-41: features
Column 42: labels for the regular (-1) and anomalous (1) data.
Note that for RNN algorithms, the PyTorch library requires that label (-1) be changed to (0).

List of features extracted from BGP update messages:1 Number of announcements2 Number of withdrawals3 Number of announced NLRI prefixes4 Number of withdrawn NLRI prefixes5 Average AS-path length6 Maximum AS-path length7 Average unique AS-path length8 Number of duplicate announcements9 Number of duplicate withdrawals10 Number of implicit withdrawals11 Average edit distance12 Maximum edit distance13 Inter-arrival time14–24 Maximum edit distance = n, n = 7, . . . , 1725–33 Maximum AS-path length = n, n = 7, . . . , 1534 Number of Interior Gateway Protocol (IGP) packets35 Number of Exterior Gateway Protocol (EGP) packets36 Number of incomplete packets37 Packet size (B)

Zebra-dump-parser tool: 
	https://github.com/rfc1036/zebra-dump-parser. 

C# code:
	https://github.com/communication-networks-laboratory/BGP_c_sharp_tool

Other tools/libraries to analyze BGP data:
	https://labs.ripe.net/Members/lorenzo_cogotti/new-mrt-bgp-reader-six-times-faster-than-its-predecessors

----------------------------------------------------------------------
Content:
BGP_datasets_for_anomaly_detection_csv_revised.zip
	README.txt
	Slammer.csv 
	Nimda.csv
	Code_Red_I.csv
	RIPE_regular.csv 
	BCNET_regular.csv

----------------------------------------------------------------------
Publications:
[1] Z. Li, A. L. Gonzalez Rios, G. Xu, and Lj. Trajkovic, "Machine learning techniques for classifying network anomalies and intrusions," IEEE Int. Symp. Circuits and Systems, Sapporo, Japan, May 2019.

[2] A. L. Gonzalez Rios, Z. Li, G. Xu, A. Diaz Alonso, and Lj. Trajkovic, "Detecting network anomalies and intrusions in communication networks," in Proc. 23rd IEEE International Conference on Intelligent Engineering Systems 2019, Godollo, Hungary, April 2019, pp. 29-34.

[3] Q. Ding, Z. Li, S. Haeri, and Lj. Trajkovic, "Application of machine learning techniques to detecting anomalies in communication networks: datasets and feature selection algorithms," in Cyber Threat Intelligence, M. Conti, A. Dehghantanha, and T. Dargahi, Eds., Berlin: Springer, pp. 47-70, 2018.

[4] Z. Li, Q. Ding, S. Haeri, and Lj. Trajkovic, "Application of machine learning techniques to detecting anomalies in communication networks: classification algorithms," in Cyber Threat Intelligence, M. Conti, A. Dehghantanha, and T. Dargahi, Eds., Berlin: Springer, pp. 71-92, 2018.

[5] P. Batta, M. Singh, Z. Li, Q. Ding, and Lj. Trajkovic, "Evaluation of support vector machine kernels for detecting network anomalies," IEEE Int. Symp. Circuits and Systems, Florence, Italy, May 2018, pp. 1-4.

[6] Q. Ding, Z. Li, P. Batta, and Lj. Trajkovic, "Detecting BGP anomalies using machine learning techniques," in Proc. IEEE International Conference on Systems, Man, and Cybernetics, Budapest, Hungary, Oct. 2016, pp. 3352-3355.

----------------------------------------------------------------------
Questions:
Please contact Zhida Li at <zhidal at sfu.ca>.
