# Red Hat JBoss A-MQ Performance Test

Red Hat JBoss A-MQ is a light weight high performance Message-Oriented Middleware(MOM).

This project make user be able to test the performance of A-MQ using `activemq-perf-maven-plugin`.


## 1. Prerequisites


	1.  java 7 or 8 
	2.  Apache Maven 3.3.1
	
 
## 2. Install and run Red Hat JBoss A-MQ 6.3.0
 	
download [JBoss A-MQ 6.3.0](https://access.redhat.com/jbossnetwork/restricted/softwareDownload.html?softwareId=46841), unzip, add a test user(step 3) before running, and run A-MQ, 
 	
 	
	> unzip jboss-a-mq-6.3.0.redhat-187.zip
	> cd jboss-a-mq-6.3.0.redhat-187/bin
	> ./amq
 	
## 3. Add a test user and password in A-MQ user.properties

append the below line to $JBOSS_A-MQ__HOME/etc/users.properties file

	test=demo,Operator 

## 4. Clone Git repository 

	> git clone https://github.com/hinunbi/a-mq-bmt.git
	

## 5. Run the message producer and consumer
	
	> cd a-mq-bmt
	> mvn activemq-perf:producer -DsysTest.propsConfigFile=src/main/resources/openwire-producer-persistence.properties
	> mvn activemq-perf:consumer -DsysTest.propsConfigFile=src/main/resources/openwire-consumer.properties


## 6. My result
 

#### 1. My pc specification
	
	MacBook Pro (Retina, 15-inch, Mid 2015)
	2.5 GHz Intel Core i7
	16GB 1600 MHz DDR3
	

#### 2. A-MQ Producer performance

	#########################################
	####    SYSTEM THROUGHPUT SUMMARY    ####
	#########################################
	System Total Throughput: 4388816
	System Total Clients: 10
	System Average Throughput: 14629.386666666665
	System Average Throughput Excluding Min/Max: 14552.84
	System Average Client Throughput: 1462.9386666666664
	System Average Client Throughput Excluding Min/Max: 1455.284
	Min Client Throughput Per Sample: clientName=JmsProducer2, value=543
	Max Client Throughput Per Sample: clientName=JmsProducer9, value=1743
	Min Client Total Throughput: clientName=JmsProducer7, value=438421
	Max Client Total Throughput: clientName=JmsProducer5, value=439188
	Min Average Client Throughput: clientName=JmsProducer7, value=1461.4033333333334
	Max Average Client Throughput: clientName=JmsProducer5, value=1463.96
	Min Average Client Throughput Excluding Min/Max: clientName=JmsProducer7, value=1453.73
	Max Average Client Throughput Excluding Min/Max: clientName=JmsProducer5, value=1456.2733333333333

#### 3. A-MQ Consumer performance

	#########################################
	####    SYSTEM THROUGHPUT SUMMARY    ####
	#########################################
	System Total Throughput: 4388811
	System Total Clients: 10
	System Average Throughput: 14629.369999999999
	System Average Throughput Excluding Min/Max: 14571.336666666666
	System Average Client Throughput: 1462.937
	System Average Client Throughput Excluding Min/Max: 1457.1336666666666
	Min Client Throughput Per Sample: clientName=JmsConsumer7, value=0
	Max Client Throughput Per Sample: clientName=JmsConsumer7, value=1741
	Min Client Total Throughput: clientName=JmsConsumer3, value=438878
	Max Client Total Throughput: clientName=JmsConsumer9, value=438883
	Min Average Client Throughput: clientName=JmsConsumer3, value=1462.9266666666667
	Max Average Client Throughput: clientName=JmsConsumer9, value=1462.9433333333334
	Min Average Client Throughput Excluding Min/Max: clientName=JmsConsumer3, value=1457.1233333333332
	Max Average Client Throughput Excluding Min/Max: clientName=JmsConsumer9, value=1457.14
