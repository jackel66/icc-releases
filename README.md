# ICC releases

Installers for the Infrastructure Command Center (ICC). This repository holds compiled
packages and release notes only; the source code is not published.

ICC is a single dashboard over backup, storage, virtualization, cloud, network and DNS
platforms (Cohesity, NetApp, Pure Storage, Dell OpenManage, VMware vCenter, Aria Automation,
Aria Operations, Zerto, Veritas NetBackup, Nutanix, Proxmox VE, AWS, EON, Ubiquiti UniFi,
Brocade SAN, BlueCat, LogicMonitor), with computed service status, an operations agent,
application service views, Server 360, topology, a configuration change ledger and optional
AI analysis behind an anonymization layer.

## Download

Go to the Releases page of this repository and pick the package for your platform:

| Package | Platform | Notes |
|---|---|---|
| icc-setup-<version>-x64.exe | Windows Server 2019 or later, Windows 10/11 (x64) | Wizard installer, two Windows services, private Node runtime |
| icc-<version>-1.x86_64.rpm | RHEL, Rocky, Alma 8 or later (x86_64) | dnf install, systemd units, private Node runtime under /opt/icc |
| icc-<version>-linux-x64.tar.gz | Ubuntu 22.04 or later | Extract and run deploy/install.sh |

Every release lists the SHA256 of each file. Check it after downloading.

## First run

1. The installer asks for a licence key. Leave it empty to start a 30-day trial; a key can be
   entered later under Global Settings.
2. Pick the platforms to start with. Nothing is ticked by default and at least one is
   required. Platforms left unpicked can be added later from the Marketplace.
3. The first account is User Admin / Password Admin. The dashboard asks for a new password at
   the first sign-in.
4. Windows opens http://localhost:3001/ when the installer finishes. On Linux the installer
   prints the address.

Silent install on Windows:

    icc-setup-1.0.0-x64.exe /VERYSILENT /LICENSEKEY=... /PORT=3001 /PLATFORMS=cohesity,vcenter

The Windows installer is not code-signed yet, so SmartScreen warns on first run.

## Upgrades

Run the newer installer over the existing install. Data, installed packs, logs and the .env
file are kept on every platform.

## Licence

See LICENSE. Production use needs a licence key; evaluation is time-boxed to the trial.
