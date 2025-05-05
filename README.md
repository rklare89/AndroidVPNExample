# VPNFlagService: Android VPN-Based Domain Monitoring

## Overview
VPNFlagService is an Android application that leverages the Android `VpnService` API to monitor and log network traffic for specific domains. This project demonstrates advanced Android development skills, including low-level network programming, multi-threading, and secure DNS routing. It serves as a proof-of-concept for building a network sniffer that filters and logs access to flagged domains, showcasing expertise in Android system services and network packet analysis.

## Features
- **VPN Setup**: Establishes a virtual private network interface to intercept and analyze network traffic.
- **DNS Monitoring**: Routes DNS queries to Google's DNS server (8.8.8.8) and extracts domain names from UDP packets.
- **Dynamic Domain Flagging**: Maintains a list of flagged domains, updated periodically using a scheduled executor.
- **Traffic Logging**: Logs raw packet data and flagged domain access with timestamps for debugging and analysis.
- **Robust Error Handling**: Ensures graceful handling of network errors, socket protection, and resource cleanup.

## Technical Highlights
- **Tech Stack**: Java, Android SDK, Android `VpnService` API.
- **Network Programming**: Parses raw network packets to extract DNS query domains, demonstrating knowledge of IP and UDP protocols.
- **Concurrency**: Utilizes `ScheduledExecutorService` for periodic domain list updates and a dedicated `Thread` for traffic monitoring, ensuring efficient resource use.
- **Security**: Protects DNS sockets to prevent traffic leaks and securely manages VPN interface lifecycle.
- **Packet Analysis**: Implements custom logic to decode DNS packets, converting raw bytes to human-readable domains.

## How It Works
1. **Initialization**: The service starts by configuring a VPN interface with a private IP address (172.16.0.2) and routes DNS traffic to 8.8.8.8.
2. **Domain Management**: A `HashSet` stores flagged domains, updated every 60 seconds via a scheduled task.
3. **Traffic Monitoring**: A separate thread reads incoming packets, extracts domains from DNS queries, and logs access to flagged domains.
4. **Cleanup**: On service termination, the VPN interface is closed, and all threads are safely shut down.

## Why This Project Matters
This project showcases my ability to:
- Build complex Android system services using the `VpnService` API.
- Handle low-level network programming and packet parsing.
- Implement efficient concurrency patterns for real-time monitoring.
- Ensure robust error handling and resource management in a production-grade application.

## Potential Applications
- Network security tools for monitoring and filtering malicious domains.
- Parental control apps to restrict access to specific websites.
- Debugging tools for network traffic analysis on Android devices.

## Setup and Usage
1. **Prerequisites**: Android Studio, Android SDK (API 21+).
2. **Clone the Repository**:
   ```bash
   git clone <your-repo-url>
   ```
3. **Build and Run**: Open the project in Android Studio, sync Gradle, and deploy to an Android device or emulator.
4. **Permissions**: Grant VPN permissions when prompted by the Android system.
5. **Customize**: Modify the `initializeFlaggedDomains` method to add or update flagged domains.

## Future Enhancements
- Integrate a remote API to fetch flagged domains dynamically.
- Add a user interface to display real-time monitoring logs.
- Implement domain blocking by dropping packets for flagged domains.

## Contact
Feel free to reach out for collaboration or inquiries:
- LinkedIn: https://www.linkedin.com/in/rklare1989
- Email: allenklare33@gmail.com

---

*This project is a portfolio piece and not intended for production use without further security auditing and permissions handling.*
