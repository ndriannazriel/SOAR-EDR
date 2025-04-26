## Lazagne-SOAR-EDR D&R Rule in LimaCharlie
The point of this EDR rule is so that it detects a command line that is executed on the windows server 2022 machine if it matches "LaZagne.exe".

##### Detection Rule
```
events:
  - NEW_PROCESS
  - EXISTING_PROCESS
op: and
rules:
  - op: is windows
  - op: or
    rules:
      - case sensitive: false
        op: ends with
        path: event/FILE_PATH
        value: LaZagne.exe
      - case sensitive: false
        op: contains
        path: event/COMMAND_LINE
        value: LaZagne
      - case sensitive: false
        op: is
        path: event/HASH
        value: 3cc5ee93a9ba1fc57389705283b760c8bd61f35e9398bbfa3210e2becf6d4b05
```
##### Response Rule
```
- action: report
  metadata:
    author: ANDRIAN
    description: TEST - Detects Lazagne Usage
    falsepositives:
      - ToTheMoon
    level: high
    tags:
      - attack.credential_access
  name: ANDRIAN - HackTool - Lazagne
```

## Slack/Gmail message from Tines
```
Title: <<retrive.body.cat>>
Time: <<retrive.body.detect.routing.event_time>>
Hostname: <<retrive.body.detect.routing.hostname>>
Source IP: <<retrive.body.detect.routing.int_ip>>
Username: <<retrive.body.detect.event.USER_NAME>>
File Path: <<retrive.body.detect.event.FILE_PATH>>
Command Line: <<retrive.body.detect.event.COMMAND_LINE>>
Sensor ID: <<retrive.body.detect.routing.sid>>
Detection: <<retrive.body.link>>
```
