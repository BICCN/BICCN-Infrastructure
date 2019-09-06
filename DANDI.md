# DANDI: Distributed Archives for Neurophysiology Data Integration

## Description
DANDI is a platform for publishing, sharing, and processing neurophysiology data funded by the BRAIN Initiative. We will work with BICCN and other BRAIN awardees to curate data using community standards, and to make data FAIR (Findable, Accessible, Interoperable, and Reusable). We will use DANDI to help improve our understanding of the brain.

# Roles
- [Primary Investigator] Satrajit Ghosh (satra@mit.edu)
- [Primary Investigator] Yaroslav Halchenko (yoh@dartmouth.edu)
- [NWB and community liaison] Ben Dichter (ben.dichter@gmail.com)
- [Co-Investigator] Michael Grauer (michael.grauer@kitware.com)

## Definitions
HDF - Hierarchical Data Format supports an unlimited variety of datatypes, and is designed for flexible, efficient I/O and for high volume and complex data.

NWB - Neurodata Without Borders. The NWB file specification can capture the entirety of heterogeneous data representing an experiment and is built on top of HDF. 

NWB:N - NWB:Neurophysiology, is a common file format that accommodates a wide variety of neurophysiology data as well as complex metadata related to stimulus and behavior. This is being developed under BRAIN award [1R24MH116922-01](https://projectreporter.nih.gov/project_info_description.cfm?aid=9582696).

## Objectives
- Develop a cloud platform for versioned neurophysiology data storage for the purposes of collaboration, archiving, and preservation. 
- Provide easy to use tools for neurophysiology data submission and access in the archive; and 
- Facilitate adoption of NWB via standardized applications for data ingestion, visualization and processing.

As an exercise, let’s assume you lose all the data in your lab. What would you want from the archive? Our hope is that your answer to this question, the necessary data and metadata that you need, is at least what we should be storing.

Our goals for the archive, we think, are rather simple:

- Optimize storage based on cost to produce and process.
- Enable reproducible practices and publications.
- Enable secondary uses of data outside the intent of the study.
- Reduce the need to contact data producers by enriching the data with rich metadata.
- If users have to come back to the raw data, for example, to apply different processing strategies, etc., it should be feasible without going to the data producer.
- The archive is not just an endpoint to dump data, it is intended as a living repository that enables collaboration within and across labs, and for others, the entry point for research.

## In-scope
- Develop infrastructure for ingesting, storing, searching across, and retrieving datasets containing cellular neurophysiology data and common data derivatives
- Develop web portal to support data and workflow management
- Support for BRAIN standards (NWB:N, BIDS, NIDM)
- Data availability with at least file level atomicity
- Provide human and programmatic search of data and metadata
- Store derive data if it is of use to the community beyond a lab
- Provide software to capture experimental metadata, convert to NWB, and upload/download data to/from the archive
- Support browser-based visualization of data
- Provide tutorials and training for users to use the archive
- We will allow limited storage of private data with an embargo period, after which data becomes public

## Out-of-scope
- Develop neurophysiology standards
- Develop neurophysiology software
- Provide unlimited computing resources

## Communication

- [Website](https://dandiarchive.org/)
- [SlackApp/channel](https://dandiarchive.slack.com/) For communication with the DANDI team 
- [Neurostars](https://neurostars.org/) For general questions about the archive
- [Twitter: @dandiarchive](https://twitter.com/dandiarchive)
- [Github](https://github.com/dandi)
