# WG4-WG1 Uncertainty Training

This is the code and data for a course on uncertainty, calibration and traceability held on Romania at CETAL in fall 2019.


The structure and content is as follows:

- Schedule and Presentations: Includes the course schedule and the presentation that are explaining the tasks that are then implemented in the Matlab code.
- ExampleData: Data used by the provided Matlab code
- Matlab Code: Example Matlab code, covering the example and exercises of this training school

Matlab function details, data and relevant presentations follow below.


![Creating L Realisations Diagram](/_img/Creating_L_Realisations_Diagram.png)



## Read the spectrometer data and determine statistics

**Presentations:**
| File name                                                   | Comment                                                                | 
| :---------------------------------------------------------- | :--------------------------------------------------------------------- | 
| Read the spectrometer data and determine statistics.pdf


**Data files:**
| File name                                                   | Comment                                                                | 
| :---------------------------------------------------------- | :--------------------------------------------------------------------- | 
| 10000fL_15ms.xlsx
| 1000fL_15ms.xlsx
| 100fL_15ms.xlsx
| 5fL_15ms.xlsx
| Dark15ms.xlsx

**Matlab code:**

| File name                                                   | Comment                                                                | 
| :---------------------------------------------------------- | :--------------------------------------------------------------------- | 
| ReadSpectrometerDataMeanStd.m								| note: the pathnames need adjusting to your local machine!	|



## Radiometric Calibration Coefficient and Uncertainty Propagation via Monte Carlo

**Presentations:**
| File name                                                   | Comment                                                                | 
| :---------------------------------------------------------- | :--------------------------------------------------------------------- | 
| Intro to Monte Carlo and Application to RAD CAL.pdf
| Radiometric Calibration Coefficient Determination.pdf




**Data files:** (see also last slide of presentation): 
| File name                                                   | Comment                                                                | 
| :---------------------------------------------------------- | :--------------------------------------------------------------------- | 
| L_Sphere.mat												| Input file for the code: radiance levels of the integrating sphere
| STD_DN.mat												| Input file for the code: noise of the DN measurements, given as standard deviation
| DN_L_CAL.mat												| Input file for the code: DN levels of the instrument as exposed to integrating sphere at different light levels
| uL.mat												    | Input file for the code: uncertainty of the radiance calibration of the sphere (given at confidence interval of k=2)
| u_rad_coeffs.mat											| Output of Monte Carlo run: uncertainties of gain, offset and uncertainty due to gain and offset correlation. This file is eventually generated by the code itself.



**Matlab code:**

| File name                                                   | Comment                                                                | 
| :---------------------------------------------------------- | :--------------------------------------------------------------------- | 
| MC_Introduction.m											| Code to produce plots shown in the intro to Monte Carlo presentation
| RAD_CAL_with_Linear_Fit_and_uncertainty_estimation_with_Monte_Carlo.m | Main script. Note: set the run_sim = true on line 408 to run MC (This can take very long! You may want initially to choose a lower number of realisations by e.g. setting N = 10 on line 282). Set to false once you have them calculated.
| print_jpeg.m print_pdf.m		| Functions to export figure to JPEG or PDF
| progressbar.m, gui_active.m		| Functions for progress bar used to show progress during monte carlo run
| get_realisations_gauss_dist.m	| Function to create realisations



## Uncertainty propagtion using radiative transfer models

**Presentations:**
| File name                                                   | Comment                                                                | 
| :---------------------------------------------------------- | :--------------------------------------------------------------------- | 
| RTM_and_uncertainty propagation_Session_1_RTM.pdf
| RTM_and_uncertainty propagation_Session_2_RTM.pdf
| RTM_and_uncertainty propagation_Ex_1.pdf
| RTM_and_uncertainty propagation_Ex_2.pdf


**Data files:**
| File name                                                   | Comment                                                                | 
| :---------------------------------------------------------- | :--------------------------------------------------------------------- | 
| Ex1_TableLeafParam.csv
| Ex2_BOAirradiance.csv
| Ex2_TableLAI.csv
| Ex2_TableLeafParam.csv
| Soil.csv

**Matlab code:**

| File name                                                   | Comment                                                                | 
| :---------------------------------------------------------- | :--------------------------------------------------------------------- | 
| RTM_and_uncertainty propagation_Ex_1_solved.m								| note: you need to download PROSPECT-D model separately	|
| normrnd_truncated.m								| 	|
| RTM_and_uncertainty propagation_Ex_2_solved.m								| note: you need to download PROSPECT-D model separately.	|


