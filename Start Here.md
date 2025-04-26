# Project Overview
Objectives:
1) Detect Lazagne attack
2) Configure EDR Rules in LimaCharlie
3) Design a working workflow through Tines 
4) Send a message to user through Gmail and Slack
## Workflow Created Using Tines
![[Pasted image 20250427023050.png]]

![[Pasted image 20250427023145.png]]
There is an option to isolate the machine(disconnecting the device from the network) so when the workflow is executed and telemetry is detected, the user will be prompted a message to isolate the machine or not.
## Slack
![[Pasted image 20250427032421.png]]
Message will be sent to slack about the details of the machine and what the threat actor did.
## Email Message
![[Pasted image 20250427032505.png]]
Message will be sent to Gmail about the details of the machine and what the threat actor did.