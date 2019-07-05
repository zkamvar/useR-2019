Zhian Kamvar  [3 days ago]
What have been the successes of the project? What were the drawbacks?

Alex Spina  [13 minutes ago]
Think the major success is simplifying, standardising and unifying methods for
analysis. Not sure we are entirely there yet but hey presto theory. Think the
major drawbacks to date are the lack of field testing ... hackathon half
addresses that but is still very in-vitro testing!

Alex Spina  [12 minutes ago]
Think the other thing this package gives beyond just msf field work ... is
generally simplifying R for all epis!


Zhian Kamvar  [3 days ago]
Some things I'm specifically wondering about:

What does a day in the life of a field epi look like and how does R4EPI fit
into that?

Alex Spina  [14 minutes ago]
the hope is that the majority of the time you are spending out in the
community, supervising data collectors and getting a feel for the context/risk
factors. What tends to happen is that you have messy data so spend a lot of
time cleaning and then double checking / going back to data managers and
collectors to try and fix inconsistencies. Then probably about once a week you
spend time pulling together figures and numbers from different excel sheets to
write a sitrep together ... which probably ends up taking a whole day depending
on how messy everything is.

.... back logs... more messy data.... no field time.... more messy data.... you
get the picture.
R4epi in theory simplifies and standardises all of that so that you save a lot
of time pointing and clicking and finding files - and spend more time out doing
what field epi is about.

--------------------------------------------------------------------------------

Fifteen minutes is enough to divide the talk up into 

# Introduction

## Links

## Acknowledgements

# What does an epidemiologist do?

## Data Collection


## Analysis

## Operational Decisions/Interventions

Amrish: 

> A field epidemiologist plays a central role in the flow and analyses of data
> and helps with on one side facilitating acquisition and on the other side
> distilling actions by collecting data from different sources in the field.
> After analyses findings have to be communicated to inform the appropriate
> course of action

# What are the gaps?

> For an epi we spent a lot of time on data collection and data analysis, whilst
> our joint emphasis needs to be on action (operational decisions and
> interventions), to get there we need to move through the data forest which
> consists of bottlenecks (text), but for all of these bottlenecks we can offer
> technical solutions and massive reduce delays and increase consistency 

Annick:

> STATA expensive and STATA license management across 25 countries with rapid
> handover between field epi's was difficult to manage So we knew we needed to
> switch to R We thought the easiest way to convince people would be to give
> them scripts they could actually use for frequent analysis questions

# R4EPIs initiative RECON + MSF

This initiative started out of a proposal to the Sapling Nursery fund from MSF,
which supports MSF staff in developing new ideas that can have a broad impact. 

The situation was that MSF field epis were spending most of their time on data
analysis and not much time in contact with the data collectors, getting a sense
of the context. Most of the STATA scripts were ad-hoc and the STATA licenses
were difficult to maintain across 25 countries with rapid handover between field
epis. The hope was that MSF could better reduce costs by switching to R and also
ensuring that the analyses were suited to their needs.

Annick and Amrish got together and wrote the proposal. We had an initial meeting
in October of 2018 with epis, managers, NGOs and RECON to get a sense of what
the landscape was.

# Creating templates

Using RMarkdown templates early on was the goal. They provided a simple way to
combine prose and code directly to a word document (which was what field epis
were used to). The idea was to create a package to host these templates that
initially contained helper functions to create 2x2 tables and other descriptive
statistics such as non-naive case fatality ratios and age-sex pyramids.

# Challenges

There were several packages available for epi analysis on CRAN, but we wanted to
ensure that these packages were at least tested and had a consistent interface.
Unfortunately, not very many appeared to have tests or were even updated 
recently.

Field epidemiologists are varied in their training for statistical tools. Most
will be familiar with excel, other will be familiar with STATA, and the newer
cohorts will have had some training in R. 


















