### IPv4 header fields

the **IPv4 datagram header** consists of several fixed-size fields that contain the information necessary to forward the datagram across the Internet. Below is the list of fields, their lengths, and their functions:

- **VERS (Version):**
    - **Length:** 4 bits.
    - **Function:** Indicates the protocol version number (e.g., version 4).
- **H.LEN (Header Length):**
    - **Length:** 4 bits.
    - **Function:** Specifies the number of **32-bit quantities** in the header. If no options are present, the value is typically 5.
- **SERVICE TYPE:**
    - **Length:** 8 bits.
    - **Function:** Carries the **class of service** for the datagram, though it is seldom used in practice.
- **TOTAL LENGTH:**
    - **Length:** 16 bits.
    - **Function:** Specifies the **total number of bytes** in the datagram, including both the header and the payload.
- **IDENTIFICATION:**
    - **Length:** 16 bits.
    - **Function:** A unique (usually sequential) number assigned to the datagram, used by the receiver to gather all fragments of a single datagram for **reassembly**.
- **FLAGS:**
    - **Length:** 3 bits.
    - **Function:** Individual bits specify whether the datagram is a **fragment**, and if so, whether it is the rightmost (final) piece of the original datagram.
- **FRAGMENT OFFSET:**
    - **Length:** 13 bits.
    - **Function:** Specifies where in the original datagram the data in the current fragment belongs; the value is multiplied by 8 to get the actual offset.
- **TIME TO LIVE (TTL):**
    - **Length:** 8 bits.
    - **Function:** An integer initialized by the sender and **decremented by each router** that processes the datagram. If it reaches zero, the datagram is discarded to prevent infinite loops.
- **TYPE (Protocol):**
    - **Length:** 8 bits.
    - **Function:** Specifies the **type of the payload** being carried (e.g., TCP or UDP).
- **HEADER CHECKSUM:**
    - **Length:** 16 bits.
    - **Function:** A ones-complement checksum of the header fields used to ensure the **integrity of the header**.
- **SOURCE IP ADDRESS:**
    - **Length:** 32 bits.
    - **Function:** The Internet address of the **original sender**; intermediate router addresses do not appear here.
- **DESTINATION IP ADDRESS:**
    - **Length:** 32 bits.
    - **Function:** The Internet address of the **ultimate destination**; this field remains unchanged as the datagram passes through the Internet.
- **IP OPTIONS:**
    - **Length:** Variable.
    - **Function:** Optional fields used to **control routing and processing**; they are omitted in most datagrams.
- **PADDING:**
    - **Length:** Variable.
    - **Function:** Zero bits added to ensure the header ends on a **32-bit boundary** if options are used.

### IPv6  header fields

the **IPv6 datagram** uses a new header format that divides information into a **base header** and zero or more optional **extension headers**. The base header contains the following fields:

- **VERS (Version):**
    - **Length:** 4 bits.
    - **Function:** Indicates the protocol version number, which is 6 for IPv6.
- **TRAFFIC CLASS:**
    - **Length:** 8 bits.
    - **Function:** Specifies the **class of service** for the datagram, using the same definition as the IPv4 Service Type field.
- **FLOW LABEL:**
    - **Length:** 20 bits.
    - **Function:** Originally intended to associate a datagram with a **label switched path**, though it has become less important over time.
- **PAYLOAD LENGTH:**
    - **Length:** 16 bits.
    - **Function:** Specifies the size of the **data being carried** (payload) measured in octets. Unlike IPv4, this field **excludes the size of the header**.
- **NEXT HEADER:**
    - **Length:** 8 bits.
    - **Function:** Identifies the type of information that follows the current header, which could be an **extension header** or the **payload** (such as TCP or UDP).
- **HOP LIMIT:**
    - **Length:** 8 bits.
    - **Function:** Serves the same purpose as the IPv4 Time-to-Live field; it is **decremented by each router**, and the datagram is discarded if the value reaches zero.
- **SOURCE ADDRESS:**
    - **Length:** 128 bits.
    - **Function:** The IPv6 address of the **original sender** of the datagram.
- **DESTINATION ADDRESS:**
    - **Length:** 128 bits.
    - **Function:** The IPv6 address of the **ultimate destination**.

Unlike IPv4, the IPv6 base header **does not include fields for fragmentation**; instead, fragmentation information is placed in a separate **fragment extension header** when needed.


