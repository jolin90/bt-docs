**bluetooth**
==========================================


# **Architecture & Terminology Overview**

## PART A: ARCHITECTURE
### 1 GENERAL DESCRIPTION

> There are two forms of Bluetooth wireless technology systems: Basic Rate
(BR) and Low Energy (LE).

> Both systems include device discovery, connection
establishment and connection mechanisms

> The Basic Rate system includes optional Enhanced Data Rate (EDR) Alternate
Media Access Control (MAC) and Physical (PHY) layer extensions.

> The Basic Rate system offers synchronous and asynchronous connections with
data rates of 721.2 kb/s for Basic Rate,2.1 Mb/s for Enhanced Data Rate and
high speed operation up to 54 Mb/s with the 802.11 AMP.

> An implementation of the Bluetooth Core has only one Primary Controller
which may be one of the following configurations:
> - a BR/EDR Controller including the Radio, Baseband, Link Manager and
optionally HCI.
> - an LE Controller including the LE PHY, Link Layer and optionally HCI.
> - a combined BR/EDR Controller portion and LE Controller portion (as
identified in the previous two bullets) into a single Controller.

![][Figure-1.1]
![][Figure-1.2]

### 2 CORE SYSTEM ARCHITECTURE
![][Figure-2.1]

### 3 DATA TRANSPORT ARCHITECTURE

![][Figure-3.1]

#### 3.1 CORE TRAFFIC BEARERS
> The Bluetooth core system provides a number of standard traffic bearers for
the transport of service protocol and application data.

![][Figure-3.2]

#### 3.2 TRANSPORT ARCHITECTURE ENTITIES
> The Bluetooth transport architecture entities are shown in Figure 3.3 and are
described from the lowest layer upwards in the subsequent sections.

![][Figure-3.3]


# **Core System Package [BR/EDR Controller volume]**
## PART A: RADIO SPECIFICATION

## PART B: BASEBAND SPECIFICATION
> This document describes the specification of the Bluetooth Link Controller
which carries out the baseband protocols and other low- level link routines.

### 1 GENERAL DESCRIPTION

#### 1.1 BLUETOOTH CLOCK
> Four periods are important in the Bluetooth system: 312.5 μs, 625 μs, 1.25 ms, and 1.28 s

#### 1.2 BLUETOOTH DEVICE ADDRESSING
![][Vol2-PART-B-Figure-1.5]
> The reserved LAP addresses are 0x9E8B00-0x9E8B3F. The general inquiry
LAP is 0x9E8B33

#### 1.3 ACCESS CODES

### 8 LINK CONTROLLER OPERATION LINK CONTROLLER OPERATION
#### 8.1 OVERVIEW OF STATES
![][Vol2-PART-B-Figure-8.1]
#### 8.2 STANDBY STATE
#### 8.3 CONNECTION ESTABLISHMENT SUBSTATES
##### 8.3.1 Page Scan Substate
##### 8.3.2 Page Substate
##### 8.3.3 Page Response Substates
#### 8.4 DEVICE DISCOVERY SUBSTATES
##### 8.4.1 Inquiry Scan Substate
##### 8.4.2 Inquiry Substate
##### 8.4.3 Inquiry Response Substate
#### 8.5 CONNECTION STATE
#### 8.6 ACTIVE MODE
#### 8.7 SNIFF MODE
#### 8.8 HOLD MODE
#### 8.10 CONNECTIONLESS SLAVE BROADCAST MODE
#### 8.11 SYNCHRONIZATION ESTABLISHMENT SUBSTATES


## PART E: HOST CONTROLLER INTERFACE FUNCTIONAL SPECIFICATION
![][Vol2-PART-E-Figure-1.1]
### 5 HCI DATA FORMATS
#### 5.4 EXCHANGE OF HCI-SPECIFIC INFORMATION
##### 5.4.1 HCI Command Packet
> The OGF of 0x3F is reserved for vendor-specific debug commands.

![][Vol2-PART-E-Figure-5.1]

##### 5.4.2 HCI ACL Data Packets
![][Vol2-PART-E-Figure-5.2]

##### 5.4.3 HCI Synchronous Data Packets
![][Vol2-PART-E-Figure-5.3]

##### 5.4.4 HCI Event Packet
![][Vol2-PART-E-Figure-5.4]

# **Core System Package [Host volume]**

## PART A: LOGICAL LINK CONTROL AND ADAPTATION PROTOCOL SPECIFICATION
## PART B: SERVICE DISCOVERY PROTOCOL (SDP) SPECIFICATION











[Figure-1.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Figure-1.1.png
[Figure-1.2]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Figure-1.2.png
[Figure-2.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Figure-2.1.png
[Figure-3.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Figure-3.1.png
[Figure-3.2]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Figure-3.2.png
[Figure-3.3]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Figure-3.3.png
[Vol2-PART-B-Figure-1.5]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Pictures/Vol2-PART-B-Figure-1.5.png
[Vol2-PART-B-Figure-8.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Pictures/Vol2-PART-B-Figure-8.1.png
[Vol2-PART-E-Figure-1.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Pictures/Vol2-PART-E-Figure-1.1.png
[Vol2-PART-E-Figure-5.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Pictures/Vol2-PART-E-Figure-5.1.png
[Vol2-PART-E-Figure-5.2]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Pictures/Vol2-PART-E-Figure-5.2.png
[Vol2-PART-E-Figure-5.3]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Pictures/Vol2-PART-E-Figure-5.3.png
[Vol2-PART-E-Figure-5.4]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Pictures/Vol2-PART-E-Figure-5.4.png
