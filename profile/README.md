# Waggle AI@Edge
<img src="https://raw.githubusercontent.com/waggle-sensor/.github/main/profile/Photo1.png" width="900"></br>
**Figure 1:** Spanning from the network edge to the Cloud and HPC, Waggle AI@Edge is a programmable cyberinfrastructure composed of software and hardware, for interfacing new sensors, actuators, and instruments through traditional computing and AI/ML inference. The figure shows the various building blocks of the Waggle framework.
</br>
</br>
Waggle is a state-of-the-art open-source platform for developing and deploying novel artificial intelligence algorithms and new sensors into distributed sensor networks.  By providing  advanced edge computing capabilities, researchers and practitioners using Waggle can analyze high-resolution instrument data at unprecedented speeds, providing new insights and answering scientific questions not previously possible. 

In many scientific disciplines, sensors and instruments are deployed in remote locations to provide valuable, real-time data streams.  In the Western US, remotely deployed cameras are used to provide real-time images of wilderness areas to aid in wildfire monitoring.  In cities, air quality sensors are used to understand the impact of electric vehicles.  In prairies, audio data streams can be analyzed for birdsong to provide key data on bird migrations. The sensing needs of the above studies differ vastly. To support these significantly varying scientific endeavors Waggle provides two key features: low-power edge computing embedded into distributed sensor arrays and a modular architecture for easily integrating new sensors.  

In the domain science communities, there is a technological gap and significant barrier to entry to being able to efficiently design, build, and deploy instrumentation to study such widely varying phenomena and activities, by small groups of researchers. Sensors and instruments which can be programmed and extended using established computer science techniques and programming practices are fundamental to making them easily accessible and readily usable. More than a feature, the strong integration of software with hardware to extend a “software-defined-instrument”, is a necessity. Waggle enables rapid development of customized, networked, and scalable field-ready instrumentation involving cutting-edge sensors and actuators, and associated low-latency AI/ML inference through edge-computing. It allows integration with centralized cloud and HPC resources for advanced and global observations, inferences, and model development. 

