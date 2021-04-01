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


