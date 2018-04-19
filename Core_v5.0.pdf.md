bluetooth
==========================================


# Architecture & Terminology Overview

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

![][Vol1-PART-A-Figure-1.1]
![][Vol1-PART-A-Figure-1.2]

### 2 CORE SYSTEM ARCHITECTURE
![][Vol1-PART-A-Figure-2.1]

### 3 DATA TRANSPORT ARCHITECTURE

![][Vol1-PART-A-Figure-3.1]

#### 3.1 CORE TRAFFIC BEARERS
> The Bluetooth core system provides a number of standard traffic bearers for
the transport of service protocol and application data.

![][Vol1-PART-A-Figure-3.2]

#### 3.2 TRANSPORT ARCHITECTURE ENTITIES
> The Bluetooth transport architecture entities are shown in Figure 3.3 and are
described from the lowest layer upwards in the subsequent sections.

![][Vol1-PART-A-Figure-3.3]


----------------------------------------------------------------------------------------------------------------------

# Core System Package [BR/EDR Controller volume]
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

----------------------------------------------------------------------------------------------------------------------

# Core System Package [Host volume]

## PART A: LOGICAL LINK CONTROL AND ADAPTATION PROTOCOL SPECIFICATION

### 1 INTRODUCTION
> L2CAP provides connection-oriented and connectionless data services to
upper layer protocols with protocol multiplexing capability and segmentation
and reassembly operation.

![][Vol3-PART-A-Figure-1.1]

> * Protocol/channel multiplexing
> * Segmentation and reassembly
> * Flow control per L2CAP channel
> * Error control and retransmissions
> * Support for Streaming
> * Fragmentation and Recombination
> * Quality of Service

### 2 GENERAL OPERATION

#### 2.1 CHANNEL IDENTIFIERS

The CID name space for the ACL-U, ASB-C, and AMP-U logical links is as follows:

| CID           | Description Channel     | Characteristics                                                         | Logical Link Supported |
| ----          | :----                   | :----                                                                   | :----                  |
| 0x0000        | Null identifier         | Not allowed                                                             |                        |
| 0x0001        | L2CAP Signaling channel | See Section 4                                                           | ACL-U                  |
| 0x0002        | Connectionless channel  | See Section 7.6                                                         | ACL-U, ASB-U           |
| 0x0003        | AMP Manager Protocol    | See [Vol 3] Part E, Section2.2.                                         | ACL-U                  |
| 0x0004-0x0006 | Reserved for Future Use | Not applicable                                                          |                        |
| 0x0007        | BR/EDR Security Manager | See [Vol 3] Part H                                                      | ACL-U                  |
| 0x0008-0x003E | Reserved for Future Use | Not applicable                                                          |                        |
| 0x003F        | AMP Test Manager        | See [Vol 3] Part D, Section1.2.3 ACL-U                                  | ACL-U                  |
| 0x0040-0xFFFF | Dynamically allocated   | Communicated using L2CAP configuration <br> mechanism (see Section 7.1) | ACL-U, AMP-U           |


The CID name space for the LE-U logical link is as follows:

| CID           | Description Channel                | Characteristics                                                                                   | Logical Link Supported |
| ----          | :----                              | :----                                                                                             | :----                  |
| 0x0000        | Null identifier                    | Not Allowed                                                                                       |                        |
| 0x0001-0x0003 | Reserved for Future Use            | Not applicable                                                                                    |                        |
| 0x0004        | Attribute Protocol                 | See [Vol 3] Part F                                                                                | LE-U                   |
| 0x0005        | Low Energy L2CAP Signaling channel | See Section 4                                                                                     | LE-U                   |
| 0x0006        | Security Manager Protocol          | See [Vol 3] Part H                                                                                | LE-U                   |
| 0x0007-0x001F | Reserved for Future Use            | Not applicable                                                                                    |                        |
| 0x0020-0x003E | Assigned Numbers                   |                                                                                                   | LE-U                   |
| 0x003F        | Reserved for Future Use            | Not applicable                                                                                    |                        |
| 0x0040-0x007F | Dynamically allocated              | Communicated using the L2CAP LE credit based <br> create connection mecha-nism (see Section 4.22) | LE-U                   |
| Other         | Reserved for Future Use            | Not applicable                                                                                    |                        |

#### 2.4 MODES OF OPERATION

* Basic L2CAP Mode
* Flow Control Mode
* Retransmission Mode
* Enhanced Retransmission Mode
* Streaming Mode
* LE Credit Based Flow Control Mode

### 3 DATA PACKET FORMAT

![][Vol3-PART-A-Figure-3.1]

![][Vol3-PART-A-Figure-3.2]

![][Vol3-PART-A-Figure-3.3]

![][Vol3-PART-A-Figure-3.6]

### 4 SIGNALING PACKET FORMATS
### 5 CONFIGURATION PARAMETER OPTIONS
### 6 STATE MACHINE
### 7 GENERAL PROCEDURES
#### 7.2 FRAGMENTATION AND RECOMBINATION
> Fragmentation is the breaking down of PDUs into smaller pieces for delivery
from L2CAP to the lower layer. Recombination is the process of reassembling
a PDU from fragments delivered up from the lower layer. Fragmentation and
Recombination may be applied to any L2CAP PDUs.

