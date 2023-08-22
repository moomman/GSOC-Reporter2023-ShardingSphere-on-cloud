# GSOC-Reporter2023-ShardingSphere-on-cloud
# Project: "Introduce New CRD ShardingSphereChaos"

| **Student** | JinYang Zhao            |
| :- | :------------------------ |
| **Organisation** | [The Apache Software Foundation](https://github.com/apache)<br />                      |
| **Project** | [Introduce New CRD ShardingSphereChaos](https://summerofcode.withgoogle.com/proposals/details/bGtR94IT) <br />                     |
| **GitHub** | [@](https://github.com/ashaman999)​[moomman](https://github.com/moomman)                        |
| **Email** | agoiyanzsaban@gmail.com |

# About Me

Hello, I am JinYang Zhao, I am in my pre-final year the time when I am doing my GSoC, I am from China. I started contributing to Apache Software Foundation a while ago, for issues regarding the features I did during my GSoC period, feel free to reach me through my Email.

# Special thanks to my mentor and community:

* tuichenchuxin [@Github](https://github.com/tuichenchuxin)
* Maxwell Miao [@Github](https://github.com/mlycore)

# Primary Goals of the Project

* Design chaos based on ShardingSphere in a production environment.

* Implement it to out environment by operator.define the status and spec of the corresponding crd based on the actual chaos implemented (considering its duration, running state). The chaos can be managed by writing corresponding logic code in reconcile.

* Make it automatic and do a lot chaos experiments to improve system availability.

The main goal was somewhat already implemented, my work was mostly to retune the existing way to have a better experience for end users. I did the way to make chaos crds and controller to set chaos engineer in shardingsphere become easy and automatic.

The difficult part for me was implementing is inject pressure in chaos and how to verify result, I tried many ways to finish this job, but the results were not satisfactory. So we had to reinvent the wheel, took help from my mentor mlycore on this one on working by using litmus,which depend on argo workflow.

Another interesting part was when inject pressure req to environment.I made a Pressure measuring tool to handle it.In finishing this tool days, I learn a lot interesting program skills.

## A BRIEF OVERVIEW OF MY WORK

### Community Bonding Period

* Explored the working of the whole project
* Explored more about the Project details, learned more about async programming
* Learning more about Chaos Engineer, make crds and controller
* Explored chaos in the whole project
* Discussed with mentors how to get the thing done well

# Work During GSoC coding period

## All PRs related to my work during Google Summer for Introduce New CRD ShardingSphereChaos

* #### Add ShardingSphereChaos CRD and convert chaos to Chaos Mesh logic in Reconcile function [#286](https://github.com/apache/shardingsphere-on-cloud/pull/286)

  * Add basic convert type: Selector,Pod Chaos,Network Chaos,WorkFlow.

  * Add convert functions in Controller.Add convert and create chaos logic in Reconcile function.

  * Add ChaoKind Enums
* #### Add inject req and pressure spec and reconcile logic [#303](https://github.com/apache/shardingsphere-on-cloud/pull/303)

  * add spec to specify inject pressure and job
  * add reconcile logic to control
* #### change docker images and push,change images for job [#311](https://github.com/apache/shardingsphere-on-cloud/pull/311)

  * change docker images and push to dockerhub
  * change images for job default use
* #### add event and status.phase to control resource create check[ #312](https://github.com/apache/shardingsphere-on-cloud/pull/312)

  * add event to show sschaos info or warn
  * add status.phase to controller sschaos create resource time
* #### add verify Spec && update reconcile logic [#316](https://github.com/apache/shardingsphere-on-cloud/pull/316)

  * add verify Spec in chaos
  * update reconcile logic to prevent error in running operator
* #### Fix status.result bug[ #323](https://github.com/apache/shardingsphere-on-cloud/pull/323)

  * Fix status.result bug
* #### change chaos deletion to finalizer rather than ownreference [#337](https://github.com/apache/shardingsphere-on-cloud/pull/337)

  * Delete chaos resource by finalizer
  * remove ownreference.
* #### add chaos mock and test case for ssChaos[ #343](https://github.com/apache/shardingsphere-on-cloud/pull/343)

  * add chaos and db mock
  * test case for ssChaos
* #### add-pressure-exec replace job(get pod log)[ #358](https://github.com/apache/shardingsphere-on-cloud/pull/358)

  * add pressureCfg spec for pressure-exec
  * change status Msg to express steady And chaos experiment
* ### add cpu,memory,podkill chaos [#399](https://github.com/apache/shardingsphere-on-cloud/pull/399)

  * make cpu,memory,podkill chaos available

## Other Merged Pull requests

Since I get to know more about community the better I realized the number of people that are being affected by my work (my first time working on a project being used by thousands). In between the project, I stepped over my responsibilities to fix some ongoing issues in the production to further help the team deliver regular updates with fixed patches and a better experience.

* https://github.com/apache/shardingsphere-on-cloud/pull/252
* https://github.com/apache/shardingsphere-on-cloud/pull/257
* https://github.com/apache/shardingsphere-on-cloud/pull/275
* https://github.com/apache/shardingsphere-on-cloud/pull/305
* https://github.com/apache/shardingsphere-on-cloud/pull/403
* https://github.com/apache/shardingsphere-on-cloud/pull/364

### My overall contribution to Shardingsphere So Far

* [All PRs](https://github.com/apache/shardingsphere-on-cloud/pulls?q=is%3Apr+author%3Amoomman+is%3Aclosed)

* [Issues](https://github.com/apache/shardingsphere-on-cloud/issues/created_by/moomman)

### Further steps:

* Loved the community and going to stay here and enjoy the open source culture, Met really good mentors and organizers, That being said I can say I got what GSoC was intended for ie. loving the way to love doing opensource
* Further fix bugs, look into more features if intended to be implemented

### 

### Thank you [Apache Software Foundation](https://www.apache.org/) for an amazing summer of code!
