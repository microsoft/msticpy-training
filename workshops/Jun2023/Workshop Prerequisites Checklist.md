# MSTICPy Jun 2023 Workshop Prerequisites

You will need the following to fully participate in the interactive training
using working notebooks. Please review both of the sections below:
* Access to notebook environment
* Access to Data Sources, Threat Intel providers, etc.

In most cases you will need to clone the `msticpy-training` GitHub repo,
so will need Git installed. https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

The training repo is at https://github.com/microsoft/msticpy-training

---

## Access to notebook environment

There are several options here:

### 1. Install Anaconda and VS Code

Students should have a device with VSCode installed alongside the Python and Jupyter extensions.
Anaconda Installed - https://www.anaconda.com/
Detailed instructions for this are in the repo README file - https://github.com/microsoft/msticpy-training/blob/main/README.md

### 2. Use VSCode plus a Docker DevContainer

This lets you work with the notebooks fully from VSCode without having to install Python
locally.
Detailed instructions for this are also in the repo README file - https://github.com/microsoft/msticpy-training/blob/main/README.md

### 3. Using a docker container with Jupyter classic

This is an option that uses the classic Jupyter browser-based interface
to navigate and run the notebooks. This is less fully-featured than the
first two options but avoids having to install either VSCode or Python locally.

### 4. Using Read-only copies of the notebooks to follow along
You can browse and view the notebooks directly on the GitHub repo.
You can view but not execute the notebooks here. (There is an option
to run the notebooks in Github.dev but we don't have support for that directly.
Feel free to try this out.)

---

## Access to Data Sources, Threat Intel providers, etc.

There are a few data services needed for the workshops.

### 1. The CyberSecuritySOC Sentinel Demo workspace

Request access to https://aka.ms/JoinAzureDemo in order to have a data environment to work with.

### 2. Azure KeyVault
Create a KeyVault to experiment with (or bring details of one along if you want to use
an existing Vault). https://ms.portal.azure.com/#browse/Microsoft.KeyVault%2Fvaults

Ensure that you have the following data for the Vault:
* Vault name
* SubscriptionId
* ResourceGroup

### 3. Threat Intel and GeoIP provider accounts
In addition, students should sign up for some free accounts in advance so they can be used during the training.
Sign up for the account and ensure that you record and safely store the API keys for these services.

* VirusTotal - https://www.virustotal.com/gui/join-us
* GeoIPLite - https://dev.maxmind.com/geoip/geolite2-free-geolocation-data?lang=en

(and optionally)
* Alienvault OTX - https://otx.alienvault.com/dashboard/new
* IBM XForce - https://exchange.xforce.ibmcloud.com/

Note: for IBM XForce, you need to record both a API Key and a User ID.