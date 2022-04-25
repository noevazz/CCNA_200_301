# The OSI Model

The Open System Interconnection (OSI) model was developed by the International Organization for Standardization (ISO), it is used to describe network systems as a layered stack of protocols.

## What is a protocol?

A protocol is a set of rules that govern the processes for a step trough the communication flow.

There are multiple network protocols and each one is in charge of defining the expected result, and sometime the implementation, of the technology.

## 7 layer

The OSI model groups networking protocols in stacked layers. Each layer contains protocols that follows and perform certain actions that generate data for the next layer.

In this stack layers are numbered from 1 to 7 from bottom to top, respectively:

|#  |Name        |
|---|------------|
|7  |Application |
|6  |Presentation|
|5  |Session     |
|4  |Transport   |
|3  |Network     |
|2  |Data link   |
|1  |Physical    |

### Layer 7

## Benefits of a layered model

- Helps network engineers and others to narrow down problems by identifying issues described by actions that should happen in a specific layer.
- Provides a framework for programmers to create applications accordingly to the layers and the expected functioning.
- Promotes competition between tech vendors, they can focus in provide the best technology but also ensuring their product can work cross the stack and with other products that talk the same protocols.
- Assists protocol design: new protocols need to work with adjacent layers and they can use the OSI model as a reference to know what is expected.

## Protocol interaction

- Same-layer interaction: same layers communicate. For example: TCP protocol in device A communicates with TCP protocol in device B.
- Adjacent-layer interaction: when a layer communicates with the layers above and below of it.

## Encapsulation

Each layer generates data for the next layer, when the next layer receives this data, it adds more data at the beginning and at the end of the receiving data. This process is known as encapsulation.

Data added at the beginning is called **header**.
Data added at the end is called **trailer**.
We refer as **payload** to the data that is in the middle of header and trailer.

Think of encapsulation as putting an envelope #1 inside and envelope #2, then envelope #2 inside envelope #3 and so on until envelope #7. Each envelope adds more information (header and trailer), and the envelope inside is the payload.

```
✉️ Layer 7
⬇
✉️ Layer 6
⬇
✉️ Layer 5
⬇
✉️ Layer 4
⬇
✉️ Layer 3
⬇
✉️ Layer 2
⬇
✉️ Layer 1
```

At layer 1 data is transformed to electrical pulses, light or radio waves according to the media to transport the data. Now the data is ready to be sended.

Layer 1 may also add info (electrical pulses, etc.) to physically synchronize with the receiving device.

## De-encapsulation

When a device receives the data it will receive the Layer 1 PDU.

The receiving device needs to reverse the encapsulation process up to layer 7 to get the desired data. (The process may stop before layer 7, for example layer 3 can request data to layer 3 so there won't be data for upper layers).

```
✉️ Layer 7                                   ✉️ Layer 7
⬇                                          ⬆
✉️ Layer 6                                   ✉️ Layer 6
⬇                                          ⬆
✉️ Layer 5                                   ✉️ Layer 5
⬇                                          ⬆
✉️ Layer 4                                   ✉️ Layer 4
⬇                                          ⬆
✉️ Layer 3                                   ✉️ Layer 3
⬇                                          ⬆
✉️ Layer 2                                   ✉️ Layer 2
⬇                                          ⬆
✉️ Layer 1 ➜➜➜➜ traveling through media ➜➜➜➜ ✉️ Layer 1
```

**Media** is a fancy name for the physical channel used to transport the data (electrical pulses, light or radio waves, etc.)

## Protocol Data Units

The envelope (data or unit if you prefer) generated at each layer is known as the Protocol Data Unit (**PDU**).

|#  |Layer name  |PDU name|
|---|------------|--------|
|7  |Application |Data    |
|6  |Presentation|Data    |
|5  |Session     |Data    |
|4  |Transport   |Segment |
|3  |Network     |Packet  |
|2  |Data link   |Frame   |
|1  |Physical    |Bits    |

> Note: `TCP` and `UDP` are the most representative protocols of layer 4. **Technically**, the `PDU` for `UDP` is the `Datagram`, and Segment for TCP. However some people use the name `Segment` for `TCP` and `UDP`.


## External resources

1. [En] https://upskilld.com/learn/same-layer-and-adjacent-layer-interactions/
2. [En] https://osi-model.com/