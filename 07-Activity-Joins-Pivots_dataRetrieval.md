---
title: 'Chapter 7: ACTIVITY: Joins Pivots dataRetrieval'
date: 2026-03-23T00:00:00.000Z
authors:
  - id: jpgannon
    name: JP Gannon
    email: jpgannon@vt.edu
    github: jpgannon
    orcid: 0000-0002-4595-3214
    corresponding: true
    url: https://jpgannon.github.io/
    affiliations:
      - vt-tech
affiliations:
  - id: vt-tech
    name: Virginia Tech
    url: https://www.vt.edu/
subject: Courseware
doi: https://doi.org/10.4211/hs.3219ef11b1bf4c7b9143c303149caf6c
venue:
  title: View Resource on HydroShare
  url: https://hydroshare.org/resource/3219ef11b1bf4c7b9143c303149caf6c/
github: https://github.com/VT-Hydroinformatics/7-Activity-Joins-Pivots_dataRetrieval
downloads:
  - file: 07-Activity-Joins-Pivots_dataRetrieval.md
  - file: 07-Activity-Joins-Pivots_dataRetrieval.pdf
---


# ACTIVITY: Joins Pivots dataRetrieval

This activity and the needed data are at
<https://github.com/VT-Hydroinformatics/7-Activity-Joins-Pivots_dataRetrieval>

## Load pacakges

Load the tidyverse, dataRetrieval, and patchwork packages. Set the theme
for plots to theme_classic()

## Problem 1 (8 pts)

Using readWQPqw, read all the chloride (00940) data for the New River at
Radford (03171000). Select the ActivityStartDate,
MonitoringLocationIdentifier, CharacteristicName, ResultMeasureValue,
ResultMeasure.MeasureUnitCode, and USGSPCode columns. Use the head()
function to print the beginning of the output from readWQPqw.

Call these data newriverWQ

## Problem 2 (8 pts)

Using the read_waterdata_daily (daily values) function, download
discharge (00060), temperature (00010), and specific conductance (00095)
for the New River at Radford from 2007 to 2009 (regular year), making
sure to skipGeometry. Keep the columns for monitoring_location_id,
parameter_code, time, value, unit_of_measure. Use head() to show the
beginning of the results of your download.

Call these data newphys

## Problem 3 (6 pts)

Do a left join on newphys and newriverWQ to add the chloride data to the
daily discharge, temp, and conductivity data. hint: you will join on the
date. Preview your data below the chunk using head().

Save these data as newwqp

## Problem 4 (10 pts)

Create a line plot of Date (x) and Flow (y) using newwqp. You will need
to filter the data based on parameter code! Create a scatter plot of
Date (x) and chloride concentration (y). Put the graphs on top of each
other using the patchwork library.

## Problem 5 (4 pts)

Use newwqp to create a scatter plot of Specific Conductance (y) and
Discharge (x). You will need to pivot table! Challenge: what could you
do to get rid of the warning this plot generates about NAs.

## Problem 6 (6 pts)

Read in the GG chem subset data and plot Mg_E1 (x) vs Ca_E1 (y) as
points.

## Problem 7 (10 pts)

We want to look at concentrations of each element in the \#6 dataset
along the stream (Distance), which is difficult in the current format.
Pivot the data into a long format, the data from Ca, Mg, and Na \_E1
columns should be pivoted. Make line plots of each element where y is
the concentration and x is distance. Use facet_wrap() to create a
separate plot for each element and use the “scales” argument of
facet_wrap to allow each plot to have different y limits.
