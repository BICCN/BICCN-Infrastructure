# DANDI: Distributed Archives for Neurophysiology Data Integration

## Description
DANDI is a platform for publishing, sharing, and processing neurophysiology data funded by the BRAIN Initiative. We will work with BICCN and other BRAIN awardees to curate data using community standards, and to make community data and software for cellular neurophysiology FAIR (Findable, Accessible, Interoperable, and Reusable). DANDI will store cellular neurophysiology electrical and optical recordings and associated MRI and/or optical imaging data.

# Roles
- [Principal Investigator] Satrajit Ghosh (satra@mit.edu)
- [Principal Investigator] Yaroslav Halchenko (yoh@dartmouth.edu)
- [NWB and community liaison] Ben Dichter (ben.dichter@gmail.com)
- [Co-Investigator] Michael Grauer (michael.grauer@kitware.com)

## Definitions
[HDF - Hierarchical Data Format](https://www.hdfgroup.org/solutions/hdf5/). HDF supports an unlimited variety of datatypes, and is designed for flexible, efficient I/O and for high volume and complex data.

[NWB - Neurodata Without Borders](https://www.nwb.org/). The NWB file specification can capture the entirety of heterogeneous data representing an experiment and is built on top of HDF. 

[NWB:N - NWB:Neurophysiology](https://www.nwb.org/nwb-neurophysiology/). NWB-N is a common file format that accommodates a wide variety of neurophysiology data as well as complex metadata related to stimulus and behavior. This is being developed under BRAIN award [1R24MH116922-01](https://projectreporter.nih.gov/project_info_description.cfm?aid=9582696).

[BIDS - Brain Imaging Data Structure](https://bids.neuroimaging.io/) A specification for a file system layout and associated metadata of neuroimaging (MRI, EEG, MEG, iEEG, eCOG) data. The specification enables human readability and accessibility of the metadata in a filesystem. BIDS is an [INCF](https://www.incf.org/) [endorsed standard](https://www.incf.org/node/295).

[NIDM - Neuro Imaging Data Model](http://nidm.nidash.org/). A [W3C-PROV](https://www.w3.org/TR/2013/REC-prov-dm-20130430/) based specification for capturing experimental representation, workflow specification and execution, and analysis results for neuroimaging. Stitches metadata of objects through a directed graph model. BIDS and NIDM [complement each other](https://f1000research.com/documents/8-1373).

Derived data. Derived data are files/objects created by software transformations of the data captured by a data capturing device (electrode, microscope, MRI scanner) or other derived data. 

## Objectives
- Develop a cloud platform for versioned neurophysiology data storage for the purposes of collaboration and dissemination of data and software containers. 
- Provide easy to use tools for neurophysiology data submission and access in the archive; and 
- Facilitate adoption of NWB via standardized applications for data ingestion, visualization and processing.

As an exercise, let’s assume you lose all the data in your lab. What would you want from the archive? Our hope is that your answer to this question, the necessary data and metadata that you need, is at least what we should be storing.

## In-scope
- Data modalities: multi-channel or single channel timeseries and 3D/4D imaging data
- Develop infrastructure for ingesting, storing, searching across, and retrieving datasets containing cellular neurophysiology data and common data derivatives
- Develop web portal to support data and workflow management
- Support for BRAIN standards (NWB:N, BIDS, NIDM)
- Data availability with at least file level atomicity
- Provide human and programmatic search of data and metadata
- Store derived data if it is of use to the community beyond a lab
- Provide software to capture experimental metadata, convert to NWB, and upload/download data to/from the archive
- Support browser-based visualization of data
- Provide tutorials and training for users to use the archive
- We will allow limited storage of private data with an embargo period, after which data becomes public
- Support data exchange with BCDC and or other archives as needed to support linking patchseq data as well as to enable BCDC integration to enable a user at Cell Registry to be directed to a subset of data at DANDI

## Out-of-scope
- Develop neurophysiology standards
- Develop neurophysiology software
- Provide unlimited computing resources
- Pure MRI imaging datasets without any cellular level data. These should go to [OpenNeuro](https://openneuro.org/) using the BIDS standard.

## Communication

- [Website](https://dandiarchive.org/)
- [SlackApp/channel](https://dandiarchive.slack.com/) For communication with the DANDI team 
- [Neurostars](https://neurostars.org/) For general questions about the archive
- [Twitter: @dandiarchive](https://twitter.com/dandiarchive)
- [Github](https://github.com/dandi)

## Funding
[NIMH 1R24MH117295-01A1](https://projectreporter.nih.gov/project_info_description.cfm?aid=9795271)
