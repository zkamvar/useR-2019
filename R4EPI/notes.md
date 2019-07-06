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

# The R4EPIs project: a new hope

## The dream

Epidemiologists are key for organizations like MSF to respond to outbreaks and
monitor situations that may lead to outbreaks. Data from patients are
collected, aggregated, analyzed, and summarised in reports that lead to
operational decisions and interventions, which could include ensuring
allocating food aid or beds to new regions. The hope of the epidemiologist on
the ground is that the spend the vast majority of their time out in the
community, supervising the data collectors to get a sense of the context and
risk factors. This background context can then be combined with the data
analysis and used to inform the response.

## The reality

The reality, however, is that field epis are spending most of their time
adapting their predecessors analysis code from proprietary software, cleaning
data, running and re-running statistical analyses by hand, and copying/pasting
reports together. They can easily spend an entire day doing this for one weekly
report and then do it all over the next week. 

## The hope

It's from this context that the R4EPIs initiative was born. We wanted to
improve the way MSF responds to outbreaks and emergencies by creating
standardized and automated situation reports along with educational materials
so that field epis could spend more time thinking about how the data fits in
with the context. 

This project is still ongoing, so I will be discussing the unique challenges
that we faced in the group effort, feedback that we've gotten from field epis
who have tested out these automated reports and tools, and a peek at where we
are heading in the future of this project.

## Links

 - https://github.com/R4EPI/sitrep
 - https://blogs.msf.org/bloggers/larissa/innovation-introducing-r4epis

## Acknowledgements

Because there is the risk I will run out of time (though Rich will make
absolute certain that I do not), I wanted to make sure to acknowledge the vast
amount of people who have contributed to this effort. We had a unique
combination of field staff, advisors, and academics helping out this
collaboration between MSF and RECON.

Annick Lenglet and Amrish Baidjoe were instrumental in securing the MSF Sapling
Nursery funding for this proposal and Annick has been a fantastic manager and
coordinator of the effort.

# Laying the groundwork

## Priorities

We prioritized creating templates for specific outbreak scenarios based on the
amount of data standardization, frequency in MSF settings, and that had epis who
most familiar with or most keen to learn R. These included outbreak reports from
four scenarios, Cholera, Meningitis, Measles, and Acute Jaundice Syndrom. We
also included reports for Malnutrition, Vaccination Coverage, and Retrospective
mortality and access to care. These would be based off of MSF templates.

## Steps

1. Adapt MSF templates to RMarkdown 
2. Identify relevant packages for descriptive analysis
3. Write the analysis
4. Trim out the repetative bits into functions
5. Test with field epis 

## Development

Mean to lean: we wanted to develop templates and that would produce results
first and then abstract out into custom functions for summary tables and
visualisations, which are not in theory difficult to create, but can contain
pitfalls that new users to R may not be aware of (e.g. default dropping of
factor levels).

When we were developing the reports, we wanted to make sure that we avoided
re-inventing the wheel as much as possible, while still giving output highly
tailored to the expectations of MSF field epidemiologists. We also wanted to
make sure that the packages we used were trustworthy (e.g. they had tests and
continuous integration at a minimum). 

For workflow, we opted for an open GitHub flow where all contributors to the
repository needed to have 2FA set up. 

# What did we accomplish

We created automated situation reports from standardised DHIS2 exported data 
for field epis to use. We have an R package that hosts these templates and the
functions to work with them. These templates and functions will properly perform
analyses without unexpectedly dropping variables and abstracting away tedious
details for producing common visualisations (such as age/gender pyramids).

This effort also resulted in the new CRAN package `aweek`, which makes simple
conversion from dates to weeks, starting on any day of the week.

# Challenges

## Existing packages

When we assessed the existing packages for this project, there were several
packages related to epi analysis that either had no tests or no integration, or
both. There were some spatial packages that we considered using for interactive
maps, but unfortunately these had a buried dependency on rJava, which is
notoriously difficult to install. There were some packages that worked fine and
produced summary tables, but the output was either too verbose, not verbose 
enough, or in an odd format that didn't quite align with our goals. 

 - no tests
 - no integration
 - required rJava
 - not-quite-there output (srvyr was a good example)

## Contributing

Several of our contributors were first-time contributors who had learned R in a
data analysis context, so there were often issues with bare variable names and 
pipes that would throw warnings and errors in the check process. People new to
git and github would for the repository and make changes to the master branch
instead of a separate branch. 

## Weight

We did not have direct access to the data, so we handled this in two ways. In
order to test the package on linelist data, we generated data based on the
DHIS2 data dictionaries. In order to test how well they worked with real-world
data, we sent them to epidemiologists in the field to test them. This revealed
an additional hurdle: because we needed to handle descriptive, survey, and 
geospatial data, the weight of the packages used was fairly heavy and difficult
to successfully install on the first try in the field where a 128K connection is
considered fast. 

# Hackathon

We held two half-day hackathons on 4-5 July 2019 that brought together several
field epis to test out these templates on their field data. We had set up a
group conference call where we could share screens and organised conversations
on an etherpad. 

## Overall impressions

 - Labelling instructions in comments is not a particularly easy task as people
   are wont to gloss over them. 
 - Renaming and matching variables is *hard* and frustrating
 - examples need to actually match the data set due to cognitive overhead for
   newbies.
 - Depending on the level of the R user, the concept of comments were not always
   intuitive

Most people had non-standard data, so the longest part was ensuring that the
variables matched up with the data. We had a helper function to help rename the
variables based off of the dictionary, but this printed in order of the
dictionary and, in the words of one epi, "Renaming variables without any order
is *exquisitely painful*"

# Future work

## Upkeep

For maintenance, we need to do an concious decoupling of sitrep into tinier unit
packages for visualisation, descriptive statistics, and survey statistics. We
still have yet to create a landing page for new users with instructions on how
to use this tool and tutorials. We have a wiki, but that's more of a placeholder
for now. 

## Tutorials

We plan to set up a tutorial site that can help guide people through basics 
descriptive analyses in R that will additionally come with a video component
courtesy of Dr. Greg Martin, who hosts a youtube video series about data analysis
in R in his spare time. There are ideas of hosting R sprints/battles where 
specific analytical tasks are posed to two epis and the code it out and compare
the two solutions. 

All in all, we still have a ways to go, but I, for one, am super excited to get
there.


--------------------------------------------------------------------------------


 

## Quotes

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


















