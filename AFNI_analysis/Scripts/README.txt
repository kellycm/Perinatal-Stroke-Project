Scripts last backed up 4/12/19 from Kelly's Mac to red KellysDrive.

0.template has the basic setup of paths and an unfilled loop

1.PSP_dimon (Oct 29 2018)  enters each subject's raw task epi folder and converts all .IMA or for some subjects .dcm and converts them to AFNI's BRIK format

2.PSP_afni_proc has an older version (Nov 7 2018) of the afni_proc.py setup, but it only analyzes one run of data. It may be useless.

2a.PSP_afni_proc_combine_runs a newer version (Feb 22 2019) of the afni_proc.py setup that analyzes both runs of data. runs tshift, align, tlrc, volreg, blur, mask, scale, and regress.

2b.PSP_afni_proc_Feb2019 runs an even newer version (Feb 25 2019) of afni_proc.py that is simpler than the 2a script: tlrc, align, no cost function for align?

2c.PSP_align_and_warp (Feb 24 2019) attempts to align stats image to MNI space using transformation matrix of anatomical to MNI space. I am not sure this worked.

3.PSP_exe_afni_proc (Nov 7 2018) runs the outfile generated for each subject by 2.PSP_afni_proc in tshell. - I don't use the 2 script because it only analyzes one run so this one is probably useless also.

3a.PSP_exe_afni_proc_combine_runs (Feb 25 2019) executes the outfile generated for each subject by 2a, 2b, or 2c. Really the only difference from script 3 is that it puts it in a task folder that combines both runs.

4a.PSP_3dTcat_betas (Dec 19 2018) copies the stats images for the designated group and concatenates the betas for the specified subbrick (one subbrick for each stat output, F T and Coef aka beta, of each contrast of interest, Fwd>Rest, etc.) to make a new nii image where each voxel has the range of betas for each subject.

5a.PSP_auto_warp (Feb 21 2019) attempts to warp the stats image to the anatomical using the transformation matrix from warping the anat to MNI space. I think this worked better than 2c.

6.PSP_3dttest_controls (Feb 25 2019) performs a ttest over the designated group of subjects for the specified subbrick (see description for script 4a for explanation of subbricks) and generates a new ouput.ttest nii.


