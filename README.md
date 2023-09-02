# Snort Windows Install
1. Download the executable file from [here](https://www.snort.org/downloads)
2. Open the file
3. click on agree
	1. ![0 2ZuWkqf1XP0x1vYP](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/7875a6da-5741-49f4-8f58-2f091e9e5be0)

4. Choose components of Snort to be installed
	1. ![0 4wAvMI1JDduraYb6 1](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/2972f09f-7141-4c3f-919b-eee90d352b3c)

5. Click "Next" and then choose install location for snort preferably a separate folder in Windows C Drive
	1. ![0 -72wEjG8eiI5pN8e](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/229ebc05-fedf-4963-995a-f7da95eb3386)

6. Click "Next" Installation process starts and then it completes as show:
	1. ![0 4v_cEgjirJF0GYLB](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/ced2d89d-6e23-4caf-84d3-fa709f73b20b)

7. When you click "Close" you are prompted with this dialogue box:
	1. ![0 W_AFWObMPUP-GwJB](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/58228a2c-3161-42c2-aeaf-1a2e2d839dcc)

8. Installing Npcap is required by Snort functioning
9. Npcap for Windows 10 can be downloaded from [here](https://npcap.com/) 
10. Opening Npcap setup file, Click on "I Agree" To license agreement
	1. ![0 90015rp3WfIwmHCe](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/17cd8096-8092-4bc8-8148-33b05a305312)

11. Now we proceed to choose which components of Npcap are to be installed then clicking on "Install" **Is importan select all the marked on the image**
	1. ![0 FKlNbx28qAO-S5jq](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/d914f228-5cd1-4b13-885a-d882a6b6fa85)

12. Installation process starts and completes. Clicking on "Next" we have:
	1. ![0 -TMBomENfQEuAOOF](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/94f9bfc6-afba-48a0-af46-66031e2fc8f3)

13. Now the window for installation of Npcap shows it has been installed Clicking "Finish"
	1. ![0 QOWWHxm9AwBb7tq1](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/9fcfd2ac-c939-4373-b648-02633b5745de)

14. After installing Snort and Npcap enter these commands in Windows CMD to check Snorts working
	1. ![0 m3PUPRURKYEDPiW6](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/35b979fc-7b87-4770-bb81-e6e1c22212d3)

15. As you can see in the above figure that snort runs successfully


# Config Rules
## Create Snort account
To download the correct rules folders before should create an account in the Snort Official Site, you can finde it [here](https://www.snort.org/users/sign_up)

## Download rules
After create your account visit [this](https://www.snort.org/downloads/#rule-downloads) to download the rules, I recommend download the last version on Snort v2.9 but you can chose your preferred  rules package
![Pasted image 20230901105251](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/edd05914-d7d9-414b-83cd-5e5820a5fd67)

**Note**
If you don't create an account the page will block the links needed and you will see something like this:![Pasted image 20230901104657](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/3fd3e6d7-3df4-4b54-b736-0c7caa3520cb)


### Recommendations over download rules step
#### Windows defender block the rules package download
If Windows defender block your download turn off every antivirus this false positive is by the patterns of the Snort rules
#### VirusTotal false positive
If you check the package with VirusTotal you can see a False positive as [here](https://www.virustotal.com/gui/file/223b863e30ab7512a165888611a61ae876118c7daef72396bf136b78a87b2539/summary) 

# Config NIDS
## Setup Folders
Once extracted the folder from the compressed rules file you can see 4 folders
1. etc
2. preproc_rules
3. rules
4. so_rules
![Pasted image 20230901110556](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/22d557ee-6d44-4a24-b6ec-e6bbf5a58aeb)


You can cut and paste this folder over the Legacy
 folder in your Snort installation path, in my case "C:\\Snort"
![Pasted image 20230901110959](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/dece7211-b790-4e16-9a7d-ce0b66c4e1a3)


Then we will modify the "snort.conf" file stored in the "etc" folder ![Pasted image 20230901111311](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/e5f84ceb-bebf-4ce2-a3a0-4b39dce1a817)

This folder is important to config some NIDS parameters and PATHs.

To facilitate the work I will leave you a modified version of the file [here](), you just should change the HOME_NET variable.

## snort.conf manual config
We are going to open the file with some text editor, I recommend some text editor with line count to facilitate the process, I will use [Sublime Text](https://www.sublimetext.com/) 

We start setting the HOME_NET variable, this variable refers to the Network Section for monitoring

If you don't know in which section is you computer just type "ipconfig" on your cmd
![Pasted image 20230901112707](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/46dd707c-2934-4503-801e-abf42995d240)

In my case y will use the 192.168.1.0/24 based on my Netmask and my computer IP

The Legacy
 line of the HOME_NET variable look like this

![Pasted image 20230901113009](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/ad56c428-02b0-4581-b27a-18e713e0323f)


Then look like this 

![Pasted image 20230901113159](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/e455a1fa-437f-4d44-a57d-b46ffddae768)


Next setup the external network address EXTERNAL_NET
In this case will set every network address who isn't the HOME_NET, to do it just will type !$HOME_NET

Legacy


![Pasted image 20230901113323](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/e675c534-004b-4e7b-a405-cdc2038ccde8)


New



![Pasted image 20230901113604](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/8b1b9650-d4ab-4d53-987a-0939730a652d)


Now we have to define the directory for our rules and preproc rules folder, the path of the folders are the same of the Snort installation folder plus the name of the corresponding folder. In this case:
- C:\\Snort\\rules
- C:\\Snort\\preproc_rules
For the case of the SO_RULE_PATH just we will add to the begin of the line a "#" to comment the line

Legacy


![Pasted image 20230901113753](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/3b8ea0ed-80f8-48ba-817d-6701b47cf71f)


New



![Pasted image 20230901114253](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/d7685c80-aae5-4155-b60b-3510c0868c4c)


Once set the last variables, we have to setup the white list and black list path in the Snort rules folder in my case "C:\\Snort\\rules"

Legacy


![Pasted image 20230901114632](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/db74b975-0eb6-4652-a847-8191ad5c9d34)


New



![Pasted image 20230901114725](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/5c164419-a04e-4f3c-bc8a-4fe0a1cde74e)


Is essential set the log directory to store the logs, to do it we will uncomment this and add the path of your log folder, in my case "C:\\Snort\\log" 

Legacy


![Pasted image 20230901114958](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/8d80f39c-b74a-45aa-90d6-43b22d800168)


New


![Pasted image 20230901115043](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/cb5e9974-4072-40c9-8721-94c82d8a5cb2)


Next we will set the path to dynamic preprocessors 
"C:\\Snort\\lib\\snort_dynamicpreprocessor"

Legacy

![Pasted image 20230901152234](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/5224b402-fcf0-4bfc-bae8-8aaaed53431d)


New

![Pasted image 20230901152321](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/63637e6c-5507-40c3-a5ac-d210afa57221)


For dynamic preprocessor engine we will add the path and the .dll file in the path
"C:\\Snort\\lib\\snort_dynamicengine\\sf_engine.dll"

Legacy

![Pasted image 20230901152356](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/ab56b17b-4373-4743-91b9-57cd73244a6e)


New


![Pasted image 20230901160937](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/a7237941-4bc7-4546-b47b-62a2afa83a5b)


We will comment this lines
![Pasted image 20230901161237](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/e536d8fd-c9df-4bee-957c-d9f3c56af2ff)


We need change the decompress_swf { deflate lzma } to { deflate } like this

Legacy

![Pasted image 20230901174402](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/63da013f-eec2-4b00-a166-cc5c0d7559de)


New


![Pasted image 20230901174429](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/f55e2698-8488-47a6-b9d0-e47230268ade)


Now we will convert ALL the forward slashes on $RULE_PATH/ to back slashes

Legacy

![Pasted image 20230901162217](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/e52e98db-5375-45cb-83fb-63ef18a348a0)


![Pasted image 20230901162241](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/d082fa09-5970-4fb9-9377-362838f9d891)


New


![Pasted image 20230901162449](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/d395a3a3-390b-4a80-b0fe-c7f537bb29db)

![Pasted image 20230901162520](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/da7479a1-0720-4dcc-9257-7fcae8aaf810)


And the same to $PREPROC_RULE_PATH\ plus uncomment

Legacy

![Pasted image 20230901162810](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/d3747061-3077-4ffb-8701-41c212a97028)


New

![Pasted image 20230901162836](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/b7efbf3b-366a-41fb-9182-c3767310a64a)


Finally in this file, take a look if "include threshold.conf" is in the last line and save
![Pasted image 20230901162943](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/be9b39b9-ae41-4af6-9a5e-b62a0d3cdf0a)

## Windows 10
If you want to install Snort on Windows 10 you also need to do this steps
Else, your config is done

We need rename the white_list.rules to white.list, black_list.rules to black.list, change the forward slash to back slash and uncomment the lines

Legacy

![Pasted image 20230901161640](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/7d54997f-303e-4dd4-a33c-7e7f12124284)


New


![Pasted image 20230901161828](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/2b6cfade-e144-4a2f-8b4c-f500e6ee44ef)


Open a cmd on your Snort rules folder and create a file named white.list and black.list, this will be your files referred before. to do it you can use 
```cmd
C:\Snort\rules type nul > white.list
C:\Snort\rules type nul > black.list
```

![Pasted image 20230901163541](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/e88f31b8-6835-4efe-a15a-9eda074ac579)


And now open each file with your text editor and
For white.list add this line
```txt
#White-listed IPs
```
![Pasted image 20230901163716](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/8683a44d-d88a-4a9b-87a0-ec39c4935a8d)

save and close

And in the black.list add
```txt
#Black-listed IPs
```
![Pasted image 20230901163900](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/6277cd5a-d829-4a2e-9977-3c9a88492f3c)

save and close

# Test config

once you have your configuration ready is time to test them
use 
``` cmd
C:\Snort\bin\snort -W
```
to show all your interfaces, and search your computer IP, in my case is the interface 9
![Pasted image 20230901175604](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/1830e8bd-1db8-4f2c-8062-906f72c13e9b)


Once having your interface number we proceed to use
```cmd
C:\Snort\bin\snort -i 9 -c C:\Snort\etc\snort.conf -T
```
![Pasted image 20230901180757](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/c8152227-5da8-4f18-971c-9d802b209d38)


If everything goes right, you should see a large output and this on the bottom
![Pasted image 20230901180717](https://github.com/CesarGBkR/Snort_Windows/assets/99093357/9946d4cb-0a82-49f1-aff2-e8b6c3f0b687)

## References
https://zaeemjaved10.medium.com/installing-configuring-snort-2-9-17-on-windows-10-26f73e342780
https://www.youtube.com/watch?v=7XqWVfsnQ8k&ab_channel=CesarDarioCordobaVidal
https://groups.google.com/g/mailing.unix.snort/c/RLeiOkPtQik