[Get started with Waggle!](https://docs.waggle-edge.ai)
</br>
</br>
<img src="https://raw.githubusercontent.com/waggle-sensor/.github/main/profile/Photo3.png" width="900"></br>
**Figure 2:** The NSF funded [Sage project](https://sagecontinuum.org/) is deploying several Waggle based Wild Nodes and Blades for research in a wide variety of science domains.  The figure shows some of the current deployment locations. Sage will deploy over 120 nodes across the world.
</br>
</br>

The name for the project comes from nature’s wireless sensors — honeybees. Bees search far and wide for pollen, and report their findings back to the hive using a sophisticated dance called a [“waggle dance“](https://en.wikipedia.org/wiki/Waggle_dance). The dance encodes the distance and angle to the food source, and is often similar to a figure-8 — which is why we picked [wa8.gl](http://wa8.gl/) as our domain name. Waggle is free under the terms of an open-source license. 

Already, Waggle is being used to instrument and understand cities, which has applications in traffic studies, urban design, sociology, and environmental science; study, design, and improve detection of radiological materials which has security and safety implications; study forest fires and re-growth; basic computing and systems research; and as the core platform for extending a national scale cyberinfrastructure for science. The core Waggle team is based at DOE’s Argonne National Laboratory, dedicated to advancing state-of-the-art  and open science.

Waggle enables researchers, scientists, academics, practitioners and communities to unlock discoveries faster using artificial intelligence, specialized sensing, actuation, and instrumentation . Waggle follows continuous development and does not have point releases. The current version of Waggle called “Waggle AI@Edge” provides three new features - support for a new class of advanced edge-focused computing hardware (ARM64 and x86-64); a new edge-application development, deployment, and management capability using industry standard software tools and practices; and the edge-code repository - an open repository for aggregation, validation, profiling, and sharing of edge applications. 

# Waggle AI@Edge Basics

Developed over 8 years, Waggle is a new kind of reusable cyberinfrastructure to enable AI at the edge. The illustration (Photo1) shows a high-level view of the Waggle AI@Edge architecture and enumerates the various software services, tools, and infrastructure elements. Two major components combine to provide the Waggle AI@Edge infrastructure.
 
First, there are the physical Waggle nodes, which are extensible and allow integration of new sensors and instruments. Waggle nodes are designed to be easily deployable into existing network infrastructure. Second, there are the software cyberinfrastructure elements, which support various services for aggregation and dissemination of data, compiling, containerization, and profiling of applications,  and control and management of the nodes. The overarching software cyberinfrastructure also connects the nodes to other cloud/HPC resources and users. The Waggle project on GitHub provides various reference designs for the hardware nodes and the software cyberinfrastructure as a collection of modules.

 
## Waggle Nodes

 Following a modular design, nodes enable rapid integration of new sensor technologies, from LiDAR to precision micro-synchrophasors for analysis of electrical distribution systems. While the earlier version of Waggle (one used by AoT) only supported ARM32 architectures, in the most recent Waggle AI@Edge release, we added support for ARM64 and x86-64 edge-focused computing hardware. There are two variants of Waggle Nodes:
 
[**Wild Waggle Nodes (WWN)**](https://github.com/waggle-sensor/wild-waggle-node) are weatherized for remote, outdoor deployment in remote and hard-to-reach locations. An important feature of our design is the addition of resilience software and electronic hardware elements. The [Waggle manager](https://github.com/waggle-sensor/wagman), Wagman, is a custom printed circuit board for environment and health monitoring, and active power control. Wagman can disconnect malfunctioning devices or reboot components with backup software stacks, providing robust operation in remote and harsh locales. Designed to be extremely reliable and resilient, the new release of [Wagman (V5)](https://github.com/waggle-sensor/wagman/tree/master/boards/v5) performs all these tasks entirely through hardware components, requiring no firmware. The next most important device is the [Node Controller](https://github.com/waggle-sensor/nodecontroller). It is a single-board Linux computer providing encrypted TCP/IP messaging, data caching, node health monitoring, and access to connected sensors and actuators. While the above tasks are its main priority, the node controller is also available to run (through container-based isolation technologies) user applications on the dedicated CPU-GPU resources. Additional processing elements called [Edge Processors](https://github.com/waggle-sensor/edgeprocessor) and storage elements can be added to this basic construct. A collection of components that provide power, networking, and embedded interfacing capabilities complete the basic node. This node can be extended with sensors through standard Ethernet (POE), USB and other embedded protocols. 

<img src="https://raw.githubusercontent.com/waggle-sensor/.github/main/profile/Photo2.png" width="900"></br>
**Figure 3:** The Wild Waggle Nodes reference design is extensively tested for reliability across wide weather conditions, as well as EMI/RF compliance and electrical safety. The figure shows a node prototype undergoing various tests with some example sensors. Also shown is a wire frame that depicts various connectivity options of the node that provide sensor and instrument extensibility.
</br>
</br>
[**Waggle Blades**](https://github.com/waggle-sensor/waggle-blade) are standard commercially available blade servers intended for use in a climate controlled machine room, or extended temperature range telecom-grade blades for harsher environments. The Waggle platform supports blades with standard x86-64 CPUs and NVIDIA GPUs for AI@Edge computational jobs. As a Waggle Node, they run the same Waggle software stack as the Wild Waggle Node, and therefore can run edge jobs, report data, and be remotely configured.

[OS images and software for various waggle nodes can be obtained from our repos.](https://github.com/waggle-sensor/node-platforms)

## Software Cyberinfrastructure

The collection of code that runs on the nodes and server infrastructure are composed as easily combinable modules. Users can use the implementations provided by Waggle, or replace, modify, and extend as they see fit. Our design goal was to both quickly enable implementation of an end-to-end Waggle system, and also provide the flexibility for complete customization. Waggle consists of a collection of modular components which cover core infrastructure such as authentication, storage, data access, communication, app development SDKs, and management services. The [Waggle Edge Stack (WES)](https://github.com/waggle-sensor/waggle-edge-stack) includes Waggle services running on the Waggle nodes, as well as the AI/ML run-time libraries and tools. The core components for managing cybersecurity, certificate management, and managing system resources, such as power, memory, and cores are features implemented here. Separately, Waggle provides OS images that incorporate the above components for a few ARM64 and x86-64 computing systems (above mentioned WWN and WB). The Waggle server infrastructure is composed of 3 main subsystems - [Beehive](https://github.com/waggle-sensor/waggle-beehive-v2), [Beekeeper](https://github.com/waggle-sensor/beekeeper) and [Edge Code Repository (ECR)](https://github.com/waggle-sensor/edge-code-repository). Beekeeper is the resource that registers, authenticates, authorizes, configures, manages, and controls the Waggle nodes. It is the node cluster administrator. Next, Beehive offers bidirectional communication to the nodes, and data aggregation, storage and dissemination capabilities. And finally, the ECR is an application repository, similar to Android’s Play Store and iOS’ App Store. Users can submit their edge applications into ECR, which are then compiled, composed into containers, and profiled for intelligently scheduling them as jobs at the edge. Finally, in addition to scheduling the above jobs, the [Edge Scheduler (ES)](https://github.com/waggle-sensor/edge-scheduler) handles updates to the edge computing algorithms. Containerized user applications in ECR can be scheduled on nodes by users with their authentication token, including pushing configuration changes. Users can also submit local “jobs'' that can be scheduled and run on nodes immediately during the development cycle. The ES makes all configuration and job scheduling decisions, and queues up changes that can be pushed out to nodes when they connect to the Beehive. The Beekeeper, Beehive, ECR and ES are to be deployed as centrally available server resources on a platform (cloud, stand-alone server etc.) of user’s choosing. 

## Operation

Waggle nodes deployed in the field are extended with sensors, actuators, and other instruments to form a scientific instrument. Through real-time modification of the sensor’s parameters and by dynamically modifying how they process the data through edge codes, the Waggle nodes are essentially software-defined instruments. Users integrate their sensors through Linux OS drivers and any other software needed to interface with them. The nodes use TCP/IP based SSL encrypted communication to establish data (RabbitMQ and rsync-over-ssh implementation provided), control, and management (ssh and RabbitMQ) connections to Beehive, Beekeeper, and ECR. The nodes are designed to initiate communication with only the predefined server resources, with no communication network ports open for other network devices to communicate with them. This extremely locked-down design provides a high level of cybersecurity. The design also enforces a hub-and-spoke communication architecture. Nodes can exchange messages with each other through the Beehive, which can operate as a store and forward communication hub. 

The main focus of Waggle AI@Edge is user-accessible edge computing utilizing AI/ML applications. It provides three capabilities:

- A mechanism by which users can develop the edge algorithms on a node 
- A mechanism through which the algorithms can be verified and profiled for efficiency and system resource requirements 
- A mechanism through which users can submit an application to be executed on the nodes based on a set of conditions (environmental, time of the day, periodic etc.). 

Using the above capabilities, Waggle users create and deploy the software that defines their instrument. This software is written as plugins using the PyWaggle library, and composed into container images, before deployment in the nodes by the Edge Scheduler. 

The sensor and inference data generated by the user code in the nodes is aggregated and made available by Beehive through two mechanisms - a streaming service with API for real-time data, and a bulk download mechanism for curated archival data (common among science communities). Users can use the data for analysis, or further pipe them into global analysis applications on cloud or HPC services of their choosing using the Waggle data API. Users can then use their authentication tokens to modify the running and schedule parameters of their applications using the Edge Scheduler.

## Getting Started with Waggle

[Documentation](https://docs.waggle-edge.ai) on writing new AI@Edge applications, using data from apps and the Waggle software and hardware architecture are available and constantly updated. If you have questions about the research or would like to talk, <a href="https://docs.waggle-edge.ai/docs/contact-us"> please contact us! </a>

## Publications

## Projects Featuring Waggle


- [Sage](https://sagecontinuum.org/) - A national scale cyberinfrastructure using Waggle AI@Edge - [YouTube Link](https://www.youtube.com/watch?v=GF0jbkMPlTc)

- [Array of Things](http://arrayofthings.github.io/) -  [YouTube Link](https://www.youtube.com/watch?v=BHrsllHJHeo&t=1s)

- [NEON Science](https://www.neonscience.org/) Collaboration with Sage that uses Waggle AI@Edge - [YouTube Link](https://www.youtube.com/watch?v=xAyksDhoFs4)

- University of Chicago’s AoT (a fitness tracker for the city) Video - [YouTube Link](https://www.youtube.com/watch?v=BHrsllHJHeo)

- BBC Coverage on Array of Things - [Link](https://www.bbc.com/news/av/technology-32511363)

- [NSF](https://www.nsf.gov/) video that describes AoT, which was built on a previous generation of Waggle - [YouTube Link](https://www.youtube.com/watch?v=2BIbtB9NWsc)

- WIRED video on AoT - [YouTube Link](https://www.youtube.com/watch?v=JTaohgbskjE)


