# Lucas-Kanade Tracking  

Assignment 2 for Spring 2023 16720A Computer Vision at Carnegie Mellon University

## Lucas-Kanade Template Tracking  

Implements the Lucas-Kanade(LK) algorithm for tracking a specified object through
successive frames. The naive LK algorithm assumes a pure translation warp of the
template object. One drawback of naively updating the template at each frame is
that the template eventually drifts due to error accumulation and ends up tracking
a different object in later frames compared to earlier frames.  

Tracking the car in traffic  
![](/results/car-in-traffic/without-template-correction/sol_1.3_carseq_1.png)
![](/results/car-in-traffic/without-template-correction/sol_1.3_carseq_80.png)
![](/results/car-in-traffic/without-template-correction/sol_1.3_carseq_160.png)
![](/results/car-in-traffic/without-template-correction/sol_1.3_carseq_280.png)
![](/results/car-in-traffic/without-template-correction/sol_1.3_carseq_410.png)  

Tracking the girl on the scooter  
![](/results/girl-on-scooter/without-template-correction/sol_1.3_girlseq_1.png)
![](/results/girl-on-scooter/without-template-correction/sol_1.3_girlseq_15.png)
![](/results/girl-on-scooter/without-template-correction/sol_1.3_girlseq_35.png)
![](/results/girl-on-scooter/without-template-correction/sol_1.3_girlseq_65.png)
![](/results/girl-on-scooter/without-template-correction/sol_1.3_girlseq_85.png)  

---  

## Lucas-Kanade Template Tracking with Drift Correction  

Improves the naive LK template tracking with drift correction. At every step,
the proposed template from the LK algorithm is realigned using the initial
template with the proposed template serving as the starting point for realignment.
The algorithm for drift correction is described in the following paper:  

Iain Matthews, Takahiro Ishikawa, and Simon Baker. The template update problem. In Proceedings of
British Machine Vision Conference (BMVC ’03), September 2003.  

Tracking the car in traffic with drift correction  
![](/results/car-in-traffic/with-template-correction/sol_1.4_carseq_1.png)
![](/results/car-in-traffic/with-template-correction/sol_1.4_carseq_80.png)
![](/results/car-in-traffic/with-template-correction/sol_1.4_carseq_160.png)
![](/results/car-in-traffic/with-template-correction/sol_1.4_carseq_280.png)
![](/results/car-in-traffic/with-template-correction/sol_1.4_carseq_410.png)  

Tracking the girl on the scooter with drift correction  
![](/results/girl-on-scooter/with-template-correction/sol_1.4_girlseq_1.png)
![](/results/girl-on-scooter/with-template-correction/sol_1.4_girlseq_15.png)
![](/results/girl-on-scooter/with-template-correction/sol_1.4_girlseq_35.png)
![](/results/girl-on-scooter/with-template-correction/sol_1.4_girlseq_65.png)
![](/results/girl-on-scooter/with-template-correction/sol_1.4_girlseq_85.png)  

---  

## Affine Motion Tracker  

Implements the LK algorithm for motion tracking of multiple objects through 
successive frames. This version of the LK algorithm assumes an affine warp. 
Motion estimation is done through dominant motion estimation (affine LK) and
dominant motion subtraction to generate a mask of pixel locations of moving
objects.   

Tracking the ants  
![](/results/ants/sol_3.2_antseq_30.png)
![](/results/ants/sol_3.2_antseq_60.png)
![](/results/ants/sol_3.2_antseq_90.png)
![](/results/ants/sol_3.2_antseq_120.png)  

Tracking the planes  
![](/results/aerial/sol_3.2_aerialseq_30.png)
![](/results/aerial/sol_3.2_aerialseq_60.png)
![](/results/aerial/sol_3.2_aerialseq_90.png)
![](/results/aerial/sol_3.2_aerialseq_120.png)  
