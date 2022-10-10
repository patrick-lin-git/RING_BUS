# RING_BUS

A ring bus is an low-bandwidth message forwarding mechanism between initiator(normally CPU) and target(normally I/O devices).
it was designed to resolve routing resouce issue of an SOC chip by replacing hierachical fan-out structure bus to peer-to-peer daisy chain structure bus. It improve routing efficiency and also timing closure especially on FPGA implementation.
## Features
   * support multi-master
   * support bit-level set/clear (bit-banding)
   * support outstanding request
   * pipeline insertion between ring member allowed
   * small P&R footprint
   
## Target application
   * low-bandwidth data transfer within SOC
   * latency insensitive event passing like software register access, status update, interrupt & acknowledge, IPC etc.
   
## Top Architecture
* four ring members case

![RING Bus Top Architecture](./doc/diagram/ring_bus_top_architecture.png)

## Protocol between Ring Member

![Protocol between member](./doc/diagram/ring_bus_protocol.png)

## Message Type

![Message Type](./doc/diagram/ring_bus_message_type.png)

## Message Structure

 * Generic Structure (Generic)

![Generic Message](./doc/diagram/ring_bus_message_structure.png)

 * Request Type (Register Read, Bit Set/Clear)

 ![Generic Message](./doc/diagram/ring_bus_message_structure_request_0.png)

 * Request Type (Register Write, Interrupt Request, Peer-to-Peer Message)

 ![Generic Message](./doc/diagram/ring_bus_message_structure_request_1.png)

 * Request Type (Set Member ID)
 
 ![Generic Message](./doc/diagram/ring_bus_message_structure_request_2.png)
 
 * Respose Type (Register Read Data Return (4 Bytes, 1 Bytes, 16 Bytes)
 
 ![Generic Message](./doc/diagram/ring_bus_message_structure_response_0.png)
 
 * Respose Type (Write Complte or Bit Set/Clear Status, Interrupt Acknowledge)

 ![Generic Message](./doc/diagram/ring_bus_message_structure_response_1.png)
 
## Ring Member Interface
 
 ![Generic Message](./doc/diagram/ring_bus_ring_element.png)
 
## Ring Member Internal Structure
 
 ![Generic Message](./doc/diagram/ring_member_architecture.png)
 


   
   
