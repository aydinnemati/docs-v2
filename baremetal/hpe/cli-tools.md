# HPE cli tools

https://downloads.linux.hpe.com/sdr/repo/mcp/pool/non-free/

# HPE iLO 4 Management Tools for Ubuntu Servers

This guide provides instructions for installing and using HPE's server management tools for ProLiant servers with iLO 4 on Ubuntu servers from version 16.04 and above.

## Introduction

HPE ProLiant servers come with integrated management features through the Integrated Lights-Out (iLO) interface. For Linux-based operating systems like Ubuntu, HPE provides a set of command-line utilities that allow you to:

- Monitor server hardware health
- Manage RAID controllers and configurations
- Configure iLO settings from within the OS
- Access detailed system information

## Available Tools

The main HPE management tools for Ubuntu servers include:

1. **ssacli** - Smart Storage Administrator CLI (formerly hpssacli/hpacucli) for managing RAID controllers
2. **hp-health** - System health monitoring and management
3. **hpasmcli** - Command-line interface for hardware health and configuration (included in hp-health)
4. **hponcfg** - Command-line tool for configuring iLO settings from the OS
5. **amsd/ams** - Agentless Management Service for iLO-OS communication

## Repository Setup by Ubuntu Version

To install these tools, you'll need to add HPE's Management Component Pack (MCP) repository. The repository URL varies by Ubuntu version.

### Ubuntu 16.04 (Xenial)

```bash
# Add repository
sudo echo "deb http://downloads.linux.hpe.com/SDR/repo/mcp xenial/current non-free" | sudo tee /etc/apt/sources.list.d/mcp.list
```

### Ubuntu 18.04 (Bionic)

```bash
# Add repository
sudo echo "deb http://downloads.linux.hpe.com/SDR/repo/mcp bionic/current non-free" | sudo tee /etc/apt/sources.list.d/mcp.list
```

### Ubuntu 20.04 (Focal)

```bash
# Add repository
sudo echo "deb http://downloads.linux.hpe.com/SDR/repo/mcp focal/current non-free" | sudo tee /etc/apt/sources.list.d/mcp.list
```

### Ubuntu 22.04 (Jammy)

```bash
# Add repository
sudo echo "deb http://downloads.linux.hpe.com/SDR/repo/mcp jammy/current non-free" | sudo tee /etc/apt/sources.list.d/mcp.list
```

## Import HPE GPG Keys

After adding the repository, you need to import the HPE GPG keys:

```bash
wget -qO- http://downloads.linux.hpe.com/SDR/hpPublicKey1024.pub | sudo apt-key add -
wget -qO- http://downloads.linux.hpe.com/SDR/hpPublicKey2048.pub | sudo apt-key add -
wget -qO- http://downloads.linux.hpe.com/SDR/hpPublicKey2048_key1.pub | sudo apt-key add -
wget -qO- http://downloads.linux.hpe.com/SDR/hpePublicKey2048_key1.pub | sudo apt-key add -
```

## Installing the HPE Management Tools

Update package lists and install the tools:

```bash
sudo apt update
sudo apt install hp-health hponcfg amsd ams ssacli ssaducli ssa
```

**Note:** Some packages might not be available for newer Ubuntu versions. If you encounter errors, try installing the packages individually.

## Direct Download Links

If you prefer to download and install packages manually, here are the direct download links:

### ssacli Package

The latest ssacli packages can be found at the HPE Software Delivery Repository:
- [HPE Software Delivery Repository - MCP Pool](https://downloads.linux.hpe.com/sdr/repo/mcp/pool/non-free/)

For direct download of specific versions:
- [ssacli-6.40-6.0_amd64.deb](https://downloads.linux.hpe.com/sdr/repo/mcp/pool/non-free/ssacli-6.40-6.0_amd64.deb) (Latest Version)
- [ssacli-5.30-6.0_amd64.deb](https://downloads.linux.hpe.com/sdr/repo/mcp/pool/non-free/ssacli-5.30-6.0_amd64.deb) (Older Version)

### hp-health Package

For hp-health, you may need to download it manually for newer Ubuntu versions:
- [hp-health_10.80-1874.10_amd64.deb](http://downloads.linux.hpe.com/SDR/repo/mcp/pool/non-free/hp-health_10.80-1874.10_amd64.deb)

To install a downloaded package:
```bash
sudo dpkg -i package_name.deb
sudo apt -f install  # Resolve dependencies if needed
```

## HPE MIB Kit for SNMP Monitoring

For SNMP monitoring, you can download the HPE MIB Kit:
- [HPE Systems Insight Manager - MIB Kit](https://support.hpe.com/hpesc/public/docDisplay?docId=emr_na-c04272529)

## Using the Management Tools

### Server Information

To view detailed server information:

```bash
sudo hpasmcli -s "show server"
```

Example output:
```
System        : ProLiant DL380p Gen8
Serial No.    : CZ12345678
ROM version   : P71 10/31/2015
iLo present   : Yes
...
```

### Temperature and Fan Information

```bash
sudo hpasmcli -s "show temp"
sudo hpasmcli -s "show fans"
```

### RAID Controller Information

To view your RAID controller configuration:

```bash
sudo ssacli ctrl all show config
```

For detailed controller information:

```bash
sudo ssacli ctrl all show detail
```

To check status of physical drives:

```bash
sudo ssacli ctrl slot=0 pd all show detail
```

### Configuring iLO from the OS

The `hponcfg` tool allows you to configure iLO settings directly from the OS. Here's a basic example:

```bash
sudo hponcfg -f /path/to/ilo-settings.xml
```

## Troubleshooting

### Package Not Found

If you encounter "Package not found" errors:
1. Make sure the repository is properly added
2. Try using a different Ubuntu version in the repository URL
3. Some packages may not be available for newer Ubuntu versions

### RAID Controller Not Detected

If your RAID controller is not detected:
1. Check if the controller is recognized by Linux: `lspci | grep RAID`
2. Ensure the driver is loaded: `lsmod | grep hpsa`
3. Try loading the module: `sudo modprobe hpsa`

## Additional Resources

- [HPE Management Component Pack](https://downloads.linux.hpe.com/SDR/project/mcp/)
- [HPE Support Center](https://support.hpe.com)
- [HPE iLO 4 User Guide](https://support.hpe.com/hpesc/public/docDisplay?docId=c03334051)