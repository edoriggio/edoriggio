# CODI – Conversation Disentanglement Microservice

CODI is an accessible and user-friendly REST microservice that can automate the disambiguation of a set of instant 
messages to form conversations by leveraging state-of-the-art machine learning algorithms.
<br/> <br/>

![](https://raw.githubusercontent.com/USIREVEAL/CODI/main/docs/assets/codi_ui.png)
*Messages (left) and color coded conversations (right) with predicted disentanglement (arrows)*
<br/> <br/>

## Abstract

Modern instant messaging applications (e.g., Gitter, Slack, Discord) provide users with real-time communication means.
Developers use them for collaborative development, to ask for code reviews, and to have software-related discussions.
In short, a (potential) treasure trove for program comprehension. However, as with any high-throughput "chat
application", messages interleave, leading to concurrent conversations. Associating messages to conversations is called
conversation disentanglement, a useful and necessary pre-processing step to analyze datasets of instant messages.
Although various conversation disentanglement algorithms have been proposed, it is cumbersome to set up proper execution
environments and hard to ensure input data format consistency, calling for better practices and tool support.
<br/> <br/>

We present CODI, a RESTful API micro-service and web interface for conversation disentanglement. It provides an easy way
to disentangle conversation transcripts with pre-trained models or to train new ones on custom datasets, features, and
hyper-parameters. CODI allows validation of manually annotated conversations, checks input consistency, and computes
performance metrics. It achieves state-of-the-art performances on transcripts of IRC, Slack, and Discord conversations.
We show how CODI can provide a significant improvement to reusability (and replicability) of research results, while
reducing the efforts and potential mistakes due to configuration, setup, and execution.
<br/> <br/>

Both the [report](https://github.com/edoriggio/edoriggio/blob/master/thesis/report.pdf) and the
[poster](https://github.com/edoriggio/edoriggio/blob/master/thesis/poster.pdf) of my thesis, from which the paper was
written from, can be viewed on my GitHub page.
<br/> <br/>

## Publications

CODI was presented and used in the following scientific research papers:
<br/> <br/>

 - E. Riggio, M. Raglianti and M. Lanza, "Conversation Disentanglement As-a-Service," 2023 IEEE/ACM 31st International
Conference on Program Comprehension (ICPC), Melbourne, Australia, 2023, pp. 59-63, doi: 
[10.1109/ICPC58990.2023.00018](https://doi.org/10.1109/ICPC58990.2023.00018).
