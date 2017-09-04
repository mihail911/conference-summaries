# Notes from SIGDIAL/SemDIAL 2017


## Oral Presentations

### Keynote 1: Challenges for Data-driven Dialogue Systems: Finding the Goldilocks Zone for Conversational Data
* Guiding question: What amount and type of data is "just right" for dialogue research?
* Some data characteristic considerations:
	* Naturalness
		* Can we process real, spontaneous dialogue with all its disfluencies, interjections, cross-talk, irregular starting and stopping?
		* Synthetic data is not too natural, with lots of boring utterances
	* Size
		* How much data do we need to learn real variations in human behavior?
		* Very difficult to build huge-scale corpora so how can we build data-efficient systems?

* Studies in models trained on natural and synthetic data
	* What can we expect if we train on synthetic but test on real data?
	* What does it mean to get 100% on bAbI task 1 (issuing API appropriate calls)?
	* Structure of bAbI: small vocab, small interaction structures
	* What about restarts, repairs, hesitations, and fragments, which are typical phenomena in human dialogue?
	* How well can such models handle content-relevant natural dialogue phenomena?
	* need to learn targeted semantic updates
	* Present babi+ dataset (<bit.ly/babi_plus>), a synthetically-enhanced dataset
		* 21% of user turns have a repair (compared to 40% in natural data)
		* repair within single turn -- no long distance dependency
	* Now model that achieves 100% performance on bAbI task 1 goes to 28% when tested on bAbI+
	* if trained on babi+ performance goes to 53% when tested on bAbI+
	* When data increased to 100000 (from 1000), performance goes to 80.5%

* Big Data Questions
	* Some natural phenomena are in long tail so need a lot of data to accurately 
	* Why not use linguistic theories to handle more natural phenomena?
	* We can then generalize around small amounts of seed data

* Data Efficiency
	* Use dynamic syntax and type theory with records (ds-ttr)
	* How does memN2N compare to grammar-based models?

* Handling Variation
	* A provided dialogue grammar handles syntactic and interactional variation
	* Then must compute semantically equivalent dialogues

