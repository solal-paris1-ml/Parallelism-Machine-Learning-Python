# ENS_DREEM_CHALLENGE

I Presentation of the project

1.1 ENS Data Challenge: Entreprise Dreem

All the elements relating to our subject have been made available by the data challenge platform Challengedata.ens. 
Like the Kaggle platform, this platform provides easy access to supervised Machine Learning datasets, this to
educational ﬁns. The data sets being suﬃsamment small so that they can be studied on standard machines, while 
maintaining interesting characteristics on real data.

For this project, we have chosen to take an interest in a challenge proposed by Dreem, a startup specialized in
sleeping problems. Their product, the Dreem headband, aims to improve the quality of sleep of individuals by stimulating certain
parts of the brain during diﬀérentes sleep phases. The object of study of our project is eﬀectue on recordings of 
10 seconds of brain signals characteristic of deep sleep phases called "slow oscillation". The measurement as well as 
the recording of these waves, symbolizing a strong cerebral activity, is carried out by the dreem band in the form of 
of EEG (electroencephalogram).

Our goal is to use the database at our disposal to predict whether a slowoscillation will be followed by another one during
the second following the ﬁn recording, in sham condition (ie: without headband stimulation). We place ourselves here in sham condition.
(without any simulation)

1.2 Principles of parallelism

Parallelism is a computer technique for using multiple processors to process operations in a way that 
Simultaneous: The aim is that all these operations are carried out with as little processing time as possible. 
This technique differs from the traditional method known as "sequencing".
tielle". The operations are processed successively and
the execution time remains higher than with parallelism.
Parallelism can be applied using multiple processors. The problem in question is subdivided into several parts 
that can be resolved in competing ways. Each part is then transformed into a series of instructions being
executed by the diﬀérents processors. Parallelism allows : - a time saving - a processing of more complex problems, 
which would be difficult to deal with with a simple sequential approach (processing large data sets) - not necessarily to
use local resources

A ranking of diﬀérentes machines was proposed by Flynn in 1966: 

- SISD: There is only one computing unit that has access to one piece of data at a time. This is an example of the sequential approach. 
and there's no parallelization. 

- MISD: Multiple processors process the same data but apply multiple instructions and diﬀérentes. 

- SIMD: The same instruction is applied simultaneously, thanks to several computing units, on several data to obtain results.
diﬀérents. -

- MIMD: Multiple machines where the processors have their own memory and do not have access to each other's memory. The processors
are, however, connected on the same network. The diﬀérentes machines can coincide with the parallelism except the first one. In addition
to this, there is the choice of Multiprocessing or Multithreading (even if empirically both are complementary).
Multiprocessing consists in adding several processes to increase the response and calculation speed of the system. 
The separation of the processors allows a joint management of resources plus eﬃcace insofar as a process, once subdivided, is less
prone to clog the device on which it eﬀectue a task (Notion of limited CPU). 
There are 2 subcategories of Multiprocessing which are : Symmetrical Multiprocessing and asymmetrical Multiprocessing. 
Symmetrical Multiprocessing is the fact that the processes operate freely and unconstrained in the system. 
Asymmetric Multiprocessing models a subordinate relationship between processors. One processor can forbid another to perform certain 
operations, so there is a division of labour. Multithreading consists in the multiplication of "threads", task, for a process. 
This creation of threads is more eﬃcace than an additional creation of processes that exhausts resources and is time-consuming. 
Increasing the number of tasks increases the level of system response to the extent that a task becomes slower and the process can 
continue to run.

