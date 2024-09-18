## About Wireshark
Wireshark is a free network protocol analyzer. It captures and displays sent and received live data from the network and allows to analyze this data using filters.

## Audience
This guide is for the users who begin studying network administration or data security, and for anyone interested in network analysis or concerned with their data safety. You will learn how to download, install and set up Wireshark and use it for capturing and filtering network traffic using the HTTP protocol. This guide applies to OS Windows.

## Download and install
1. Download Wireshark [from the official website](https://www.wireshark.org/#download). Choose the file for your OS (for example: Windows 64-bit)
2. Run the downloaded `*.exe` file.
[!download Wireshark](media/1-download page.jpg)

_Note: The Wireshark installer offers to install **Npcap**. It is a packet capture library for Windows that allows Windows software to capture raw network traffic. If you do not have it installed, agree by checking the checkbox._
[!install Npcap](media/2-installation page.jpg)

## Setup
When you run Wireshark, in the welcome screen, you see the list of network connections (or interfaces) available for your device. Next to each interface name, you see the live traffic line chart. Choose the required interface by double-clicking on the corresponding interface name. Traffic capture will start automatically.

To start, stop, and restart traffic capture, choose the corresponding button on the toolbar.
[!traffic capture controls](media/3-controls.jpg)

## Capture HTTP traffic
To start capturing HTTP traffic, open the required website in your browser. The main packet information is displayed in a table in the **Packet List Pane**. 
The table includes:
- time
- source
- destination IP
- used protocol
- packet length
-  brief information about the request

To study the HTTP packet in detail, select the packet and expand the **Hypertext Transfer Protocol** details in the **Packet Details Pane**.
[!http packet details](media/4-capture http.jpg)

## Filter HTTP traffic
Wireshark offers two types of filters: **Capture Filters** to capture the selected traffic, and **Display Filters** to analyze the captured traffic.

### Capture Filters
Prior to capturing the packets, assign a filter to the selected interface using the following options:
- The *Capture filter* field in the welcome screen
[!capture filter field](media/5-capture filters.jpg)

- The **Capture** menu on the main toolbar
[!capture menu](media/6-capture options.jpg)
1. Select **Capture > Capture Options**.
2. In the filter line, enter the necessary filter. It will be assigned to the selected interface.

The available filters show in the **Capture filters** section. Here, you can add and remove them.
[!list of filters](media/7-add remove filters.jpg)

### Display Filters
**Display filters** apply after you stop capturing the traffic. The most commonly used filtering options are as follows:
- Enter `HTTP` to display only the packets using the HTTP protocol.
[!filtering option 1](media/8-display filters case 1.jpg)

- Enter the protocol and port filter to display all the HTTP traffic, including handshake and termination TCP packets.
[!filtering option 2](media/9-display filters case 2.jpg)

- Use `and` / `or` operators to make filters with multiple parameters. For example, if you need to filter the HTTP traffic exchanged with a specific IP address, enter the two parameters into the display filter line.
[!filtering option 3](media/10-display filters case 3.jpg)

- Use `http.request.method` filter type to filter specific HTTP packets (GET, PUT, POST, DELETE, HEAD, CONNECT, TRACE, etc.). For example, to filter only GET requests, enter this filter into the display filter line.
[!image](media/11-display filters case 4.jpg)

To trace the full HTTP stream, right-click on the HTTP packet and choose **Follow > HTTP Stream**. You will see a window with the full stream: request (in red) and response (in blue).
[!full HTTP stream](media/12-stream outcome.jpg)