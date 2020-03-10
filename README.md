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

Then comes the choice of model. The synchronous model or the asynchronous model. In the synchronous model there is a dependency between tasks, so you have to wait for the ﬁn completion of a task before moving on to the next one (First-In-First-Out). On the contrary, the asynchronous model allows to pass to another task even if the task eﬀectuéeprécédemmentresteencoursderéalisation.Each machine has its own memory and acts independently.

1.3 Application on Machine Learning algorithms 

In order to be able to eﬀectuer predictions about this challenge, we will use diﬀérents Machine Learning algorithms. Here we place ourselves in a problematic of classiﬁcation, our labels in exit can take the values :
Labels = 0,1,2
0 = No oscillation in the following sec. 
1 = A weak oscillation in the following sec.
2 = a strong oscillation in the following probe

Algorithms used for Machine Learning applications can be "heavy" and have a large memory footprint. 
for "standard" computer systems. Even more so when confronted with large data sets, such as the
case here.
Our training data is from :
Xtrain = 261,634 (obervations) for 1261 variables, i.e. 261.634 x 1261. 
Ytrain = 261.634 (observations) i.e. 261634 x 1

The first 11 variables characterize each of these recordings (sleep stage, amplitude of the oscillation, etc.). 
current oscillation, duration of the current oscillation etc.) . 
The next 1250 columns correspond to the 10 sec of EEG recording for each observation (1250 points, i.e. 
125 columns/sec). Our Xtrain before processing for a 2.4 GB (2,408.14 MB) memory footprint (on import) 
and 2.13 mo for our Ytrain.
Moreover, even if these algorithms are relatively simple to implement, the method we will use here to solve our
problematic will prove to be very time-consuming. The cross validation as well as the split between training data and
validation (or test) will considerably increase the execution time of our program. Similarly, it is not recommended 
to train our data on a single model, because if eﬀectivement an algorithm is efficient on a set of data, nothing can be done.
says it will be on data never before encountered. So we've trained several models and applied to them the 
called "cross validation".

Here the parallelization will prove to be a determining factor aﬁn to optimize the speed of execution of our code. In eﬀet apply 
these diﬀérentes procedures on our processors allows us to save a considerable amount of time and reduce the memory footprint of 
our initial dataset. In the rest of this document we will show the importance of the time/memory saving realized by using
these methods of multiprocessing and multhreading.


