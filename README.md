# SCADA system development for curing press

I was assigned in my internship to develop the SCADA system to overcome the challenges, provide a good interface to the operator, increase efficiency and improve the quality. This specialized SCADA system was implemented to modernize the L05 curing presses at CEAT Kelani Radial (private) Limited. It introduces a range of innovative enhancements compared to its predecessor, including a revamped recipe loader with expanded memory capacity, upgraded counter accuracy categorized into shifts, and automated daily data storage in the database.


The communication method of this system can be changed easily by using the [MX Component](https://www.mitsubishielectric.com/fa/products/cnt/plceng/smerit/mx_component/index.html) tool. That can be configured to any communication interface and that data can be read from the [visual studio](https://visualstudio.microsoft.com/)  application. 


## The system considers the following installation requirements:
#### 1.	This software can run on the following operating systems:
  -	Microsoft Windows 10 All editions
  -	Microsoft Windows 8 All editions
  -	Microsoft Windows 7 All editions with Network framework 3.5 or above.
#### 2.	 Hardware requirements
-	Any type of computer (IPC / desktop)
-	Monitor
-	USB mini Male to USB male Cable or Serial Cable
#### 3.	Required Software
-	Install MX component 4.16 or above update
-	Virtual keyboard software
#### 4.	Required drivers
-	Install USB drivers

The installation procedure involves setting up six executable files. If you've chosen to modify the installation path, update the corresponding link in the configuration file. (Right-click to copy its location and store the corresponding link in the configuration file). Similarly, this process applies to all executable files. Upon completion, launch the Chart installed File to initiate the system.

## Configure MX Component Software:

This software serves as the communication interface that facilitates interaction between the SCADA and PLC systems. The advantage of this software we can configure any communication method. Below Figure 01 shows the Communication setup utility of the MX component. <br>
<br>
<img src="Document/Images/Communication setup of MX component.png" width="700" >
<br>
<br>

In the subsequent step, the appropriate CPU type is selected, as depicted in Figure 02. With this selection made, the setup process can be continued. This method enables us to establish connections between the SCADA system and various CPU modules. <br>
<br>
<img src="Document/Images/Selecting CPU module.png" width="700" >
<br>
<br>

## Startup Interface

The SCADA system can be launched on Windows by simply clicking the desktop icon. An example startup screen is provided to illustrate this process. This screen, depicted in Figure 03, showcases all the relevant parameters associated with tire curing.<br>
<br>
<center>
 <img src="Document/Images/Starting monitor surface.png" width="1000" > 
</center>

<br>
<br>



#### This interface shows,
-	24h Polar Chart with 5 Series.
-	Real-time Trend Chart with 5 axes.
-	Internal Pressure with analog gauge and digital Display.
-	Internal Temperature with analog gauge and digital Display.
-	Pattern Temperature right side with analog gauge and digital Display.
-	Pattern Temperature left side with analog gauge and digital Display.
-	Jacket Temperature with analog gauge and digital Display.
-	Real-Time Alarm View
-	Production Counter (Shift wise &Total Production of the Day).
-	Remaining Time when green tyre curing.
-	Step Number when green tyre curing.
<br>

This system enhances the precision of data memory registers on the PLC. The counter increments within the last 10 seconds of each curing cycle. At the conclusion of the 24-hour over-production shift, both the shift-wise counters and the total counter reset automatically. And simultaneously polar chart and real-time will reset automatically. Normally that reset time is 6.00 am.
<br>

#### Machine Operator can use this menu bar (ComboBox) for go to,
-	Main view Interface
-	Recipe Loader Interface
-	Input / Output Interface
-	Parameter Interface
-	Main Database

This is the easiest way to go to other pages. Otherwise, you can open that installed exe files individually by opening a particular exe file. 



## Mainview Interface

The main view interface of the SCADA is shown in below figure 04.<br>
<br>
<img src="Document/Images/Main view interface.png" width="1000" >
<br>
<br>

In this Main view real-time displays,
-	Valve Status (on/off) 
-	Step number
-	Step time
-	Total cure time
-	Remaining Cycle time
-	Bladder Count (LHS/RHS) with reset Buttons
-	Password Logging access for Critical changings.
-	Internal Pressure 
-	Internal Temperature
-	Step Jumping Tool
-	Valve Adjustment of jacket Control valve & Pattern Control Valve
-	Jacket temperature display on both sides.
-	Pattern Temperature display of both sides.

The very important tool of this view is the step jumping tool. When tyre curing some Malfunction has occurred we have to step jump immediately to minimize the damage. This tool has a numerical up-down button and we can select the number of steps we wanted to jump. Before using this tool, the operator should log into the system by entering the password.



## Recipe loader


The machine recipe loader in SCADA is shown in Figure 05.<br>
<br>
<img src="Document/Images/Recipe loader.png" width="1000" >
<br>
<br>

In this setup, you can set the time for each step in the "time" column. Each valve's name is displayed on its respective button for easy identification. To open a valve, simply press the corresponding button, and check the checkbox in the corresponding row (step) and column (valve). If you haven't entered your password before accessing this screen, the "Write" button will appear in red (enabled), and you won't be able to make any changes on this screen. In other words, to configure curing techniques here, you must input your correct password by clicking the "Login" button. You can do this by pressing "Enter" on the alphanumeric virtual keyboard and then selecting "Recipe Setting" to switch to the curing recipe setup screen. If you want to check the current status of valves, press the "Read" button. It will display which valves are activated (red) and which ones are deactivated (green).

The recipe loader features individual buttons for direct recipe loading. To use this method, the operator must first log in by entering the correct password. Once logged in, the buttons become active. This direct approach simplifies writing a recipe, and by using the "Read" button, you can view the loaded recipe, valve statuses, and step times, as depicted in Figure 06.<br>
<br>
<img src="Document/Images/Saved recipe load interface.png" width="450" >
<br>
<br>

The recipe loader features a "Recipe Configuration" button for setting the recipe time and name. You can modify these settings using the configuration text file, as displayed in Figure 07. This text file is located within the database folder and can be accessed through the menu bar.
<br>
<br>
<img src="Document/Images/Configuration text file.png" width="650" >
<br>
<br>
Another function of this recipe loader is the ability to skip to specific recipe steps. To do this, you select the desired step number on the numerical input window and then press the "Jump" button (Figure 08). However, before initiating step jumping, the operator should log in by entering the correct password, at which point the buttons become enabled for use.<br>
<br>
<img src="Document/Images/Step jumping tool.png" width="450" >
<br>

## Parameter Settings

Set parameters interface is shown in below Figure 09.<br>
<br>
<img src="Document/Images/Parameter interface.png" width="1000" >
<br>
<br>

This page provides access to all machine parameters and their predefined values. Typically, each parameter is set to "read-only." However, if an operator needs to make changes, they must log in by entering the password, after which the "save" button becomes active.

The parameters that can be monitored and edited using this interface include:

- Encoder positioning settings.
- Pattern PID control settings.
- Jacket PID control settings.
- Machine delay times.
- Shaping settings.
- Analog display, which operates when shaping involves 3 steps.

To set PID parameters on this screen, you must input your password, following the same method used for configuring curing recipe settings. Once you've ensured all settings are correct, please press the "save" button to save your modifications. These settings will then be downloaded to the PLC. After saving settings, you can read PLC memory by using the "read" button. However, before reading, it's essential to log in using the correct password.


## I/O points monitoring

Below, you'll find an example illustrating the real-time monitoring of I/O points. In this representation, red indicates an "ON" status, while green indicates "OFF." This page includes all the input and output points from the PLC unit, and it establishes direct and real-time communication with the PLC.Both the input (Figure 10) and output (Figure 11) statuses are updated and operational in real-time online, providing a comprehensive view of the PLC's performance.<br>
<br>
<img src="Document/Images/PLC inputs.png" width="1000" >
<br>

<br>
<img src="Document/Images/PLC outputs.png" width="1000" >
<br>
<br>

## Main Database

Figure 12 displays all the databases, encompassing Alarm, Cycle Charts, Polar Charts, Production reports, and Trend Charts. If you wish to access historical data, you can simply open the corresponding folder within the database.<br>
<br>
<img src="Document/Images/Main database.png" width="1000" >
<br>
<br>
