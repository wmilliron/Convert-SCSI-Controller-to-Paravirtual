# Convert VMware SCSI Controller to Paravirtual for a Windows VM

## SYNOPSIS

    This script will convert the SCSI adapter of a Windows VM running on VMware to Paravirtual.

## DESCRIPTION

### Prerequisites

        1. Powershell 3.0 or newer
        2. PowerCLI
        3. Run the script as a user with administrative permissions within the OS of the VM being altered. If that same account does not have permissions to vCenter, a prompt for credentials will appear during runtime.
        4. VMware tools must be installed, updated, and running on the target VM.

### Assumptions

        1. The target VM is connected to a network that is routable from the machine running the script.
        2. All WinRM ports are open to the target VM.

## PARAMETER VMName

    Required parameter. Specify the name of the target VM for SCSI controller conversion. If the VM name has spaces, wrap it in quotation marks (Example ConvertSCSItoParaVirtual.ps1 -VMName "App Server 1" -vCenter vcsa01.domain.com).

## PARAMETER vCenter

    Required parameter. Specify the name of the vCenter server appliance (or ESXi host) that the target VM resides on.

## EXAMPLE

    Usage:
    > ConvertSCSItoParavirtual.ps1 -VMName "appserver1" -vCenter vcsa01.domain.com

## NOTES

    Author: wmilliron
    Date: 8/2018

    Future releases will include
    *Multi-VM conversions
    *Bug fixes
