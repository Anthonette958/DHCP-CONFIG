<!DOCTYPE h
<html lang="en"
<head>
    <meta charset="UTF-8">
    <title>DHCP Configuration - Cisco Packet Tracer Project</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 40px;
            background-color: #f4f6f8;
            color: #333;
        }
        h1, h2, h3 {
            color: #0a3d62;
        }
        table {
            border-collapse: collapse;
            width: 100%;
            margin-bottom: 20px;
        }
        table, th, td {
            border: 1px solid #ccc;
        }
        th, td {
            padding: 10px;
            text-align: left;
        }
        code {
            background-color: #e8eef2;
            padding: 4px 6px;
            border-radius: 4px;
        }
        pre {
            background-color: #1e272e;
            color: #ffffff;
            padding: 15px;
            overflow-x: auto;
            border-radius: 5px;
        }
        .section {
            margin-bottom: 40px;
        }
        .screenshot-container {
            text-align: center;
            margin-top: 20px;
        }
        .screenshot-container img {
            max-width: 100%;
            height: auto;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
        }
        .caption {
            font-style: italic;
            margin-top: 10px;
            color: #555;
        }
    </style>
</head>
<body>

    <h1>📡 DHCP Configuration – Cisco Packet Tracer Project</h1>

    <div class="section">
        <h2>📘 Project Overview</h2>
        <p>
            This project demonstrates the configuration and implementation of 
            <strong>Dynamic Host Configuration Protocol (DHCP)</strong> in Cisco Packet Tracer.
        </p>
        <p>
            DHCP automatically assigns IP addresses and other network parameters 
            such as subnet mask, default gateway, and DNS server to client devices.
        </p>
        <ul>
            <li>A router is configured as a DHCP server.</li>
            <li>Multiple PCs obtain IP addresses dynamically.</li>
            <li>Network connectivity is verified using ping tests.</li>
        </ul>
    </div>

    <!-- Screenshot Section -->
    <div class="section">
        <h2>🖼️ Project Screenshot</h2>
        <div class="screenshot-container">
            <!-- Replace the src path with your actual screenshot file -->
            <img src="images/dhcp-topology.png" alt="DHCP Packet Tracer Topology Screenshot">
            <div class="caption">
                Figure 1: Cisco Packet Tracer DHCP Network Topology
            </div>
        </div>
    </div>

    <div class="section">
        <h2>🧠 Objectives</h2>
        <ul>
            <li>Configure router interfaces with static IP addresses</li>
            <li>Enable DHCP service on the router</li>
            <li>Create DHCP pools</li>
            <li>Exclude specific IP addresses</li>
            <li>Automatically assign IP addresses to client PCs</li>
            <li>Verify connectivity</li>
        </ul>
    </div>

    <div class="section">
        <h2>🖥️ Network Topology</h2>
        <table>
            <tr>
                <th>Device</th>
                <th>Interface</th>
                <th>IP Address</th>
            </tr>
            <tr>
                <td>Router</td>
                <td>G0/0</td>
                <td>192.168.1.1</td>
            </tr>
            <tr>
                <td>PCs</td>
                <td>DHCP</td>
                <td>Assigned Automatically</td>
            </tr>
        </table>
    </div>

    <div class="section">
        <h2>⚙️ Step-by-Step DHCP Configuration</h2>

        <h3>Step 1: Configure Router Interface</h3>
        <pre>
enable
configure terminal
interface gigabitEthernet 0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
exit
        </pre>

        <h3>Step 2: Exclude IP Addresses</h3>
        <pre>
ip dhcp excluded-address 192.168.1.1 192.168.1.10
        </pre>

        <h3>Step 3: Create DHCP Pool</h3>
        <pre>
ip dhcp pool LAN_POOL
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8
exit
        </pre>

        <h3>Step 4: Configure PCs to Obtain IP Automatically</h3>
        <ol>
            <li>Click on a PC</li>
            <li>Go to Desktop</li>
            <li>Click IP Configuration</li>
            <li>Select DHCP</li>
        </ol>

        <h3>Step 5: Verify DHCP Assignment</h3>
        <pre>
ipconfig
        </pre>

        <h3>Step 6: Test Network Connectivity</h3>
        <pre>
ping 192.168.1.1
        </pre>
    </div>

    <div class="section">
        <h2>🎯 Conclusion</h2>
        <p>
            This project demonstrates how DHCP simplifies network administration 
            by automatically assigning IP addresses to devices. Instead of manually 
            configuring each device, the router dynamically distributes network 
            parameters, improving efficiency and reducing configuration errors.
        </p>
    </div>

</body>
</html>
