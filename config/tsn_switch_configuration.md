# AccessTSN Industrial Use case Demo - Switch Configuration
The central tsn switch of the industrial use case demo needs to be configured to support the converged traffic of the use case. Since tsn-ready switches from multiple manufacturers are available which do not have a common configuration interface (at least as of November 2020) the configuration is given here in text form and not as a ready to use configuration file.

## General parameters
- IEEE802.1AS should be available and activated on the used ports
- The forwarding of the used multicast MAC-Addresses should be ensured

## Gate Control List
The gate control list ist derived from the overall network schedule explained in the traffic_schedule-file in the *doc/usecase* subdirectory. For the gate control list it is assumed, that the devices used in the setup are connected to the switch ports in the following matter.

| Switch Port No.     | Device (function)           | 
| :-----------------: |:----------------------:| 
| 1 | Control PC (Control) | 
| 2 | Drive PC (Simulation of drives|
| 3 | HMI| 
| 4 | Notebook/PC (OPC UA Client)       |
| 5 | Notebook/PC (Webview) |

In the following table the given time intervals indicated at which point in time the respective traffic class on teh respective port should be opened. The given seconds are specified from the start of the cycle. For each line a own queue should be used. For the shown gate control list a switch with eight traffic queues is assumed. Since not all queues are used, switches with less queues could also be used.

| Traffic Class | Port 1 | Port 2 | Port 3 | Port 4 | Port 5|
| ------------- |:------:|:------:|:------:|:------:|:------:|
| TC 7          | 500-1000µs|500-1000µs|500-1000µs|500-1000µs|always closed|
| TC 6          | 0-100µs and 300-500µs|0-100µs and 300-500µs|always closed|always closed|always closed|
| TC 5          | 100-300µs |always closed|100-300µs |always closed|always closed|
| TC 2          | 500-1000µs|always closed|always closed|500-1000µs|always closed|
| TC 0          | 500-1000µs|always closed|always closed|always closed|500-1000µs|
