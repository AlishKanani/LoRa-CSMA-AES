# Getting Started

## Overview


The ns3 lora module is a simplistic model of a lora-like network. It supports LoraWAN Class A end devices and one gateway. The simulator is working end to end from packet creation, node setup, gateway setup to final transmission along with the AES encryption.

## Installing

To install this module, follow these steps:
1. Download ns-3 latest version (ns-3-27) at [ns-3 main page](https://www.nsnam.org/ns-3-27).
2. Extract ns-allinone-3.27.tar.bz2 file.
3. Download ns3 lora module, then copy it ./src folder inside ns-allinone-3.27 folder.
4. Run three next statements to build source code:
```
	~/ns-allinone-3.27/ns-3$ ./waf clean
	~/ns-allinone-3.27/ns-3$ ./waf configure --enable-tests --enable-examples
	~/ns-allinone-3.27/ns-3$ ./waf build	
```

## Running the tests and examples

To test ns3 lora module, you run this statement:
```
	~/ns-allinone-3.27/ns-3$ ./test.py -s lora-node -m -t lora-node.txt
```
To run example of ns3 lora module, you run this statement:
```
	~/ns-allinone-3.27/ns-3$ ./waf --run lora-example
```

## Features Implemented
### Custom center frequency 

We have implemented the custom frequency module for different range (865-866 MHz for India, 902-928 MHz for US etc.). Using this module user can twitch the frequencies and simulate the network for different regions.

### Security

As lora communicates in ISM band, which is open band so there are lot of security concerns for any sensitive data. We have implemented security module using Advanced Encryption Standard(AES) scheme, which is suggested by [lora-alliance](https://lora-alliance.org/). 

This encryption is working on both Network and Application layer. The public key for both layer is shared with end devices and the gateway in the initialisation stage.

### Enable Logging

NS-3 log module is used to display the channel and device specifications at each stage of the communication. The logs are displaying the journey of the packet from the source to the destination, along with the network parameters like power consumer, packet error etc.

### Implement CSMA channel

The LoraWAN network similuations that are available till now is working on ALOHA technique, we have modified the MAC channel access, to enable the communication using Carier Sense Multiple Access(CSMA) channel, which transmits packet much faster than traditional ALOHA.

## License

This software is licensed under the terms of the GNU GPLv2 - see the [LICENSE](LICENSE) file for details.

