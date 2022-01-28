# SIRET Junior
This organisation groups projects that are developed at the [SIRET research group](http://siret.ms.mff.cuni.cz). Specifically projects related to SOMHunter Video Search Tool.

## Overview of Repositories
Here is a brief overview of the repositories and what they mean in the overall context. Use this to determine where to look.

### **SOMHunter Tool**
This is the main software work. SOMHunter as a whole consists of multiple parts.

- #### [`somhunter`](https://github.com/siret-junior/somhunter)
The root project of the SOMHunter tool. If you wish to use the tool as a whole and not just some parts of it, this is where you start. By following the instructions in this repository you'll get yourself SOMHunter running in no time.

- #### [`somhunter-core`](https://github.com/siret-junior/somhunter-core)
The core of the tool. All the models and logic is implemented there. Basically, all other parts of the tool (UI, data/ranking server, ...) are somewhat optional. You can use your own implementation and substitute them. All these parts are separated using HTTP API and the core complies with the OpenAPI standard so it should be relatively easy to write your own UI for example.

- #### [`somhunter-ui`](https://github.com/siret-junior/somhunter-ui)
A user interface for the SOMHunter. It is implemented as a web application using the Ember.js framework. This part just uses the HTTP API of the `somhunter-core`.

- #### [`somhunter-data-server`](https://github.com/siret-junior/somhunter-data-server)
Currently, a simple server serving frames over the HTTP protocol. `somhunter-ui` requests this server to get frames and thumbnails.

- #### [`ranking-server`](https://github.com/siret-junior/ranking-server)
A general server that provides an on-demand ranking for configured models. It can embed textual queries to respective vector spaces or do the scoring and return just score. 

It is not attached to SOMHunter because it is used by other search tools (e.g. CVHunter) as well. Therefore its configuration must be done seperately and is not done based on config files inside the `somhunter-core` project.

- #### [`somhunter-docs`](https://github.com/siret-junior/somhunter-docs)
Thorough written user and developer documentation for the SOMHunter project as a whole.

### **Preprocessing Tools**
For SOMHunter to work you also need some extracted metadata from the dataset you want to search in.

- #### [`extraction-pipeline`](https://github.com/siret-junior/extraction-pipeline)
There are two variations of the pipeline (for W2VV++ model with subregions & for CLIP model) authored by [Tomas Soucek](https://github.com/soCzech). This is mainly his work. With his permission, we modified the pipeline to extract also subregions of frames. This is still private repository. If you'd like to use it contact us.

### **SOMHunter Collector & Simulator**
These tools were used for relevance feedback study.

- #### [`som-collector`](https://github.com/siret-junior/som-collector)
This is the fork of SOMHunter that was developed specifically for wide relevance feedback study. This version is altered so multiple users can use the same core to collect data while they are solving tasks.

- #### [`somhunter-collector-tester`](https://github.com/siret-junior/somhunter-collector-tester)

### **Analysis Tools**

- #### [`somhunter-user-analysis`](https://github.com/siret-junior/somhunter-user-analysis)
Scripts were used to analyze user behaviour while using the SOMHunter tool for the wide relevance feedback study.

- #### [`log-analyzer`](https://github.com/siret-junior/log-analyzer)
These are python scripts that were used for VBS 2021 log analysis.


> Any other repositories not mentioned here have no significane (yet) so do not pay attention to them.
