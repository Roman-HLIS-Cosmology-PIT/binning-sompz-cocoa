# Optimal Tomographic Bins for Cosmology and the Interplay with CPIP-DC2
@ this yamls folder:

dv_generator_photoz_realizations_{nbins}bins_equalnum.yaml, nbins = 4,...,10
Procedure to compute the fiducial 3x2pt data vector (DV): 
    1. Run calculate_mask.py for nbins (the number of rows equals the 3x2pt length)  
    2. Use any arbitrary file with a 3x2pt DV and correct its dimension with 0's to match the mask dimension
    3. Build the yaml file for a single likelihood evaluation and ensure it points to the correct .dataset file
    4. The .modelvector's filename defined in the .dataset file must have the same name and path as the one defined in the yaml's flag print_datavector_file 
    4. Run CoCoA twice with:
        4a. The first one will return a worse chi2 (because it's using the arbitrary .modelvector) - this run overrides the .modelvector!
        4b. The second one must return a chi2 ~ 0 (because it's using the overrided .modelvector from the previous ran) 

MCMC_BASELINE{i} / nbins / status   
0 / 4  / running   
1 / 5  / running   
2 / 6  / running   
3 / 7  / running   
4 / 8  / running   
5 / 9  / x   
6 / 10 / x    