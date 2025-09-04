## Introduction
This script provides comprehensive system inspection functionality, helping administrators promptly identify and resolve potential issues to ensure system security.

Based on the open-source program '一键自动化巡检服务器' for modifications, copyright belongs to the original author (零氪的云原生).

## Functionality Overview

1. **Permission Check**
   - **Function**: Checks whether the script is running with root privileges to ensure sufficient permissions for executing system checks.

2. **Dependency Check**
   - **Function**: Verifies whether necessary tools (such as `sysstat`, `iotop`, `net-tools`) are installed. If any tools are missing, the script attempts to install them automatically.

3. **Basic System Information**
   - **Function**: Retrieves and displays basic system information, including the operating system version, kernel version, hostname, IP address, and system uptime.

4. **Environment Variable Security Check**
   - **Function**: Analyzes the `PATH` environment variable to check for dangerous paths, scans for sensitive environment variables, and checks the permissions of environment configuration files.

5. **System Handle Count Analysis**
   - **Function**: Examines the usage of system handles, including the maximum number of handles, currently used handles, and remaining available handles, as well as analyzing handle usage rates.

6. **System Performance Monitoring**
   - **Function**: Analyzes the performance of CPU, memory, disk, and network, displaying CPU usage, memory usage, disk I/O performance, and network traffic.

7. **System Security Check**
   - **Function**: Checks user security (such as accounts with empty passwords and privileged users), permissions of critical files, and the configuration of SSH and firewalls.

8. **Service and System Update Check**
   - **Function**: Checks the status of critical services and lists available system updates and security updates.

9. **Log and Cron Job Check**
   - **Function**: Inspects system error logs, failed login records, and scheduled tasks to identify potential risks.

10. **Inspection Summary**
    - **Function**: Outputs a summary of the inspection results, including key points of concern, and saves the report to a specified file.


# Usage Instructions for the System Inspection Script

## Prerequisites
- Ensure you have root privileges to run the script. You can use `sudo` to execute it if you are not logged in as the root user.
- The script requires certain dependencies to be installed. These include `sysstat`, `iotop`, and `net-tools`. The script will attempt to install any missing dependencies automatically.

## Running the Script

1. **Download the Script**
   - Copy the script code into a text editor and save it as `system_inspection.sh`.

2. **Make the Script Executable**
   - Open a terminal and navigate to the directory where the script is saved.
   - Run the following command to make the script executable:
     ```bash
     chmod +x system_inspection.sh
     ```

3. **Execute the Script**
   - To run the script, use the following command:
     ```bash
     sudo ./system_inspection.sh [output_file_name]
     ```
   - Replace `[output_file_name]` with your desired name for the report file (optional). If you do not provide a name, the default format will be `system_inspection_YYYYMMDD_HHMMSS.log`.

4. **Review the Output**
   - After the script completes, it will generate a log file containing the inspection results. You can view this file using any text editor or by using the `cat` command:
     ```bash
     cat system_inspection_YYYYMMDD_HHMMSS.log
     ```

## Tips
- It is recommended to run this script periodically (e.g., weekly or monthly) to maintain system health and security.
- Review the generated report carefully to address any identified issues or warnings.

