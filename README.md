# GNSS processing scripts and utilities
This repository contains a series of jupyter notebooks to postprocess GPS data. Each notebook is oragnized within a folder, where also example files are stored.

This dataset can be cited via the DOI provided in Zenodo: [![DOI](https://zenodo.org/badge/268749470.svg)](https://zenodo.org/badge/latestdoi/268749470)

# Comparison of two GNSS points within error ellipses
This script compares the distance of two GNSS points (Lat/Lon/Height Above Ellipsoid) within their uncertainties. 

![alt text](GNSS_data_comparison/GNSS_comparison.svg)

## Single GNSS position from multiple points
This script usess a Monte-Carlo approach to calculate the average position (with positioning uncertainties) given a series of GNSS points collected at the same location. It can be used, for example, when several processing options are available for a base station point. The result is a single averaged position, with associated Lat/Lon/elevation 2-sigma uncertainties.

![alt text](GNSS_Averaging/GNSS_averaged.svg)

## PPK processing of "Stop and Go" data
This script can be used to process GNSS data acquired in "stop-and-go" mode. The script needs the following inputs:

 - Rover data processed with RTKlib as kinematic points and saved as *.pos* file
 - Files exported from the data collector in *.csv* format

The script first merges the data collector files into a single dataframe. Then, postprocessed rover data is imported and a new dataframe is created with time-averaged postprocessed static positions acquired in FIX status. Time-averaged positions are also calculated for FLOAT and SINGLE status datapoints. All the results are saved in a multi-sheet excel file.

For a guide on how to use the NRCAN system and RTKlib with EMLID GPS, see:
https://docs.emlid.com/reach/common/tutorials/ppp-introduction/

This discussion on the EMLID forum contains some useful insights on the processing, as well another (similar) tool, including an intuitive user interface. The results of this script compare well with those obtained from this tool.
https://community.emlid.com/t/ppk-point-extractor-software/12822/46

## RTK postptocessing

This script can be used to process data from two GNSS receivers that were set to collect data in RTK mode, for which the precise base position was not available at the time of survey. To use the script, the following inputs are required:

 - Initial base station position
 - Corrected Lat,Lon,Height of base station
 - Files exported from the data collector in *.csv* format

A general outline of the survey workflow is explained here:

https://docs.emlid.com/reach/common/tutorials/placing-the-base/

## RTKlib .pos file to .csv
This script converts .pos data (output of RTKlib) to .csv files
