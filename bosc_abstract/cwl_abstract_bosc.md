--------------   -------------------------------------------
**Title**        Portable workflow and tool descriptions with the CWL
**Authors**      Peter Amstutz^0^, Nebojša Tijanić^1^, Stian Soiland-Reyes^2^, John Kern^3^, Luka Stojanovic^1^,
                 Tim Pierce^0^, John Chilton^4^, Maxim Mikheev^5^, Samuel Lampa^6,7^,
                 Hervé Ménager^8^, Scott Frazer^9^, Venkat Sai Malladi^10^, \underline{Michael R. Crusoe}^11^
**Affiliations** 0. Curoverse Inc. 1. Seven Bridges Genomics, Inc.
                 2. University of Manchester, School of Computer Science
                 3. AccuraGen Inc. 4. Penn State University, The Galaxy Project 5. BioDatomics Inc.
                 6. Uppsala University, Department of Pharmaceutical Biosciences
                 7. BILS (Bioinformatics Infrastructure for Life Sciences) 8. Institut Pasteur
                 9. The Broad Institute 10. Stanford University
                 11. University of California, Davis, School of Veterinary Medicine 
**Contact**      crusoe@ucdavis.edu
**URLs**         <http://common-workflow-language.github.io/>
                 <https://github.com/common-workflow-language/common-workflow-language/>
**License**      [Apache License, Version 2.0](https://github.com/common-workflow-language/common-workflow-language/blob/master/LICENSE.txt)
--------------   -------------------------------------------

<!-- Prompts in HTML comments are from

http://phdtalk.blogspot.ro/2011/08/how-to-write-abstract-in-30-minutes.html -->

<!-- Motivation: Why do we care about the problem and the results? -->

Bioinformatics workflow platforms provide provenance tracking, execution and
data management, repeatability, and an environment for data exploration and
visualization. Example F/OSS bioinformatics workflow platforms include
[Arvados](https://arvados.org/),
[Galaxy](http://usegalaxy.org/),
[Mobyle](https://projets.pasteur.fr/projects/mobyle/wiki),
[iPlant DiscoveryEnvironment](http://www.iplantcollaborative.org/ci/discovery-environment),
[Apache Taverna](http://taverna.incubator.apache.org/)
and [Yabi](https://ccg.murdoch.edu.au/yabi).
Each one
presently represent workflows using different vocabularies and formats, and
adding new tools requires different procedures for each system.

<!-- Problem statement: What problem are you trying to solve? -->

Neither the description of the *workflows* nor the descriptions of the *tools* that
power them are usable outside of the platforms they were written for.
This results in duplicated effort, reduced reusability, and impedes
collaboration.

<!-- Approach: How did you go about solving or making progress on the problem?
Did you use simulation, analytic models, prototype construction, or analysis of
field data for an actual product? -->

Three engineers (Peter Amstutz, John Chilton, and Nebojsa Tijanic) from
leading bioinformatics platform teams (Curoverse, Galaxy Team, and Seven
Bridges Genomics) and a tool author (Michael R. Crusoe / khmer project)
started working together at the BOSC 2014 Codefest
with an initial focus on developing a portable means of representing, sharing
and invoking command line tools which was then the basis for portable workflow
descriptions. The group placed high value on re-using existing formats and
ontologies; they governed themselves with a lazy consensus / do-ocracy
approach.

<!-- Results: What's the answer? -->

On March 31st, 2015 the group released their second draft of the
[Common Workflow Language specification](http://common-workflow-language.github.io/).
The serialized form is a YAML document that is
validated by an [Apache Avro](https://avro.apache.org/) schema and can be
interpreted as an RDF graph using
[JSON-LD](http://json-ld.org/). The documents are also valid
[Wf4Ever 'wfdesc'](http://wf4ever.github.io/ro/#wfdesc) descriptions after a simple
transformation. Future drafts will include the use of the
[EDAM ontology](http://edamontology.org) to
describe the tools enabling discovery via the
[ELIXIR tool registry](https://elixir-registry.cbs.dtu.dk/).

<!-- Conclusions: What are the implications of your answer? Is it going to
change the world (unlikely), be a significant "win", be a nice hack, or
simply serve as a road sign indicating that this path is a waste of time (all
of the previous results are useful)? -->

Seven Bridges Genomics, the Galaxy Project, and the organization behind Arvados
[(Curoverse)](https://curoverse.com/) have started to implement
support for the Common Workflow Language, with interest from other projects
and organizations like Apache Taverna,
[BioDatomics](http://www.biodatomics.com/)
and the [Broad Institute](https://www.broadinstitute.org/). Developers on the
Galaxy Team are exploring adding CWL tool description support with plans to add
support for the CWL workflow descriptions. Tool authors and other community
members will benefit as they will only have to describe their tool and workflow
interfaces once. This will enable scientists, researchers and other analysts to
share their workflows and pipelines in an interoperable and yet human readable
manner.
