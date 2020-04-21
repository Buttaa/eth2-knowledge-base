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
    - - Installing Docker on Windows **Pro**
    - Windows **10 Pro** w/Docker 
    - - Installing Docker on Windows **Home**
    - Windows **Home** w/Docker
    - Prysm.sh script
    
- macOS

    - something
    - Docker
    - Prysm.sh script 
    
#### [Lighthouse](https://lighthouse.sigmaprime.io/)

- Windows 10

    - Windows 10 w/Binary files (.exe)
    - Windows **10 Pro** w/Docker
    - script
  
---
### [Prysmatic Labs - Topaz Testnet](https://prysmaticlabs.com/)

#### Windows 10 w/Binary files (.exe) - <ins>Beaconchain</ins>

<ins>**Step 0.**</ins> 

Open the [Prysmatic Participation Page](https://prylabs.net/participate) and the [client release page](https://github.com/prysmaticlabs/prysm/releases)

<ins>**Step 1.**</ins> 

Open a [Command Prompt](https://www.wikihow.com/Open-the-Command-Prompt-in-Windows) window and enter the following:

`reg add HKCU\Console /v VirtualTerminalLevel /t REG_DWORD /d 1`

<sub> This will change the looks of the command prompt output later </sub>

<ins>**Step 2.**</ins> 

**Download** the newest versions of the Beaconchain **and** Validator. The version name might have changed because of an update, but the file name should similar (green mark on the picture below).

<details>
  <summary>Picture to clarify</summary>
  
![Prysmatic_DownloadPage](https://user-images.githubusercontent.com/26490734/79451678-33b69c80-7fe7-11ea-80c8-b92c75fbb937.png)
</details>

<ins>**Step 3.**</ins> 

Find the files that have been downloaded. Usually located in the "Downloads" folder

<ins>**Step 4.**</ins> 

Open the beaconchain file - **beacon-chain**-v1.0.0-alpha.2-<ins>windows-amd64</ins>.exe - a **warnining** should appear. **Click** on "More Info" and then "Run anyway".

<details>
  <summary>Picture to clarify</summary>
  
![Prysmatic_DownloadWarning](https://user-images.githubusercontent.com/26490734/79451935-a1fb5f00-7fe7-11ea-875d-f443afe24b09.png) 
</details>

1. **If this does not work**, you can also open a "Command Prompt" window and drag&drop the beaconchain file into it and press enter.
2. **If you get the error** `The process cannot access the file because it is being used by another process`, you will need **manually** delete the "beaconchain.db" file.

#### Windows 10 w/Binary files (.exe) - <ins>Validator</ins> (REQUIRES [A FIX BY PRYSM TEAM](https://github.com/prysmaticlabs/prysm/issues/5456#issue-601128068))

<ins>**Step 0.**</ins> 

<!-- Make sure to have the Validator File as desribed [here, <ins>Step 1 and 2.</ins>](https://github.com/Buttaa/eth2-knowledge-base/blob/howToMultiClient/howToMulticlient.md#windows10) -->

<ins>**Step 1.**</ins> 

<!-- Open the validator file - **validator**-v1.0.0-alpha.2-<ins>windows</ins>-amd64 -->

---

#### Installing Docker on Windows **Pro**

<ins>**Step 0.**</ins>

Make sure you have [Windows10 Pro](https://support.microsoft.com/en-us/help/13443/windows-which-version-am-i-running)

<ins>**Step 1.**</ins>

[Downloading Docker](https://download.docker.com/win/stable/Docker%20Desktop%20Installer.exe), which is the "hardest" part and is different for everyone depending on the motherboard manufacturer. You will need to have "[Virtualization](https://docs.docker.com/docker-for-windows/troubleshoot/#virtualization-must-be-enabled)" enabled, which you can on your Taskmanager. [Docker Info Page](https://docs.docker.com/docker-for-windows/install/)

<details>
  <summary>Picture to clarify</summary>
  
![virtualization](https://user-images.githubusercontent.com/26490734/79853838-dba5de80-83c8-11ea-9fbf-d640c4bb1980.png)
</details>

---

<ins>**Step 0.**</ins>

Open a [Command Prompt](https://www.wikihow.com/Open-the-Command-Prompt-in-Windows) window and type `docker -v`. If installed correctly it should give you the Docker Version.

To get the latest testnet client version follow up with this:

1. `docker pull gcr.io/prysmaticlabs/prysm/beacon-chain:latest`

2. `docker pull gcr.io/prysmaticlabs/prysm/validator:latest`

<details>
  <summary>Picture to clarify</summary>
  
 ![pullValidator](https://user-images.githubusercontent.com/26490734/79550092-2efdf100-8098-11ea-948f-84cc150a2251.png)
</details>


<ins>**Step 1.**</ins>

Change Docker File sharing settings, Manually create a folder in that specific directory.

<details>
  <summary>Picture to clarify</summary>
  
 ![dockerWindows](https://user-images.githubusercontent.com/26490734/79551080-7c2e9280-8099-11ea-8886-0b739b7d12c1.png) 
</details>

<ins>**Step 4.**</ins>

Running the beaconchain:

Open a "Command Prompt" window and enter the following and press enter:

`docker run -it -v c:/prysm/:/data -p 4000:4000 -p 13000:13000 gcr.io/prysmaticlabs/prysm/beacon-chain:latest --datadir=/data`

The manually created folder should now have files including the beaconchain data.

<details>
  <summary>Picture to clarify</summary>
  
 ![installingBeacon](https://user-images.githubusercontent.com/26490734/79552684-a1240500-809b-11ea-9e84-8841cc4caba2.png)
</details>

<ins>**Step 5.**</ins>

Creating your ETH2 Keys:

Copy the following code, **replace** "YOUR-PC-USERNAME" with your PC user name: 

`docker run -it -v C:\Users\YOUR-PC-USERNAME\prysm\validator/prysm:/data gcr.io/prysmaticlabs/prysm/validator:latest --keystore-path=/data accounts create --password=changeme`

Once you press enter the output should look the image below. If you didn't change `--password=changeme` your validator keys will have this password by default. For simplicity, let's keep it this way for the testnet.

`C:\Users\YOUR-PC-USERNAME\prysm\validator/prysm` this is the location of your keys.

**Copy the Raw Transaction Data** (Yellow mark) and go to the [participation page](https://prylabs.net/participate).

<details>
  <summary>Picture to clarify</summary>
  
![validatorKeyGen](https://user-images.githubusercontent.com/26490734/79572401-2e2b8600-80bd-11ea-80b7-cedc798541be.png)
</details>

<ins>**Step 6.**</ins>

Getting 32 Goerli ETH (=Testnet ETH). If you cannot get any goerli ETH through the participation page join the [Prysm Discord](https://discord.gg/wJW7Rjk)

<details>
  <summary>Picture to clarify</summary>
  
![Participation](https://user-images.githubusercontent.com/26490734/79573699-53b98f00-80bf-11ea-8c7c-4092778bab7d.png)
</details>

<ins>**Step 7.**</ins>

Starting beaconchain & validator. 

Open **two** "Command Prompt" windows.

1. **First Command prompt window: Start the beaconchain**

`docker run -it -v c:/prysm/:/data -p 4000:4000 -p 13000:13000 gcr.io/prysmaticlabs/prysm/beacon-chain:latest --datadir=/data`

<sub> The blockchain data will be stored in the folder we manually created in Step 4 </sub>

2. **Second Command prompt window: Start your validator**

`docker run -it -v c:/prysm:/data --network="host" gcr.io/prysmaticlabs/prysm/validator:latest --beacon-rpc-provider=127.0.0.1:4000 --keystore-path=/data --datadir=/data --password=changeme`

<ins>**Step 8.**</ins>

Track your validator perfomance on [beaconcha.in](https://beaconcha.in/dashboard?validators=)

---


