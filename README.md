# Extrema documentation

Extrema is a quite straightforward program to run. Its main requirement is to have the correct folder structure. You have to copy in 1_AWK/RAW_ALL/*_RAW directories the corresponding raw files. The rest of the directories will automatically be filled in. It should be like this:
```
├── 10_ATS
│   ├── ATS_Boom1_Calculations
│   ├── ATS_Boom1_Calculations2
│   ├── ATS_Boom1_Global
│   ├── ATS_Boom1_means
│   ├── ATS_Boom1_means2
│   ├── ATS_Boom2_Calculations
│   ├── ATS_Boom2_Calculations2
│   ├── ATS_Boom2_Global
│   ├── ATS_Boom2_means
│   ├── ATS_Boom2_means2
│   └── Read_Global
├── 1_AWK
│   ├── CLEAN_ALL
│   │   ├── ADR_CLEAN
│   │   ├── MD_CLEAN
│   │   └── NV_CLEAN
│   └── RAW_ALL
│       ├── ADR_RAW *Copy the ADR raw files
│       ├── MD_RAW *Copy the MD raw files
│       └── NV_RAW *Copy the NV raw files
├── 2_MEAN
│   ├── Mean1
│   │   ├── MD_CLEAN
│   │   ├── NV_CLEAN
│   │   ├── Out_Lowest_Temp
│   │   ├── Out_Mean_Pressure
│   │   ├── Out_Means
│   │   ├── Out_Means_GTS
│   │   ├── Out_Mean_UV
│   │   └── Out_Temp_B1_B2
│   ├── Mean5
│   │   ├── MD_CLEAN
│   │   ├── NV_CLEAN
│   │   ├── Out_lowest_Temp
│   │   ├── Out_Mean_GTS
│   │   ├── Out_mean_Pressure
│   │   ├── Out_mean_P_Tg_Ta_rho
│   │   ├── Out_mean_RH
│   │   ├── Out_Means
│   │   ├── Out_mean_Tg_P
│   │   ├── Out_mean_UV
│   │   └── Out_Temp_B1_B2
│   └── Mean6
│       ├── MD_CLEAN
│       ├── NV_CLEAN
│       ├── Out_lowest_Temp
│       ├── Out_mean_GTS
│       ├── Out_mean_Pressure
│       ├── Out_mean_RH
│       ├── Out_means
│       ├── Out_mean_UV
│       └── Out_Temp_B1_B2
├── 3_Splines
│   ├── Derivative
│   ├── GTSspli
│   └── Pspline
├── 4_RH
│   ├── RHSurface5
│   ├── RHSurface6
│   └── RHumidity
├── 5_UV
├── 6_HEA_COO
│   ├── Derivative_GTS
│   ├── localExtrema
│   └── splineGTS
├── 7_AirGround_Tdiff
├── 8_Extrema
├── 9_VMR_GTS
│   ├── RDR_Timestamp2
│   ├── VMR
│   └── VMR_GTS_P_MAX
├── main_No_RAD.py
├── main_RAD.py
├── Other_Files
│   └── msl_ls_sunrise_sunset_sol_0_to_7299_v_2_msl_sclk_v_13.dat
└── TOA
    └── sol_Ls_ABC1_TOA.dat
```

There are two script to run Extrema. One including the analisis of RAD and another one without including it. When you want to run pre-release data, with data not available from RAD use the "main_No_RAD.py" script. Normally we run this one.

In the scripts there are many path variables similar to "in_dir", or "out_dir", these variables must point to the correct path. Therefore, before starting a run, you have to make sure that the paths are correct. By default I have changed all the absolute paths to relative paths so you can run it anywhere without having to change the paths. I just mention it for you to have it in mind.

# Run the program 

The easiest way to work around it would be to do a git clone of this repository getting the correct structure and auxiliary files e.g. msl_ls_sunrise_sunset_sol_0_to_7299_v_2_msl_sclk_v_13. Then, copy the raw files in 1_AWK/RAW_ALL/*_RAW directories and finally run the python script.
```
$ git clone https://github.com/RobertoMantas/Extrema.git
$ cp PATH_TO_MD_RAW_FILES* 1_AWK/RAW_ALL/MD_RAW
$ cp PATH_TO_NV_RAW_FILES* 1_AWK/RAW_ALL/NV_RAW
$ cp PATH_TO_ADR_RAW_FILES* 1_AWK/RAW_ALL/ADR_RAW
$ python3.6 main_No_RAD.py
```
# Output

When the code finishes, in folder "8_Extrema/" you will find the extrema file output with the name you gave in line 7084.
