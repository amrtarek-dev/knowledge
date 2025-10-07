Wireshark is one of the most potent traffic analyser tools available in the wild. There are multiple purposes for its use:  
- Detecting and troubleshooting network problems, such as network load failure points and congestion.
- Detecting security anomalies, such as rogue hosts, abnormal port usage, and suspicious traffic.
- Investigating and learning protocol details, such as response codes and payload data.

Wireshark GUI opens with a single all-in-one page, which helps users investigate the traffic in multiple ways. At first glance, five sections stand out.

| **Toolbar**                       | The main toolbar contains multiple menus and shortcuts for packet sniffing and processing, including filtering, sorting, summarising, exporting and merging.                                                                         |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Display Filter Bar**            | The main query and filtering section.                                                                                                                                                                                                |
| **Recent Files**                  | List of the recently investigated files. You can recall listed files with a double-click.                                                                                                                                            |
| **Capture Filter and Interfaces** | Capture filters and available sniffing points (network interfaces).  The network interface is the connection point between a computer and a network. The software connection (e.g., lo, eth0 and ens33) enables networking hardware. |
| **Status Bar**                    | Tool status, profile and numeric packet information.                                                                                                                                                                                 |

## PCAP files
By `file` menu or dragging and dropping the file, or double-clicking on the file to load a pcap.
this will open 3 panes:
  
| Packet List Pane    | Summary of each packet (source and destination addresses, protocol, and packet info). You can click on the list to choose a packet for further investigation. Once you select a packet, the details will appear in the other panels. |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Packet Details Pane | Detailed protocol breakdown of the selected packet.                                                                                                                                                                                  |
| Packet Bytes Pane   | Hex and decoded ASCII representation of the selected packet. It highlights the packet field depending on the clicked section in the details pane.                                                                                    |
To get the file data  view the details by following "**Statistics --> Capture File Properties"** or by clicking the **"pcap icon located on the left bottom"** of the window.

## Traffic Sniffing
**"shark button"** to start network sniffing (capturing traffic), 
the red button will stop the sniffing, 
and the green button will restart the sniffing process. 

The status bar will also provide the used sniffing interface and the number of collected packets.

## Packet Dissection
Packet dissection is also known as protocol dissection, which investigates packet details by decoding available protocols and fields. Wireshark supports a long list of protocols for dissection, and you can also write your dissection scripts. You can find more details on dissection [**here**](https://github.com/boundary/wireshark/blob/master/doc/README.dissector).

Every packet is fallowing the OSI layers to break down packets, Packets consist of 5 to 7 layers based on the OSI model.
- The Frame (layer 1)
- Source [mac] (layer 2)
- Source [IP] (layer3)
- Protocol [TCP/UDP] (layer 4)
- Segments
- Application protocol (layer 5)
- Application Data

## Packet Navigation
Wireshark calculates the number of investigated packets and assigns a unique number for each packet. (Packet Numbers)
You can use `Go` menu -> `Go to Packet` then number if packet

Find Packets
`Edit` menu -> `Find Packet` to make a search inside the packets.
1. it search in the packet panes (Packet List, Packet details, Packet bytes)
2. input types (String, Regex, Hex and Display filter) (checkbox for case sensitive)

## Export Packets
You can use the **"File"** menu to export packets.
- Export Specified Packets
- Export Packet Dissections
- Export PDUs to File
- Export TLS Session Keys
- Export Objects


## Time display format
By default, Wireshark shows the time in "Seconds Since Beginning of Capture", the common usage is using the UTC Time Display Format for a better view. You can use the "View --> Time Display Format" menu to change the time display format.


## Export Information
`Analyze` menu-> `Expert Information`
Wireshark also detects specific states of protocols to help analysts easily spot possible anomalies and problems.

>  these are only suggestions, and there is always a chance of having false positives/negatives.



## Packet Filtering
There are 2 filter:
- Capture :  Capture filters are used for **"capturing"** only the packets valid for the used filter.
- Display: Display filters are used for **"viewing"** the packets valid for the used filter.

- Apply as Filter: you can click on the field you want to filter and use the "right-click menu" or **"Analyse** **--> Apply as Filter"** menu to filter the specific value.

- Prepare as a Filter: Similar to "Apply as Filter", However, unlike the previous one, this model doesn't apply the filters after the choice. It adds the required query to the pane and waits for the execution command (enter) or another chosen filtering option by using the **".. and/or.."** from the "right-click menu".

- Conversation Filter: helps you view only the related packets and hide the rest of the packets easily. You can use the"right-click menu" or "**Analyse --> Conversation Filter**" menu to filter conversations

- Apply as Column: the packet list pane provides basic information about each packet. You can use the "right-click menu" or "**Analyse --> Apply as Column**" menu to add columns to the packet list pane.

- Follow Stream: Wireshark displays everything in packet portion size. However, it is possible to reconstruct the streams and view the raw traffic as it is presented at the application level. use the"right-click menu" or  **"Analyse** **--> Follow TCP/UDP/HTTP Stream"** menu to follow traffic streams. Streams are shown in a separate dialogue box;