* DS-TTR dialogue model
	* Process word-by-word
	* Bidirectional: parse and generate in same model
	* Can handle split utterances, fragments, ellipsis, self-other-repair
	* [Bootstrapping incremental dialogue systems from minimal data](https://arxiv.org/pdf/1612.00347)
	* *How efficient is this processing?*
	* Can ds-ttr parse babi+?
		* accuracy of semantic parsing babi/babi+ both get 100%

* [Burchak Data](aclweb.org/anthology/W17-2001)

* [BABBLE method](https://sites.google.com/site/hwinteractionlab/babble)
	* parse seed dialogues
	* MDP actions are words
	* end-to-end system
	* leads to generalization (after starting with a seed dialogue)

* Recap
	* Can ML methods capture structure dialogue variation?
		* can if they have enough data
	* Use formal grammars/semantics 
	* Not everything needs to be learned from data
	* Approach: combine reusable abstractions (e.g. grammars) with learning from data 

* Alexa challenge semi-finals
	* <https://developer.amazon.com/alexaprize>
	* Systems deployed live periodically to interact with real US customers
	* 200 ratings per day
	* Provided noisy and sparse user feedback signals
		* Some dialogues are over 100 turns long
		* Lots of ratings gathered

* Big & Noisy bot data
	* Reddit/Twitter/Movie subtitles, daytime TV transcripts
	* Often inappropriate as data sources


* Heriot-Watt Alexa system
	* Ensemble model
		* rules, retrieval, seq2seq + ranker
	* Features: 3 turns of context
	* Maintain coherence
	* Approach
		* Explicit rules to catch inappropriate situations (blasphemy, calls for help, etc.)
		* Then allow statistical bots to do their work
		* Train statistical bots on clean data (news)
		* can never 100% avoid potentially offensive turns in context if using statistical bots

* Has the dialogue community made progress?
	* Abundance of data sources provide real user data/feedback
	* **BUT WHAT ABOUT PLANS, CONSTRAINTS, NEGOTATION, REASONING?**
	* Goal to achieve explainable AI
		* Systems don't really know what they're talking about


### [Generative Encoder-Decoder Models for Task-Oriented Spoken Dialog Systems with Chatting Capability](https://arxiv.org/abs/1706.08476)
* Problem: Getting slots and KB queries completely correct is necessary but hard
* Contributions
	* tackle OOV and KB query problem
	* domain-general dialog models
	* Method adapted from delexicalization process


* entity-index
	* is not associated with entity value, but solely on order of appearance
	* computer mostly corroborate entities from users

* Domain general model
	* one example usage is out-of-domain handling
	* Chat data for better out-of-domain recovery

* Centralized dialogue service
	* [Dialport](http://skylar.speech.cs.cmu.edu)
	* delexicalization difficult for large datasets

### [Sample-efficient Actor-Critic Reinforcement Learning with Supervised Data for Dialogue Management](https://arxiv.org/abs/1707.00130) 
* Dialogue Policy
	* RL
		* learn policy online with real/simulated users
		* poor performance in early training stage
	* SL
	* Combine best of both worlds

* Deep RL
	* Actor-critics
	* slow learning and cold start

* On-policy learning
	* behavior policy



### SIGDIAL/SEMDIAL Joint Session on Negotiation Dialog

* Automatic measures to calculate verbal alignment in human-agent interaction
	* multimodal interaction
	* adaptation
	* communication accommodation theory
	* interactive alignment theory
	* studying verbal alignment
		* speakers reuse lexical as well as syntactic structures from previous utterances

	* take into account socio-emotional behavior of user -- "social glue"
	* adaptation without the need of extensive user profiling
	* automatic building of expression lexicon
		* surface text pattern that has been produced by both speakers in a dialogue


### Keynote 2: Empowering Human-Robot Dialogue by Affective Computing Research

* Question: How can we effectively study and use nonverbal communication
	* allows us to enrich useful functions of computers to shape meaning of nonverbal behaviors

* Recognition of social cues
	* speech, facial expressions, gaze, postures, body movements (social cues)
	* interpersonal attitudes, display of social engagement (interaction patterns)

* Facial features
	* Can we recognize and generate facial expressions?

* Features for Vocal Emotion Recognition
	
* Non-Ekmanian Emotions
	* wish to move beyond only studying [Ekman's 6 universal emotions](https://people.ece.cornell.edu/land/OldStudentProjects/cs490-95to96/HJKIM/emotions.html)	

* Accuracy drops with naturalness
	* systems in lab conditions perform poorly in less controlled scenarios

* Interactive Real-life Applications
	* modalities need to be synchronized
	* handling of noisy and corrupted data
	* processing in real-time

* Contextualized Analysis
	* Gender-specific information
	* dialogue behavior of virtual agent/robot
	* learning context using (B)LSTM

* Multimodal Fusion
	* natural interaction people draw on strategies to express emotion

* Event-based Fusion
	* Take into account temporal relationships between channels and learn when to combine information
	* Move from segmentation based process
	
* Synchronous Fusion
	* characterized by consideration of multiple modalities within same time frame

* Asynchronous Fusion
	* refer to past time frames with help of some kind of memory support

* [Social Signal Interpretation Framework](https://hcm-lab.de/projects/ssi/)
	* Open source framework for developing affective computing applications

* Some considerations for affective interactions with robot
	* Generating Social Cues by the Robot
	* Nonverbal signals 
		* expression emotional states
		* express attitudes
	* Expression of Action Tendencies
		* Action tendencies for NAO used body movement, posture, eye color and sound
	* Generation of Facial Expressions
		* Facial Action Coding System -- used to generate and recognize facial expressions
	* Empathic Listener
		* Perception -> Understanding -> Internal reaction -> External Reaction -> Reaction
	* Measurement of Engagement between Human + Robot
	* Gaze-based Interaction important for
		* Object grounding
		* Social Grounding
		* Turn management

	


### [Towards a General, Continuous Model of Turn-taking in Spoken Dialogue using LSTM Recurrent Neural Networks ](www.sigdial.org/workshops/conference18/proceedings/pdf/SIGDIAL27.pdf)
* Observation: turn-taking is context-dependent
* Towards a Model that is
	* General
	* Continuous
	* Predictive
	* Probabilistic

* Features
	* voice activity
	* pitch
	* power
	* spectral stability
	* POS (audio?)


### [Attentive listening system with backchanneling, response generation and flexible turn-taking](www.sigdial.org/workshops/conference18/proceedings/pdf/SIGDIAL16.pdf) 

* Examples of attentive listening
	* short interjections to stimulate more conversation

* Backchanelling
	* prediction of backchannel timing and form
	* counseling corpus used to train models because of many examples of attentive listening

* Subjective Experiment 
	* Metrics
		* naturalness
		* tempo
		* empathy
		* understanding
		* willingness to talk again
	 	* correct timing is more important than correct form

* Statement response generation
 	* generate responses based on focus words extracted from speech of user


### [The E2E Dataset: New Challenges For End-to-End Generation](https://arxiv.org/abs/1706.09254)
* Problem: So far NLG limited to small delexicalized datasets
* This dataset is more challenging -- more sentences per one MR,
* longer sentences


### [Modelling Protagonist Goals and Desires in First-Person Narrative](https://arxiv.org/abs/1708.09040)
* Goal: infer from context whether desired fulfilled or not
* Contributions
	* https://nlds.soe.ucsc.edu/DesireDB


### [The Role of Conversation Context for Sarcasm Detection in Online Interactions](https://arxiv.org/abs/1707.06226)
* Use Twitter exchanges to assess sarcasm present
* Investigate a variety of LSTM networks (with attention) to incorporate sentence-level attention on context and response
* attention weights indicate
	* semantic coherence between context and reply
	* incongruity between context and reply
	* able to pick up on certain word/phrase-level sarcasm markers


### [Evaluating Natural Language Understanding Services for Conversational Question Answering Systems](www.sigdial.org/workshops/conference18/proceedings/pdf/SIGDIAL22.pdf)
* Microsoft LUIS
* IBM Watson Conversation
* API.ai
* wit.ai -- batch import not working for external data
* Amazon lex -- no batch import
* RASA
* Results
	* LUIS on top, RASA in 2nd place
* github.com/sebischair/NLU-Evaluation-Corpora 



### Demos
* Dialport 
	* https://skylar.speech.cs.cmu.edu/master/PortalSite/about.html
	* centralized platform for interacting with variety of dialogue models
	* <https://arxiv.org/abs/1606.02562>
	* great idea and about time someone did this!
* Demonstration of interactive teaching for end-to-end dialog control with hybrid code networks
	* training dialogue agents using hybrid code networks + interactive learning paradigm
	* train from a few supervised datasets
	* very similar to wit.ai
	* great UI provided and I think this paradigm can help build dialogue agents from scratch that can probably handle 70-80% of basic dialogue stories

### Panel/Discussion for Special Session on Natural Language Generation for Dialogue Systems 
* Purely black box end2end systems will never fly in a corporate setting because someone has to explain wth is going on to a superior
* Models that can handle longer term context still very elusive (3+ turns)
* One-shot learning and other data-efficient methods important -- annotated data often lacking
* clean data also often lacking which limits achievable quality of models
* Improvement from 2000 is ASR and large KBs
* Likert scales are pretty bad
* Inadequacy of evaluation metrics is ok for now since it's still early days
	* I personally don't agree with this point; I think it's never premature to know whether what you're doing is off the mark
