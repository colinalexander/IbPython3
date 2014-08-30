IbPython3
=========

IbPython3 provides a native Python 3 implementation of the Interactive Brokers API software (version 9.70), allowing traders and investors to use Python's command line console to interact with Interactive Brokers via the IB Gateway or IB Trader Workstation platforms.

IbPython3 is a third-party implementation used for accessing the Interactive Brokers IB API and is not endorsed by Interactive Brokers or its affiliates.

Contact information: IbPython3@gmail.com
 
##Installation
Using Python's pip installation package, just type 'pip3 install ibpython3' from the terminal window.

##Description 
IbPython3 is a 3rd party implementation of the Interactive Brokers API interface functionality, currently version 9.70.  It supports all of the read and write methods to the server.

Compatible with Python version 3.3+ and IB Server versions 62+ (current IB server version is 67)

IbPython3 is not related to IbPy, although I wish to thank its authors for their hard work.

IbPython3 is a Python 3 hand coded implementation of the IB Java API.  It groups the modules by their functionality as detailed below.  The socket reading and writing routines should be more efficient.  The naming conventions are intended to follow Python style guidelines, although their Java equivalents should be easily identifiable.

Any client implementations of the EWrapper functions are over-ridden in the my_methods.py file.  See the demo for examples.

##Videos
Below are the planned series of videos (with links to existing titles) which are meant to be the same groupings as used in IB's documentation to demonstrate the usage of each function. IbPython3 hides the complexity of the event-driven callbacks in the API, making it much more accessible to average users (somewhere between Excel and Java). The ability to directly interact with the API via the Python console also makes learning more interactive.

1.  [An Introduction](https://www.youtube.com/watch?v=BF5Pjd-dVFY)
2.  Data Containers (specific to IbPython3)
3.  [Contract Details](https://www.youtube.com/watch?v=F-jb6JPXjsw)
4.  [Historical Data and Real Time Bars](https://www.youtube.com/watch?v=A8AV3UJeHwQ)
5.  [Account & Portfolio Data](https://www.youtube.com/watch?v=FRX-MFL8CIw)
6.  [Orders](https://www.youtube.com/watch?v=AKrrgOyNUe4)
7.  [Executions and Commission Reports](https://www.youtube.com/watch?v=6xc3fwltUB0)
8.  Market Data
9.  Market Depth
10.  News Bulletins
11.  Fundamental Data
12.  Market Scanners
13.  Financial Advisors
14.  [Combination Orders and Option Exercise](https://www.youtube.com/watch?v=NSIDAEjdyrE)

##File Structure and Classes
| IbPython3 version 9.70                         | IB API 9.70 Java Client equivalent |
| ---------------------------------------------- | ---------------------------------- |
| **contracts.py** | |
|    class ComboLeg | ComboLeg.java |
|    class Contract | Contract.java |
|    class UnderComp | UnderComp.java |
|    class ContractDetails | Contract Details.java
|
| **execution.py**
|    class Execution | Execution.java |
|    class ExecutionFilter | ExecutionFilter.java |
|
| **ib_connector.py**
|    class IbConnector | EClientSocket.java (partial implementation) |
|    class SockReaderThread | EReader.java (partial implementation) |
|    class Socket | n/a (custom Python implementation)
|    class IbClient | EClientSocket.java (partial implementation) |
|
| **logger.py**
|    class Logger | n/a (custom Python implemenation of a log file)
|
| **misc.py**
|    class Eq | n/a (custom Python implemenation to test object equality) |
|    class Clone | n/a (custom Python implemenation to clone an object) |
|    class ByteArray | n/a (roughly equivalent to Builder.java as implemented in ib_connector.Socket) |
|    class TagValue | TagValue.java |
|    class MarketDataType | MarketDataType.java |
|    class CommissionReport | CommissionReport.java |
|    class UnderComp | UnderComp.java |
|    class ScannerSubscription | ScannerSubscription.java |
|    class Util | Util.java |
|    class TickType | TickType.java |
|    class CodeMsgPair | EClientErrors.java |
|    class EClientErrors | EClientErrors.java |
|
| **msg_processor.py**
|    class ProcessIncomingMsg | EReader.java (implementation of reading functions) |
|    class ProcessOutgoingMsg | EClientSocket.java (implementation of writing functions |
|
| **my_methods.py** | n/a (override EWrapper implementations here) |
|
| **orders.py**
|    class OrderComboLeg | OrderComboLeg.java |
|    class OrderState | OrderState.java |
|    class Order | Order.java
|
| **Wrappers.py**
|    classes ObjectDespriptor and PrintSelf | n/a (custom Python implementation to print object contents, similar to EWrapperMsgGenerator.java) |
|    class AnyWrapper | AnyWrapper.java |
|    class AnyWrapperMsgGenerator | AnyWrapperMsgGenerator.java |
|    class Error | n/a (custom Python implementation to propogate error messages) |
|    class EWrapper | EWrapper.java |

Note:  IApiEnum.java and MarketDataType.java are not deemed necessary to include in the Python code

# DISCLAIMER #

**THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHERIN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.**

Source files  
functionality from EClientSocket.java, EReader.java

Original file(s) Copyright (C) 2014 Interactive Brokers LLC.
All rights reserved.

This file Copyright (c) 2014 by Colin Alexander, CFA (the 'Author').

All Rights Reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1.  Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
2.  Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
