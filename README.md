Download Link : https://programming.engineering/product/up23-hw1-secured-api-call/

# UP23-HW1-Secured-API-Call
UP23 HW1 Secured API Call
The homework aims to practice library injection, API hijacking, and GOT rewriting. You have to implement a sandbox.so by following the specification given below. Please read it carefully before you implement your homework.

Specification

Program Launcher

	
	
	
	
	
	
	

Example3

command: ./launcher ./sandbox.so config.txt cat /etc/ssl/certs/Amazon_Root_CA_1.pem

output:

[logger] open(“/usr/share/ca-certificates/mozilla/Amazon_Root_CA_1.crt”, 0, 0) = 5

[logger] read(5, 0x7f6a9c486000, 131072) = -1

cat: /etc/ssl/certs/Amazon_Root_CA_1.pem: Input/output error

cat: /etc/ssl/certs/Amazon_Root_CA_1.pem: Bad file descriptor

Example4

Deleted because duplicated to Example1.

Example5

command: ./launcher ./sandbox.so config.txt wget http://google.com -t 1

output:

–2023-03-29 15:07:09– http://google.com/

Resolving google.com (google.com)… [logger] getaddrinfo(“google.com”,”(null)”,0x7f failed: Name or service not known.

wget: unable to resolve host address ‘google.com’

Example6

command: ./launcher ./sandbox.so config.txt wget https://www.nycu.edu.tw -t 1

output:

–2023-03-29 15:08:12– https://www.nycu.edu.tw/

Resolving www.nycu.edu.tw (www.nycu.edu.tw)… [logger] getaddrinfo(“www.nycu.edu.tw

203.66.32.225, 203.66.32.227,
	

203.66.32.231, …
	

Connecting to www.nycu.edu.tw
	

(www.nycu.edu.tw)|203.66.32.225|:443… [logger] conne

failed: Connection refused.
		

Connecting to www.nycu.edu.tw
	

(www.nycu.edu.tw)|203.66.32.227|:443… [logger] conne

failed: Connection refused.
		

Connecting to www.nycu.edu.tw
	

(www.nycu.edu.tw)|203.66.32.231|:443… [logger] conne

failed: Connection refused.
		

Connecting to www.nycu.edu.tw
	

(www.nycu.edu.tw)|203.66.32.233|:443… [logger] conne

failed: Connection refused.
		

Connecting to www.nycu.edu.tw
	

(www.nycu.edu.tw)|203.66.32.226|:443… [logger] conne

failed: Connection refused.
		

Connecting to www.nycu.edu.tw
	

(www.nycu.edu.tw)|203.66.32.234|:443… [logger] conne

failed: Connection refused.
		

Connecting to www.nycu.edu.tw
	

(www.nycu.edu.tw)|203.66.32.228|:443… [logger] conne

failed: Connection refused.
		

Connecting to www.nycu.edu.tw
	

(www.nycu.edu.tw)|203.66.32.229|:443… [logger] conne

failed: Connection refused.
		
			
			

Example7

command: ./launcher ./sandbox.so config.txt wget http://www.google.com -q -t 1

output:

[logger] getaddrinfo(“www.google.com”,”(null)”,0x7ffd88b905f0,0x7ffd88b905b8) = 0

[logger] connect(5, “142.251.43.4”, 16) = 0

[logger] write(5, 0x56126a865840, 129) = 129

[logger] read(5, 0x56126a8658d0, 511) = 511

[logger] read(5, 0x56126a865acf, 512) = 512

[logger] read(5, 0x56126a865ccf, 129) = 129

[logger] read(5, 0x56126a865840, 6) = 6

[logger] read(5, 0x56126a866610, 8192) = 8192

[logger] read(5, 0x56126a866610, 6408) = 4650

[logger] read(5, 0x56126a866610, 1758) = 1758

[logger] read(5, 0x56126a865840, 2) = 2

[logger] read(5, 0x56126a865840, 3) = 3

[logger] read(5, 0x56126a865840, 2) = 2

Note:

You should find an index.html that contains the HTML content. And you should also find the same content in the log file.

Example8

command: ./launcher ./sandbox.so config.txt python3 -c ‘import os;os.system(“wget http://www.google.com -q -t 1”)’

[logger] read(5, 0x560ce341c5e0, 3908) = 3907

[logger] read(5, 0x560ce341d523, 1) = 0

[logger] read(5, 0x560ce341cad0, 33180) = 33179

[logger] read(5, 0x560ce3424c6b, 1) = 0

[logger] read(5, 0x560ce3428530, 10922) = 10921

[logger] read(5, 0x560ce342afd9, 1) = 0

[logger] read(5, 0x560ce3429540, 1598) = 1597

[logger] read(5, 0x560ce3429b7d, 1) = 0

[logger] read(5, 0x560ce342b990, 3664) = 3663

[logger] read(5, 0x560ce342c7df, 1) = 0

[logger] read(5, 0x560ce342fd60, 6752) = 6751

[logger] read(5, 0x560ce34317bf, 1) = 0

[logger] read(5, 0x560ce3433b00, 17923) = 17922

[logger] read(5, 0x560ce3438102, 1) = 0

[logger] read(5, 0x560ce3434b10, 31557) = 31556

[logger] read(5, 0x560ce343c654, 1) = 0

[logger] read(5, 0x560ce3435af0, 4274) = 4273

[logger] read(5, 0x560ce3436ba1, 1) = 0

[logger] read(5, 0x560ce3404330, 32838) = 32837

[logger] read(5, 0x560ce340c375, 1) = 0

[logger] read(5, 0x560ce340c3f0, 10516) = 10515

[logger] read(5, 0x560ce340ed03, 1) = 0

[logger] read(5, 0x560ce3408d20, 3908) = 3907

[logger] read(5, 0x560ce3409c63, 1) = 0

[logger] read(5, 0x560ce340bf40, 3548) = 3547

[logger] read(5, 0x560ce340cd1b, 1) = 0

[logger] read(5, 0x7f7bafc41150, 226) = 225

[logger] read(5, 0x7f7bafc41231, 1) = 0

[logger] system(“wget http://www.google.com -q -t 1”)

[logger] getaddrinfo(“www.google.com”,”(null)”,0x7ffd704a8120,0x7ffd704a80e8) = 0

[logger] connect(9, “142.251.43.4”, 16) = 0

[logger] write(9, 0x55f9bb917110, 129) = 129

[logger] read(9, 0x55f9bb9171a0, 511) = 511

[logger] read(9, 0x55f9bb91739f, 512) = 512

[logger] read(9, 0x55f9bb91759f, 129) = 129

[logger] read(9, 0x55f9bb917110, 6) = 6

[logger] read(9, 0x55f9bb925990, 8192) = 8192

[logger] read(9, 0x55f9bb925990, 6383) = 4650

[logger] read(9, 0x55f9bb925990, 1733) = 1733

[logger] read(9, 0x55f9bb917110, 2) = 2

[logger] read(9, 0x55f9bb917110, 3) = 3

[logger] read(9, 0x55f9bb917110, 2) = 2

Homework Submission

Please provide a Makefile to compile your source code. Make sure your code can be compiled by make . We use the following command to test your program.

make

./launcher {your sandbox.so} {config file name} command arg1 arg2 …

Please pack your files into a single tar.gz archive and submit your homework via the E3 system.

Grading

    [30%] Your program has the correct output for all test cases listed in the examples section.

    [60%] We use N additional test cases to evaluate your implementation. You get 60 points for

    [10%] If you can perform GOT hijacking without an external program, you get 10% * {ratio of the score you got from the above two items}.

You may leverage external libraries that can be installed from the official Ubuntu package repository using the apt command. In this case, please list your library dependencies as comments in the Makefile and ensure you use the correct parameters to link against the required libraries.

Demo Steps

https://md.zoolab.org/s/gLXd81Myi (https://md.zoolab.org/s/gLXd81Myi)

Hints

You don’t need to consider the non-PIE binary. We will use PIE binary to test your program only.

You can use readelf -r to find the GOT offset of the binary.
