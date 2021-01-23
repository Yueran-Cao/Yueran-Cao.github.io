---
layout: post
title:  "Step by Step Tutorial"
categories: jekyll update
---
Step 1.	Download the VERTEX toolbox for MATLAB from <http://vertexsimulator.org/> ( [figure1][figure1-docs] ). Follow the instructions on the website to download the VERTEX toolbox and open it in MATLAB. Make sure to add the whole file and its contents to the path ( [figure2][figure2-docs] ), this can be done by right-clicking on “Vertex_git-master” on the left then selecting “add to path” then clicking on “selected folders and sub folders”. 

Step 2.	Install the “Partial Differential Equations” toolbox required to run the simulations in MATLAB. 

Step 3.	In the “Current Folder” part of MATLAB open “Vertex_git-master”, then look for “catVisModel” ( [figure3][figure3-docs] ). Open this and double-click “cvc_model_run.m” ( [figure4][figure4-docs] ) to open it. 

Step 4.	Comment out line 19 of the code (load('zerostimfield_cvc.mat');) and comment in line 18 (cvc_field_stimulation;) ( [figure5][figure5-docs] ).

Step 5.	Parameters within “cvc_tissue.m” can be altered, such as the dimensions of the tissue sample as well as the neuron density, as seen in ( [figure6][figure6-docs] ). 

Step 6.	Between lines 4-14 of the code, make sure that one ‘cvc_neurons…” and one “cvc_connectivity…” are commented into the code by removing the “%” from the beginning of the line, and comment out the unwanted lines by adding “%” to the start of the line. Preferably if, for example, “cvc_neurons_beta” is selected, then the corresponding connectivity line should be commented in, which in this case would be “cvc_connectivity_beta”. (see [figure7][figure7-docs] for an example)
Note: if other types of waves are required (e.g. theta) then the “cvc_neurons” code can be changed to accommodate for this, however, this is beyond the scope of this tutorial. 

Step 7.	The parameter within “cvc_simulation” on line 8 “SS.simulationTime = 100;” ( [figure8][figure8-docs] ) can be changed to alter the amount of time the simulation will run for in milliseconds. It is strongly recommended not to change the time step (“SS.timeStep” on line 3 of the code) as this can alter the function of the whole program. 
Note: 100ms can be used to test the code to see if it is working, however, it is recommended to use at least 200ms recording time, as the simulation displays some quite random activity in the first 100ms. Furthermore, increasing the time will lead to longer processing times, which should be kept in mind if longer simulations are to be run. 

Step 8.	The value on “TP.StimulationOn” can be adjusted to decide when the stimulation in the simulation begins ( [figure9][figure9-docs] ). This value is in milliseconds (ms). 

Step 9.	The text within the quotation marks ( [figure10][figure10-docs] ) can be changed according to user preference to choose where the data will be saved. 

Step 10.On line 30 ( [figure11][figure11-docs] )the parameter “SS.parallelSim” can be changed to true by commenting out false and commenting in true. This can allow for faster simulations by employing multiple cores in your machine to run multiple parallel simulations. However, this is only recommended if the simulation is expected to take a long time to run, as it takes some time to initialise the use of multiple cores. 

Step 11.To produce a graph of the results (such as the one seen in [figure12][figure12-docs] and in [figure1][figure1-docs] (B)), comment in the code on lines 46-52 ( [figure13][figure13-docs] ). The graph produced can be manipulated within MATLAB to zoom in/out and also rotated since it is a 3D graph. Each different shape on the graph represents a different type of neuron. 

Step 12.Finally run “cvc_model_run.m” to get the results. Simulation time will vary depending on the parameters selected, and it is recommended to use a time of at least 200ms to get more accurate results. 

[figure1-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig1.jpg/
[figure2-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig2.png/
[figure3-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig3.png/
[figure4-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig4.png/
[figure5-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig5.png/
[figure6-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig6.png/
[figure7-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig7.png/
[figure8-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig8.png/
[figure9-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig9.png/
[figure10-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig10.png
[figure11-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig11.png
[figure12-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig12.png
[figure13-docs]: https://github.com/Yueran-Cao/simulated_stimulation_on_VERTEX/blob/main/fig13.png
Reference:
[1] Hutchings F, Thornton C, Zhang C, Wang Y, Kaiser M. Predicting the Impact of Electric Field Stimulation in a Detailed Computational Model of Cortical Tissue. arXiv preprint arXiv:2001.10414. 2020 Jan 28.

