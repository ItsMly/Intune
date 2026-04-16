# BIOS Certificate-Based Authentication

This folder contains scripts for implementing certificate-based authentication in a Windows Autopilot pre-provisioned deployment.

## Overview

This solution replaces legacy BIOS Supervisor Passwords (SVP) with certificate-based authentication, enabling secure, passwordless BIOS management at scale for Lenovo Think devices.

## Contents

- **New-AzKeyVaultCertificate.ps1** - Generates a self-signed X.509 certificate in Azure Key Vault with HSM protection
- **Install-LnvBiosCertificate.ps1** - Installs the public certificate on the device during Autopilot ESP, converting the BIOS to certificate-based authentication
- **Set-LnvBiosSettings.ps1** - Applies configured BIOS settings using signed WMI commands with the private key from Azure Key Vault

## Prerequisites

- Commercial Lenovo Think device (ThinkPad/ThinkCentre/ThinkStation) with Supervisor Password set
- Azure Key Vault (Premium tier for HSM-backed keys)
- Service principal with Key Vault Administrator and Crypto User roles
- [Lenovo BIOS Certificates Tool (LBCT)](https://docs.lenovocdrt.com/guides/lbct/)
- [Think BIOS Config Tool V2](https://docs.lenovocdrt.com/guides/tbct_v2/tbct_v2_top/)
- Az.KeyVault and Az.Accounts PowerShell modules

## Reference

[Certificate-based Authentication in an Autopilot Pre-provisioning Deployment](https://blog.lenovocdrt.com/deep-dive---certificate-based-authentication-in-an-autopilot-pre-provisioning-deployment/)
