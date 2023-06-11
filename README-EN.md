# Security Patch Management with Ansible

This repository contains Ansible playbooks for managing security patches on Linux servers. The playbooks perform a series of pre-tasks to validate the system's state before applying the patches.

## Pre-Tasks

### Prerequisites

- Create a temporary directory to store patching results at `/tmp/patched`.
- Create a file to store the results of the post-tasks at `/tmp/patched/pre-tasks.txt`.

### Kernel Validation

- Validate the system's kernel.
- Show the kernel validation result.
- Save the kernel validation result to `/tmp/patched/pre-tasks.txt`.

### Validate Last Reboot Date

- Validate the system's last reboot date.
- Show the last reboot date.
- Save the last reboot date validation result to `/tmp/patched/pre-tasks.txt`.

### Validate Processes Requiring Restart and Their Corresponding Binaries (CentOS, Red Hat, Ubuntu)

- Validate processes requiring restart and their corresponding binaries.
- Show processes requiring restart and their corresponding binaries.
- Save the processes requiring restart and their corresponding binaries validation result to `/tmp/patched/pre-tasks.txt`.

### Verify Services Requiring Restart (Ubuntu)

- Verify services requiring restart.
- Show services requiring restart.
- Save the services requiring restart validation result to `/tmp/patched/pre-tasks.txt`.

### Validate Internet Access for Patch Downloads

- Validate internet access for patch downloads.
- Show the internet access for patch downloads.
- Save the internet access for patch downloads validation result to `/tmp/patched/pre-tasks.txt`.

### Validate Operating System Version

- Validate the operating system version.
- Show the operating system version.
- Save the operating system version validation result to `/tmp/patched/pre-tasks.txt`.

### Validate Service Status and Performance

- Validate the system's service status and performance.
- Show the service status and performance.
- Save the service status and performance validation result to `/tmp/patched/pre-tasks.txt`.

### Validate Required Patch List

- Validate the required patch list.
- Show the required patch list.
- Save the required patch list validation result to `/tmp/patched/pre-tasks.txt`.

### Validate Disk Space in the / Partition for Each Server

- Validate the disk space in the / partition for each server.
- Show the disk space in the / partition for each server.
- Save the disk space validation result in the / partition for each server to `/tmp/patched/pre-tasks.txt`.

### Review the Last 50 Historical Logs

- Review the last 50 historical logs.
- Show the last 50 historical logs.
- Save the last 50 historical logs validation result to `/tmp/patched/pre-tasks.txt`.

## Implementation Tasks

### Prerequisites

- Create a file to store the results of the implementation tasks at `/tmp/patched/implementation-tasks.txt`.

### Execute Security Patch Installation

- Execute the security patch installation.
- Show the security patch installation.
- Save the security patch installation result to `/tmp/patched/implementation-tasks.txt`.

### Server Restart after Patching

- Restart the server after patching.

### Validate SSH Connection 1 Minute After Restart

- Validate the SSH connection 1 minute after the restart.

### Validate Internet Access to Rule Out Connectivity Issues

- Validate internet access to rule out connectivity issues.
- Show the internet access status.

## Post-Tasks

### Prerequisites

- Create a file to store the results of the post-tasks at `/tmp/patched/post-tasks.txt`.

### Save Evidence of Installed Patches to a .txt File on the Server

- Save evidence of the installed patches to a .txt file on the server.
- Show the evidence of the installed patches in a .txt file on the server.
- Save the evidence of the installed patches to a .txt file on the server to `/tmp/patched/post-tasks.txt`.

### Monitor System Time, Hostname, and IP Address

- Monitor the system time, hostname, and IP address.
- Show the system time, hostname, and IP address.
- Save the system time, hostname, and IP address result to `/tmp/patched/post-tasks.txt`.

### Validate Server Restart after Patching

- Validate the server restart after patching.
- Show the server restart after patching.
- Save the server restart after patching result to `/tmp/patched/post-tasks.txt`.

### Validate Service Status and Performance

- Validate the system's service status and performance.
- Show the service status and performance.
- Save the service status and performance validation result to `/tmp/patched/post-tasks.txt`.

### Copy Patching Result to Ansible Server

- Copy the patching result to the Ansible server.
- Show the result sent to the Ansible server.
- Save the result of sending to the Ansible server to `/tmp/patched/post-tasks.txt`.

### Delete Patched Folder

- Delete the "patched" folder containing patching test files.

---
