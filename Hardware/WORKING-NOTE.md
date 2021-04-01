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






