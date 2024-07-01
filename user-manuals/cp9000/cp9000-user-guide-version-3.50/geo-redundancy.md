# Geo Redundancy

It consists in synchronizing two CP9000, located in different sites, to ensure the continuity of video/audio/data streams transmission, in case of loss of channel signal.

Geo synchronization is performed between channels on 2 CP9K pair equipment. Each CP9000 encoder is in a distinct location (sites A and B). A and B devices are using the same C\&C network (same VLAN).

For a given encoding channel pair, PCR counters shall be synchronized (same origin time) to provide Video/Audio/Ancillary PTS timestamps to support seamless switching on downstream device.

PCR synchronization can be achieved if and only if the encoding sources (SDI or 2022-6) feeding channel pair are fully synchronous and have the same delay path.

To complete the synchronization, PCR alignment requires that CP9000 encoder pair is receiving the same flow containing the same VITC (Timecode). VITC is acting as the common Frame Time base for sites A and B.

One CP9000 is acting as Master reference for the PCR/PTS and the other as Slave per channel basis.

CP9000's role depends on error or failure events, some rules shall be specified to elect and assign a CP9000 to Master role for a channel.

CP9000 pair are connected together and exchange some messages including data such as role, status and Timestamps \<VITC,PTS> on channel basis.

Channel pairing means same channel ID and same Board ID for CP9000 A and B: CP9000 A channel x board y can only be paired with CP9000 B channel x board y.

**Parent topic:**Product Overview
