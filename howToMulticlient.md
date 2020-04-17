## Step by Step: How to use the Ethereum 2.0 Multiclient

This guide will be designed for **non technical** people. It will focus on **Windows10 and MacOs**. This guide will be an ongoing process and will be updated as we collect feedback and adapt to the most recent changes! 

There will be **multiple ways** to join the ETH2.0 Testnet (different clients).

**System requirements: Recommended: 8GB RAM, 100GB SSD , Minimum: 4GB RAM, 20GB SSD.**

Before we start off, reading the [glossary](https://kb.beaconcha.in/glossary) is recommended but not required.

---

### Overview

#### [Prysmatic Labs](https://prysmaticlabs.com/)

- Windows 10

    - Windows 10 w/Binary files (.exe)
    - Windows **10 Pro** w/Docker
    - Prysm.sh script
    
- macOS

    - something
    - Docker
    - Prysm.sh script 
    
#### [Lighthouse](https://lighthouse.sigmaprime.io/)
  
---
### [Prysmatic Labs - Topaz Testnet](https://prysmaticlabs.com/)

#### Windows 10 w/Binary files (.exe)

##### Beaconchain

<ins>Step 0.</ins> 

Open the [Prysmatic Participation Page](https://prylabs.net/participate) and the [client release page](https://github.com/prysmaticlabs/prysm/releases)

<sub> **NOTE:** The description displayed on the **[Participation Page](https://prylabs.net/participate)** does not work for Windows. </sub>

<ins>Step 1.</ins> 

Press **Windows button + R** , type **cmd**, press enter. A **black** window called **command prompt** should appear. Copy and paste the following code:

`reg add HKCU\Console /v VirtualTerminalLevel /t REG_DWORD /d 1`

<sub> This will change the looks of the command prompt output later </sub>

<ins>Step 2.</ins> 

**Download** the newest versions of the Beaconchain **and** Validator. The version name might have changed because of an update, but the file name should similar (green mark on the picture below).

![Prysmatic_DownloadPage](https://user-images.githubusercontent.com/26490734/79451678-33b69c80-7fe7-11ea-80c8-b92c75fbb937.png)

<ins>Step 3.</ins> 

Find the files that have been downloaded. Usually located in the "Downloads" folder

<ins>Step 4.</ins> 

Open the beaconchain file - **beacon-chain**-v1.0.0-alpha.2-<ins>windows-amd64</ins>.exe - a **warnining** should appear. **Click** on "More Info" and then "Run anyway".

![Prysmatic_DownloadWarning](https://user-images.githubusercontent.com/26490734/79451935-a1fb5f00-7fe7-11ea-875d-f443afe24b09.png)

1. **If this does not work**, you can also open a "Command Prompt" window and drag&drop the beaconchain file into it and press enter.
2. **If you get the error `The process cannot access the file because it is being used by another process`, you will need **manually** delete the "beaconchain.db" file.

##### Validator

<ins>Step 1.</ins> 

<!-- Make sure to have the Validator File as desribed [here, <ins>Step 1 and 2.</ins>](https://github.com/Buttaa/eth2-knowledge-base/blob/howToMultiClient/howToMulticlient.md#windows10) -->

<ins>Step 2.</ins> 

<!-- Open the validator file - **validator**-v1.0.0-alpha.2-<ins>windows</ins>-amd64 -->

#### VALIDATOR REQUIRES [A FIX BY PRYSM TEAM](https://github.com/prysmaticlabs/prysm/issues/5456#issue-601128068)
---

#### Windows **10 Pro** w/Docker

<ins>Step 1.</ins>

Make sure you have [Windows10 Pro](https://support.microsoft.com/en-us/help/13443/windows-which-version-am-i-running), otherwise you won't be able to get Docker working. 

<ins>Step 2.</ins>

[Installing Docker](https://docs.docker.com/docker-for-windows/install/), which is the "hardest" part and is different for everyone depending on the motherboard manufacturer. You will need to have "[Virtualization](https://docs.docker.com/docker-for-windows/troubleshoot/#virtualization-must-be-enabled)" enabled. 