##### 7.2.1 Fragmentation of L2CAP PDUs

![][Vol3-PART-A-Figure-7.1]
![][Vol3-PART-A-Figure-7.2]

### 8 PROCEDURES FOR FLOW CONTROL AND RETRANSMISSION
### 9 PROCEDURE FOR AMP CHANNEL CREATION AND HANDLING
### 10 PROCEDURES FOR CREDIT BASED FLOW CONTROL

## PART B: SERVICE DISCOVERY PROTOCOL (SDP) SPECIFICATION
> This specification defines a protocol for locating services provided by or
available through a Bluetooth device.

### 2 OVERVIEW
#### 2.1 SDP CLIENT-SERVER ARCHITECTURE
![][Vol3-PART-B-Figure-2.1]

### 2.5 SEARCHING FOR SERVICES
#### 2.5.1 UUID
> A UUID is a universally unique identifier that is guaranteed to be unique across
all space and all time. UUIDs can be independently created in a distributed
fashion. No central registry of assigned UUIDs is required. A UUID is a 128-bit
value.

> Bluetooth Base UUID and has the value 00000000-0000-1000-8000-00805F9B34FB
* 128_bit_value = 16_bit_value * 2 96 + Bluetooth_Base_UUID
* 128_bit_value = 32_bit_value * 2 96 + Bluetooth_Base_UUID

https://www.bluetooth.com/specifications/assigned-numbers/service-discovery

### 2.6 BROWSING FOR SERVICES

> In SDP, the mechanism for browsing for services is based on an attribute
shared by all service classes. This attribute is called the BrowseGroupList
attribute. The value of this attribute contains a list of UUIDs. Each UUID
represents a browse group with which a service may be associated for the
purpose of browsing.


### 4 PROTOCOL DESCRIPTION
#### 4.1 TRANSFER BYTE ORDER
4.2 PROTOCOL DATA UNIT FORMAT

![][Vol3-PART-B-Figure-4.1]

* PDU ID:

| Value     | Parameter Description                                                                      |
| ----      | :-----                                                                                     |
| N         | The PDU ID field identifies the type of PDU. I.e. its meaning and the specific parameters. |
| 0x00      | Reserved for future use                                                                    |
| 0x01      | SDP_ErrorResponse                                                                          |
| 0x02      | SDP_ServiceSearchRequest                                                                   |
| 0x03      | SDP_ServiceSearchResponse                                                                  |
| 0x04      | SDP_ServiceAttributeRequest                                                                |
| 0x05      | SDP_ServiceAttributeResponse                                                               |
| 0x06      | SDP_ServiceSearchAttributeRequest                                                          |
| 0x07      | SDP_ServiceSearchAttributeResponse                                                         |
| 0x08-0xFF | Reserved for future use                                                                    |







[Vol1-PART-A-Figure-1.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol1-PART-A-Figure-1.1.png
[Vol1-PART-A-Figure-1.2]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol1-PART-A-Figure-1.2.png
[Vol1-PART-A-Figure-2.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol1-PART-A-Figure-2.1.png
[Vol1-PART-A-Figure-3.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol1-PART-A-Figure-3.1.png
[Vol1-PART-A-Figure-3.2]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol1-PART-A-Figure-3.2.png
[Vol1-PART-A-Figure-3.3]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol1-PART-A-Figure-3.3.png
[Vol2-PART-B-Figure-1.5]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol2-PART-B-Figure-1.5.png
[Vol2-PART-B-Figure-8.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol2-PART-B-Figure-8.1.png
[Vol2-PART-E-Figure-1.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol2-PART-E-Figure-1.1.png
[Vol2-PART-E-Figure-5.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol2-PART-E-Figure-5.1.png
[Vol2-PART-E-Figure-5.2]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol2-PART-E-Figure-5.2.png
[Vol2-PART-E-Figure-5.3]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol2-PART-E-Figure-5.3.png
[Vol2-PART-E-Figure-5.4]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol2-PART-E-Figure-5.4.png
[Vol3-PART-A-Figure-1.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol3-PART-A-Figure-1.1.png
[Vol3-PART-A-Figure-3.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol3-PART-A-Figure-3.1.png
[Vol3-PART-A-Figure-3.2]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol3-PART-A-Figure-3.2.png
[Vol3-PART-A-Figure-3.3]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol3-PART-A-Figure-3.3.png
[Vol3-PART-A-Figure-3.6]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol3-PART-A-Figure-3.6.png
[Vol3-PART-A-Figure-7.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol3-PART-A-Figure-7.1.png
[Vol3-PART-A-Figure-7.2]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol3-PART-A-Figure-7.2.png
[Vol3-PART-B-Figure-2.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol3-PART-B-Figure-2.1.png
[Vol3-PART-B-Figure-4.1]:https://raw.githubusercontent.com/jolin90/bt-docs/master/Pictures/Vol3-PART-B-Figure-4.1.png
