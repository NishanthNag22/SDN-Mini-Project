# SDN Path Tracing Tool (POX + Mininet)

## Overview
This project implements a Software Defined Networking (SDN) based path tracing tool using the POX controller and Mininet network emulator. It provides real-time visibility into how packets traverse the network by intercepting OpenFlow messages and logging the hop-by-hop forwarding path.

## Features
* **Packet Interception:** Captures packets using the PacketIn mechanism.
* **Hop-by-Hop Tracking:** Tracks the forwarding path across multiple switches.
* **Route Visualization:** Displays the precise route between source and destination hosts in the controller terminal.
* **Connectivity Validation:** Built-in support for validating network state using Mininet's pingall.

## Setup & Installation

### 1. Prepare the Controller
Clone the POX repository and place your script in the misc folder:
- Clone POX: `git clone https://github.com/noxrepo/pox`
- Move your `path_trace.py` script into the `pox/misc` directory.

### 2. Run the POX Controller
Start the POX controller with the path tracing component:
- Run command: `./pox.py misc.path_trace`

### 3. Launch Mininet
In a separate terminal, launch a topology and point it to the remote controller:
- Run command: `sudo mn --topo single,3 --controller remote`

## Usage & Output
1. Run `pingall` in the Mininet CLI.
2. View the path logs in the POX controller terminal.

**Expected Output:**
- Displays path logs in the controller terminal.
- Verifies connectivity using pingall results.
