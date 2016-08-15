=======================================================
Report for Argonne Laboratory Computing Resource Center
=======================================================

Abstract
========
The rainfall project was proposed to LCRC to support a number of projects within
the Climate and Weather Research program of EVS. The primary project supported
was a Department of Homeland Security funded project investigating the impact of
the resolution of rainfall rate retrievals on modelled drainage network flows.
The original project was only aimed at producing several case studies but due to
the computing power available and the accessibility of the resource we ended up
retrieving high resolution rainfall rates, at the target site of Portland Maine,
for the entire radar record of 15 years.

New Results
===========
Unlike many projects run on LCRC the rainfall project is data informatical in
nature. Due to the highly parallel nature of the file system Blues enabled a deep and rapid exploration of the radar dataset. The deliverable to DHS was a set of rainfall retrievals for targeted times. Instead we performed rainfall retrievals for all available times. 

To do this we used IPCluster which is part of Project Jupyter [1]. IPCluster starts
python kernels on available cores and sets up a messaging system between these
workers and the controller node. This very simple multi-processing using a map
method within python. 

The dataset was 700,000 plus individual radar volumes collected from the NEXRAD
radar site in Gray, Maine. A simple reflectivity-rain rate relation was used to
retrieve instantaneous rain rate and a inverse distance weighted gridding
technique mapped the radar data to a constant height at the surface on a
100-100km domain at a 250 meter resolution. Py-ART [2] was the primary software package used and, thanks to its detailed IO layer, data was written out to a CF complaint [3] NetCDF file. 

In addition the domain mean and maximum rain rate was saved. This was primarily
done for job monitoring purposes but, given the gridded rainfall rate data set
is over a terrabyte, the simplicity of a time series data set has been very
popular with stakeholders as a way of isolating high impact events. 

We also looked at the temporal distribution of rainfall by partitioning it into hourly and monthly percentiles and means. Rainfall rates were split into separate distributions based on the hour of the day (local time) and the month of the year. We found many interesting pattens in Portland rainfall. For example we found first the rainfall distribution is skewed. That is, a greater contribution towards total rainfall comes 
from the more extreme events than the weaker events. 
We also found a clear diurnal (or daily) cycle with an overnight maximum. This is consistent with many studies 
of rainfall across the globe (eg [4]). This is due to the most widespread systems being more 
intense at night, the physical mechanisms are beyond the scope of this report but it is pleasing to see an expected 
natural and physically consistent variation apparent in the data. 
The monthly data shows a clear seasonal cycle with the percentiles exhibiting a fall and spring peak. However inspection
 of the mean and histograms to the right shows that while mid-scale events are more populous in spring and fall higher end 
events occur in summer as well. 

Project Impact
==============
Primarily the impact of using LCRC resources is that it allowed us to meet (and
greatly exceed) the expectation of our sponsor, 

New Capabilities
================
capabilities and stuff

Publications
============
published stuff

Presentations
=============
presented stuff

Grants
======
money



