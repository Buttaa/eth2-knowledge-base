## Step by Step: How to use the Ethereum 2.0 Multiclient

This guide will be designed for **non technical** people who have never coded before and focus on **Windows10 and MacOs**.
It will be an ongoing process and will be updated as we collect feedback and adapt to the most recent changes! 

There will be **multiple ways** to join the ETH2.0 Testnet (different clients).

**System requirements: Recommended: 8GB RAM, 100GB SSD , Minimum: 4GB RAM, 20GB SSD**
Before we start off, reading the [glossary](https://kb.beaconcha.in/glossary) is recommended but not required.


### [Prysmatic Labs - Topaz Testnet](https://prysmaticlabs.com/)

#### Windows10

##### Windows10 Beaconchain

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

Open the beaconchain file - **beacon-chain**-v1.0.0-alpha.2-<ins>windows-amd64</ins>.exe - a **red** warnining should appear. **Click** on "More Info" and then "Run anyway".

![Prysmatic_DownloadWarning](https://user-images.githubusercontent.com/26490734/79451935-a1fb5f00-7fe7-11ea-875d-f443afe24b09.png)

 TO BE CONTINUED ONCE GENESIS IS MINED.

##### Windows10 Validator

<ins>Step 1.</ins> 

Make sure to have the Validator File as desribed [here, <ins>Step 1 and 2.</ins>](https://github.com/Buttaa/eth2-knowledge-base/blob/howToMultiClient/howToMulticlient.md#windows10)

<ins>Step 2.</ins> 

Open the validator file - **validator**-v1.0.0-alpha.2-<ins>windows</ins>-amd64


