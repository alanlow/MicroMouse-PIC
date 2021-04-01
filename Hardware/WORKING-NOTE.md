# This is the working note for design required calculation or estimation


### ADP1612
The robot will be powered with  single cell Li-Ion 16850 which as a typical 3.7V

Vin = 3.7V
Vout = 5V
Current = 1.2A

#### Setting the output Voltage

   Vout = 1.235 x ( 1 + R1//R2 )

   Choose R2 = 10k

   R1 = R2 x ( Vout - 1.235) / 1.235
   R1 = 30.485k (choose closer value) 30.5k

#### Verification of Vout with selected value

   Vout = 1.235 x ( 1 + (30.5k/10k))
   Vout = 5V

#### Inductor Selection

   Let fsw = 1.3MHz
 
   D = (Vout - Vin)/Vout
   D = 0.26

   ton = D/fsw
   ton = 0.26/1.3M
   ton = 0.2uS

   let L 4.7uH
   dIl = (Vin x ton) / L
   dIl = (3.7 x 0.2u) / 4.7u
   dIl = 157mA

#### Cout selection
   let dVout is 20mV
   let Cin is 10uF

   Cout ≥ (Iout x ( Vout - Vin )) / ( fsw x Vout x dVout )
   Cout ≥ (1.2 x ( 5 - 3.7 )) / ( 1.3M x 5 x 20m )
   Cout ≥ 12uF

   Select 10uF + 1uF + 1uF


#### Diode Selection

   D ≥ ( Vout - Vin(max) ) / Vout
   D ≥ ( 5 - 4.2 ) / 5
   D ≥ 0.16

   Recommended Diode PN MBRA340T3G


#### Loop compensation

   Select Rcomp = 12k
   fc = ( Rcomp x Vin ) / ( 4746 x 12u x Vout2)
   fc = ( 12k x 3.7 ) / (4746 x 12u x 5 x 5 )
   fc = 31.184 kHz

   Ccomp = 2 / ( π x fc x Rcomp )
   Ccomp = 1.7nF



