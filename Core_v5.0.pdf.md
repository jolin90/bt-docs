**bluetooth**
==========================================


# **Architecture & Terminology Overview**

## PART A: ARCHITECTURE
### 1 GENERAL DESCRIPTION

> There are two forms of Bluetooth wireless technology systems: Basic Rate
(BR) and Low Energy (LE).

> Both systems include device discovery, connection
establishment and connection mechanisms

> The Basic Rate system includes optional Enhanced Data Rate (EDR) Alternate Media Access Control (MAC) and Physical (PHY) layer extensions.

> The Basic Rate system offers synchronous and asynchronous connections with data rates of 721.2 kb/s for Basic Rate,2.1 Mb/s for Enhanced Data Rate and high speed operation up to 54 Mb/s with the 802.11 AMP.

> An implementation of the Bluetooth Core has only one Primary Controller
which may be one of the following configurations:
>- a BR/EDR Controller including the Radio, Baseband, Link Manager and
optionally HCI.
>- an LE Controller including the LE PHY, Link Layer and optionally HCI.
>- a combined BR/EDR Controller portion and LE Controller portion (as
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
> This document describes the specification of the Bluetooth Link Controller which carries out the baseband protocols and other low- level link routines.

### 8 LINK CONTROLLER OPERATION LINK CONTROLLER OPERATION

#### 8.1 OVERVIEW OF STATES
![][Figure-8.1]

# **Core System Package [Host volume]**

[Figure-1.1]:Figure-1.1.png
[Figure-1.2]:Figure-1.2.png
[Figure-2.1]:Figure-2.1.png
[Figure-3.1]:Figure-3.1.png
[Figure-3.2]:Figure-3.2.png
[Figure-3.3]:Figure-3.3.png
[Figure-8.1]:Figure-8.1.png
