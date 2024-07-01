# Setting the ProMedia IP 2110 sources

In Device Configuration, Board Mode, if **ProMedia IP 2110** is selected as the input mode, then the user needs to set the IP source, one per components received.

**Note:** All incoming sources have to be accuracy synchronized using the PTP protocol, refer to section Configuring PTP for ProMedia IP 2110.

Click on the 2110 Sources to set the parameters for receiving, independently, Pro media IP 2110 streams for the Video, Audio (up to 2 sources, 8 audios each) and Ancillary data. Optionally configure 2022-7 redundancy parameters.

**Restriction:** Be aware that 2022-7 feature has the following limitations for IP-2110 :

* Receiver is Class D: Ultra Low-Skew D

CAUTION:

Prior to any 2110-xx sources configuration it is mandatory to setup and enable at least SFP 1, 3. In addition, if 2022-7 is required, it is mandatory to setup and enable SFP 2, 4 prior to any backup 2110-xx sources.

**Note:** If SFP 1 or 3 is disabled and related link is Down, a warning "SFP# Link Down" is raised. Disabling SFP Ethernet IF only stops 2110-xx flow traffics but not PTP protocol allowing Slave PTP PLL to lock if link is UP, ready for 2110 experience.

The CP9000 allows the user to import predefined parameters of the sources using SDP (Session Description Protocol), to do so, click Import SDP button to download the file.

**Note:** Note the importance of rigorous compliance of 2110 (SDP) source parameters with incident sources. An incorrect parameter which can lead to malfunctions that are difficult to detect, the protocol 2110 does not include information describing the stream neither in the RTP header nor in RTP Payload.

**2110-20 Video source**

* **Input**: to use it set to **Enabled**
*   **Redundancy scheme**: Activate 2022-7 redundancy. Since 2022-7 is a global setting for all encoding channel sources, its activation is proposed in the 2110-20 Video tab only.

    If deactivated, then there is no backup stream. Only Main IP stream parameters need to be set.

    If activated, the Main and Backup redundancy IP streams parameters need to be configured independently in video source. Video format and RTP Payload type are common settings for main and backup streams.
* **Rx parameters**:
  * _Main_: set the IP address, UDP port and SSM (if required) to receive the SDI signal.
  * _Backup_: available if 2022-7 is ON. RTP Payload Main and Backup must be identical to meet 2022-7 Requirements. Therefore RTP Payload _Backup_ value is always read-only and follows _Main_ value.
  * _Video Format_: Set the video format of the incoming signal. The following HD video formats are supported:
    * HD720p50/59.94
    * HD1080i50/59.94
    * FHD1080p50/59.94 **Note:** Only a single 1080p50/59.94 2110-20 source is allowed going along with 2 x HD1080i/720p sources.
  * _Picture Resolution_: Not configurable.

**2110-3x Audio 1 and Audio 2 sources**

* **Input**: to use it set to **Enabled**
*   **Redundancy scheme**: 2022-7 redundancy state. Since 2022-7 is a global setting for all encoding channel sources, its activation is proposed in the 2110-20 Video tab only.

    If deactivated, then there is no backup stream. Only Main IP stream parameters need to be set.

    If activated, the Main and Backup redundancy IP streams parameters need to be configured independently. RTP Payload, Audio Encoding Mode, number of channel and Packet Time are common settings for Main and Backup streams.
* **Rx parameters:**
  * _Main_: set the IP address, UDP port and SSM (if required) to receive the SDI signal.
  * _Backup_: available if 2022-7 is ON (See 2110-20 Video configuration tab). RTP Payload Main and Backup must be identical to meet 2022-7 Requirements. Therefore RTP Payload _Backup_ value is always read-only and it follows _Main_ value.
  * _Encoding Mode_: Set the encoding mode of the incoming signal.
  * _Number of channel_: Set the number of channels present in the incoming signal.
    * 2/4/6/8 for PCM pairs
    * 2/4/6 for AES3 pairs
  * _Packet Time_: 1ms

**2110-40 Ancillary source**

* **Input**: to use it set to **Enabled**
*   **Redundancy scheme**: 2022-7 redundancy state. Since 2022-7 is a global setting for all encoding channel sources, its activation is proposed in the 2110-20 Video tab only.

    If deactivated, then there is no backup stream. Only Main IP stream parameters need to be set.

    If activated, the Main and Backup redundancy IP streams parameters need to be configured independently. RTP Payload value is common for Main and backup sources.
* **Rx parameters:**
  * _Main_: set the IP address, UDP port and SSM (if required) to receive the SDI signal.
  * _Backup_: available if 2022-7 is ON (See 2110-20 Video configuration tab). RTP Payload Main and Backup must be identical to meet 2022-7 Requirements. Therefore RTP Payload _Backup_ value is always read-only and it follows _Main_ value.

**Parent topic:**Setting the ViBE CP9000 Equipment
