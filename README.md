# Detecting-Strange-Parent-Child-Relationships-Detecting-Malicious-.NET-Assembly-Loading
In this lab, I worked with Seatbelt and SilkETW to generate and capture .NET activity, then analyzed the telemetry to understand how suspicious assembly loading can be detected.


Running SilkETW



Here I’m navigating to the SilkETW directory to begin collecting .NET runtime events. This lets me see what happens behind the scenes when a tool like Seatbelt executes, which is useful for understanding how defenders detect .NET-based tooling.
<img width="1096" height="386" alt="image" src="https://github.com/user-attachments/assets/37b1cc0c-adb8-4da9-99ca-56e2a5f1d620" />


After fixing the path issue, SilkETW successfully started collecting .NET runtime events. At this point, it’s actively capturing method load activity, which I’ll use to analyze what happens when Seatbelt executes.
<img width="1912" height="914" alt="image" src="https://github.com/user-attachments/assets/ffdfa2ce-4997-40bf-ae2e-3cf0f1a62b91" />


Seatbelt

Here I’m running Seatbelt.exe TokenPrivileges to generate .NET activity. Seatbelt is a C# tool commonly used to gather system information during security testing. In this lab, I’m using it to trigger .NET method loads so I can capture and analyze that activity with ETW.
<img width="1686" height="473" alt="image" src="https://github.com/user-attachments/assets/b8669550-1359-4c7d-a2b2-5e7517e9dd33" />


After stopping SilkETW, I confirmed that the etw.json file was created in C:\Windows\Temp. This file contains the captured .NET runtime events that I’ll review to identify the method loads triggered by Seatbelt.
<img width="1551" height="577" alt="image" src="https://github.com/user-attachments/assets/415f28f8-52c0-4879-9976-4a2c2278f1c6" />

Finding .json file 
<img width="1092" height="601" alt="image" src="https://github.com/user-attachments/assets/6313c055-54d2-4a9c-882d-378e445bf8e1" />


Ctfr f

<img width="1530" height="549" alt="image" src="https://github.com/user-attachments/assets/6c43c88d-d128-4eea-bd1f-0fbd14f73ed7" />
