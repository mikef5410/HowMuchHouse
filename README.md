# HowMuchHouse
Calculate maximum affordable mortgage with circuit simulator

## How much house can an  RF/uWave EE afford?

My son's starting his career in Northern California and we were wrestling with basic questions like how much house can he afford.  The problem involves solving simultaneous non-linear equations; especially when you start to consider PMI (private mortgage insurance) which is usually required when you're under 20% down.  Around here, to get to 20% down you're looking at over $120K.

Our first attempts with Matlab were frustrating, but then we had a flash of inspiration ... circut simulators are really good at systems of nonlinear equations ... plus you can kind of see what's going on, especially with parameter sweeps at your disposal.  So in this example, I let 1A=$1, and use current sources to represent income and dollar outflow.  Account for fixed costs and by KCL, the mortgage payment is whatever's left. That's the max house you can afford.  This simulation is with Qucs, a handy and powerful simulator, but the _real_ one we did is done with ADS ... complete with tax tables, etc. I'll upload the .zap file soon.

The real point of this exercise is to make the point that circuit simulators are useful tools for solving all sorts of problems, not just circuits.

At the top of the circuit, there are current sources for Paycheck and Renter income, then fixed current sources for school loan payments, and operating/living costs. The Trick is the equation defined device to calculate PMI payments and shut them off if the down is over 20% of mortgage. I do this with tanh(x), a common trick to turn on/off a value in a nice smooth differentiable way ... helps convergence. 

Enjoy!
-Mike & Andy
