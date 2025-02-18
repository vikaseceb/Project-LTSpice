![Screenshot 2025-02-13 203010](https://github.com/user-attachments/assets/2ff6c3b5-9c1c-425d-8007-2fd231c6eb21)# Experiment-1

## Aim:
To perform DC analysis, Transient analysis, and AC analysis of a Common Source (CS) amplifier circuit and extract various parameters using LTSpice.


## Introduction to the Topic:

A MOSFET (Metal-Oxide-Semiconductor Field-Effect Transistor) is a crucial component in modern electronics due to its compact design, low power consumption, and compatibility with VLSI technology.


In saturation mode, an NMOS transistor operates under the conditions:
- *Vgs > Vth* (Gate-to-Source Voltage greater than Threshold Voltage)
- *Vds ≥ Vov* (Drain-to-Source Voltage greater than Overdrive Voltage)

In a CS amplifier, the output will give 180-degree phase shift with respect to input 

the current equation in saturation mode is given by
*Id = (1/2) kn Vov²*, where:
- *Vov = Vgs - Vth*


The voltage gain is given by:

*Av = -gm Rd*
or
*Av = Vout/Vin*


A *diode-connected MOSFET* is always in saturation and acts as a *constant current source*, making it useful for amplifier circuits.

- *Drain current equation:*
  *Id = (1/2) kn Vov², where **Vov = Vgs - Vth*.

- The amplifier gain follows *Av = -gm Rd*.



## Task 1: CS amplifier with resistive load

## Components Required:
- NMOS (nmos4)
- Resistor (1kΩ)
- Voltage sources (1.8V, 0.9V)


## Circuit diagram:
![Screenshot 2025-02-18 162811](https://github.com/user-attachments/assets/c0a7148a-b70f-4948-9985-25901e4996cb)


## Procedure:

1. *Create a New Project*

2. *Set Up the values for MOSFET*
   - Configure the *NMOS transistor (CMOSN)* with:
     - Length: *480nm*
     - Width: *466nm*
  
3. *Perform DC Analysis*
   - Connect all circuit components properly.
   - Apply:
     - *Vdd = 1.8V*
     - *Vin = 0.9V*
   - Run *DC analysis* to obtain:
     - *Vout*
     - *Id*

4. *Run Transient Analysis*
   - Apply a *sine wave input*:
     - *Vin = 0.9V*
     - *Amplitude = 50mV*
     - *Frequency = 1kHz*
   - Run *transient analysis*
   - 
5. *Run AC Analysis*
   - Include all required library files.
   - Run *AC analysis* with:
     -Start and end frequency: *0.1Hz to 1THz*



## Results:
### DC Analysis:
- *DC Operating Point:*
  - *Id =27.7uA*
  - *Vout =1.77223V*
  - *Width = 466nm*
  - *length = 480nm*
  - *Q-Point:* (1,77223V, 27.7uA)

![Screenshot 2025-02-13 210350](https://github.com/user-attachments/assets/11c000b4-51fd-46f9-bc91-209c563d8661)


### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.77223V* at *Width = 466nm* and *length = 480nm*.

![Screenshot 2025-02-13 202231](https://github.com/user-attachments/assets/068a3a5a-7f4a-41fe-80c8-1da6114555ff)



### AC Analysis:

![Screenshot 2025-02-13 203010](https://github.com/user-attachments/assets/592b67e9-63d9-450c-bac7-5e511be68c82)




## Inference:
1. The MOSFET's *current (Id) is directly proportional to its width*, affecting overall circuit performance.
2. Operating in saturation region.
3. Transient analysis helps in evaluating the circuit’s response to time-varying signals, crucial for high-speed applications.
4. AC analysis aids in designing amplifiers with desired gain and understanding frequency behavior.
5. The overall analysis ensures proper design, optimization, and stability of the amplifier circuit.

   

## Task 2: CS Amplifier with Diode-Connected MOSFET

## Components Required:
- NMOS (nmos4) and PMOS(pmos4)
- Voltage sources (1.8V, 0.9V)
- Bias DC source (-2.5V)

## Circuit diagram:
![Screenshot 2025-02-18 154637](https://github.com/user-attachments/assets/c10110a9-f588-48b9-80ce-a4e30445370c)



### Procedure:
1. Set the PMOS transistor (CMOSP) with a length of *180nm* and width of *0.61μm*.

2. *DC Analysis:*
   - Apply *Vdd = 1.8V* , *Vin = 0.9V* 
   - As the MOSFET should be in saturation region,
     Here Vb is connected to gate , so for us both the mosfet should be in saturation so for that Vgs>Vt 
    |Vg-Vs|>|Vt|
    here Vg is unknown so I calculated Vg ie Vg =Vb
    Vb=-2V
   - Run DC analysis to determine *Vout* and *Id*.
  ![Screenshot 2025-02-18 153133](https://github.com/user-attachments/assets/9d6a7135-e73e-41db-a992-a149f219cbb4)


3. *Transient Analysis:*
   - Apply a sine wave input and observe the response.
   - ![Screenshot 2025-02-18 153440](https://github.com/user-attachments/assets/fd1e8825-cb4a-40e4-93ca-c92f955297fe)


4. *AC Analysis:*
   - Run AC analysis to measure gain and frequency response.
   - 
![Screenshot 2025-02-18 153641](https://github.com/user-attachments/assets/89a78360-9ebb-4f29-8a99-f117db9c530d)


## Results:


### DC Analysis:
- *DC Operating Point:*
  - *Id1 =27.7uA*
  - *Id2 =27.7uA*
  - *Vout =1.79981V*
  - *Width = 690nm* (NMOS)
  - *length = 700nm* (NMOS)
  -  *Width = 360Um* (PMOS)
  - *length = 302nm* (PMOS)
  - *Q-Point:* (1,79981V, 27.7uA)


![Image](https://github.com/user-attachments/assets/076773ae-cb10-45f6-bed1-9193ff1f8564)


### Transient Analysis:
- The output shows a *180-degree phase shift* between input and output.
- *Vout = 1.79981V* 


![Image](https://github.com/user-attachments/assets/0645a560-4518-4b8d-810f-b852f6cfc73f)



### AC Analysis:

![Image](https://github.com/user-attachments/assets/efdabf4f-7389-4f89-a955-7690d7be3f20)

## Gain:

*Av = -gm Rd*
*gm = 1/lamda*Id*

Practical result: *Gain = 36.7361dB* at 1KHz frequency.

![Image](https://github.com/user-attachments/assets/b8175d28-f620-4588-9f58-48f3623757c7)

## Inference

1. The MOSFET's **drain current (Id) is directly proportional to its width (W)**, influencing circuit performance and power consumption.  
2. The MOSFET operates in the **saturation region** for amplification, ensuring a stable output.  
3. **Transient analysis** evaluates the circuit’s response to time-varying signals, which is crucial for high-speed applications and switching performance.  
4. **AC analysis** helps in designing amplifiers by determining gain, bandwidth, and frequency response.  
5. A comprehensive analysis ensures **optimal design, performance, and stability** of the amplifier circuit.
