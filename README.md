# BOOTCAMP - COIMBATORE
## DAY 1 - INTRODUCTION

On  day one we just had an introductory session on various branches of bi0s hardware like Reversing/Firmware, automotive security, SCADA/ICS, Embedded. Also we had a discussion on how to give pull requests on gitlab also some other commands for gitlabs with the help of this [blog](https://web.archive.org/web/20161121145226/http://rypress.com:80/tutorials/git/index).


## DAY 2 - Reversing/Firmware

On day two we had an interesting session on assembly language and Firmware.Basically assembly language is just a programing language which is older than c and comparatively easier for the computer or processor to understand. These language does not require compiler which converts human readable file into a machine readable file. Instead of variables registers are used. They can store both values and the address of the value. These resiters can be either general purpose,special purpose,instruction pointers,instruction pointers and status flags. Then we discussed about GDB or GNU debugger which is used to reverse an executable file into a human readable program file (mostly assembly language in GDB) which is not the perfect code but just an assumption of how the the file executes and another version peda which just pyhton exploit devolopment assistance for GDB which has some really useful commands for decompiling and understanding the code. The execution of an assembly code is based on stack memory i.e. each fuction creates its own memory stack on top of the main stack which in turn is destroyed itself after the function is completely executed. Furthermore we tried to reverse an exe file. Some challeges were given that are supposed to be reversed.


## DAY 3 - AUTOMOTIVE SECURITY

On day 3 we discussed about automotive security, CAN protocol was on of the crucial protocols that is followed by the microcontrollers or ECUs connected in bus topology such that no host computer is required to communicate with each other. These ECUs or electronic control units are used to control automotive parts like the ABS, stearing, windows etc.these Protocols runs over two wires- CAN-H and CAN-L. This protocol transfers data in an format.
1. indentifier extention: this bit is always zero

2. data frame: this consists of the data which needs to be transferred.

3. Error frame: this frame will be written to specify an error.

4. Arbitration ID: this provides a unique id for each node in the bus.

5. Data length code: represents number of bytes of data.

Then we discussed about ICsim and did some challeges on ICsim like to analyse how the bits change with speed, opening door etc. Finaally challenges were given to do in ICsim.

## DAY 4 - SCADA/ICS

On day 4 we discussed about ICS or industrial control system and SCADA or supervisory control and data acqusition which is used in industries to manage large arrays of machine, with a certain purpose or process, using just a single computer. These machines are connected in a master-slave relation.PLCs and RTUs are acts as the master which could send and request to recieve info to the slaves and sensors etc acts as the slave which does work according the messege from the master to either send  any information or do a perticular function. These messege has certain format or protocol which helps the slaves to understand wheather the messege is for it or not.

## DAY 5 -EMBEDDED SECURITY

Could'nt join on day 5 but read about general hardware  communication protocols like UART, SPI, I2C (I square C) with the help of [wiki bi0s](https://wiki.bi0s.in/hardware/basic-electronics/protocols/). 

 ### UART

 UART or universal asynchronous reciver/transmitter is a hardware communication protocol that uses asynchronous serial communication with configurable speed. Asynchronous means there is no clock signal to sychronize the output bits from transmitting device to receiving device. Two UARTs directly communicate with each other with 2 signals Transmitter(Tx) and receiver(Rx).For communication between 2 UARTs the baut rate should be the same. UART data transmission in done in high voltage. Whenever there is a high to low voltage transition the device starts reading the data frame at the frequency of the baud rate. Data frame contains the actual data being transferred. it can be 5 bits to 8 bits. The data is sent with least significant bit first.
 [source](https://www.analog.com/en/analog-dialogue/articles/uart-a-hardware-communication-protocol.html#:~:text=By%20definition%2C%20UART%20is%20a,going%20to%20the%20receiving%20end.)

 ### SPI

 SPI or serial peripheral interface is a sychronous serial communication interface for short distance communication. SPI device communicate using master-slave architecture with one master and one or more slaves. SPIis a synchronous protocol hence has a clock pin to sync up the data being sent. The data from the master comes through MOSI "master out/slave in" nad the clock s set according the line through whicht the data is transferred. Pins in a SPI device are MOSI, MISO (master in/slave out), SCLK(serial clock), SS(slave select).
 [source](https://wiki.bi0s.in/hardware/basic-electronics/protocols/)

 ### I2C

 I2C or inter-integrated circuit is another sychronous communication protocol used for short distance communication and it supports more than one master and slaves. Each slave can be connected to multiple masters and each master can be connected to multiple slaves. HTey have 2 pins SDA and SCL. SDA or serial data is to send and receive data between master and slave. SCL or serial clock is the line which caries the clock.
 [source](https://www.circuitbasics.com/basics-of-the-i2c-communication-protocol/)

## DAY 6 - PCB DESIGNING

On day 6 we discussed about PCB designing with the help of a platform called [KiCAD](https://www.kicad.org/download/). KiCAD is used for electronic design automation. PCB can be either single layered or double layered i.e. either one copper sheet is used to connect the components or 2 copper sheets are used respectively. Did one PCB with the help of kiran chetan. Challeges were given to be solved.

## DAY 7 - WIRELESS

day 7 was wireless. Couldnt attend the session but read about wireless from [bi0s wiki](https://wiki.bi0s.in/hardware/wireless/introduction/). wireless communication, as the name suggest, to communicate without any wire. NFC, bluetooth, Radio frequency,  Industrially Controlled Wireless Transmission (ZigBee), WLAN or WiFi, cellular network, GPS, SATCOM etc. THese communication have its own vulnerabilities and can be attacked through:
 1. wireless signal replay: the wireless devices does not have a replay security hence a hacker can easily clone or replay a perticular signal which was sniffed using special device to do a perticular function.

 2. wireless signal deception: the sniffer could decipeher the sniffed signal to understand the packet format to further send a packet to do a certain function,

 3. wireless signal hijacking and DoS attack: the users network is blocked pulls the user from a legitimate network to a simulated network and attack the network.

Then challenges were given but have to try doing it.

## DAY 8- SIDE CHANNEL ATTACK

Side channel attack was an interesting topic that we discussed on day 8. It si an attack based on the fundamental factors like time power consumption etc to decipher the file or to access the file. These attack can be based on some general classes like timing attack, Power monitoring attack, voltage fluctuation attack etc. Some examples on how to do it was shown ut no challeges were assigned.

## DAY 9- LAST DAY OF BOOTCAMP

On the last day we had a session on our falcon badge. It is embedded with an esp module. We were able to play 2-3 game using the LED display and aslo had some challeges and easter egg in the badge. The making of such badge was explained and also got a sneak peek on t=our new badge for InCTF 2022. Also we ended our 

 ## CHALLENGES

  1. ### Reversing/Firmware challenge
     The challenge was to decompile  the executable file given and get output "YOU WIN" but was not able to        get the output for all the four files but will try to find out in 2-3 days.
   
  2. ### Automotive security
      1. CHALLENGE-1 
        to sniff out packets I used  can sniffer -c vcan0 to get the packet transferred in ICsim. To dump the         packet transfer log just use `candump -l vcan0`. Now to replay the captured packet use `canplayer -I         dumped_file_name.log`.
      2. CHALLENGE-2
        To go over the limit in speedometer in ICsim, firtly analyse the log file or  sniffed bits to find           which packet changes for accelaration and file the max value. Now just send a packet higher than the         max to go over 100mph. But to make it constant use a while loop in the terminal. In my case `cansend         vcan0 244#0000004196` will go over 100mph but to make it connstant  use the following command:
        
         ```function repeat(){
         for ((i=0;i<$1;i++));
         do eval ${*:2}done
         }
       
       now give the command `repeat 1000 echo cansend vcan0 244#0000004196` for the cansend command to repeat 1000 times so that the speed is constant.
    
   3. ### PCB DESIGNING
       
       The task was to make a PCB of a simple circuit with atleast 1 via and a custom silkscreen behind the PCB. 

       => [challenge.kicad_pcb](https://github.com/Karthik-G-21-06/bootcamp_2022/blob/main/challege.kicad_pcb)

       => [challenge.kicad_sch](https://github.com/Karthik-G-21-06/bootcamp_2022/blob/main/challege.kicad_sch)

   4. ### SCADA
      
      The task was to just follow the instruction given in the [blog](https://www.hackers-arise.com/post/2016/10/31/SCADA-Hacking-Modbus-MasterSlave-Simulation) to make a  small master-slave system using qmodmaster and modpal.
## SUMMARY
 
 I was able to know about a lot of stuff in bi0s hardware. Most of them were interesting but found reversing to be really interesting even though its really tough to understand. Also was able to bond with our senior and also enjoyed the stay at coimbatore even though had some issue. Overall I had a really great time there and will be looking into reversing/firmware. Thanks Bi0s team for organising this really informative and fun bootcamp.











