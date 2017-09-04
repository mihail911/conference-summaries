# Notes from SIGDIAL/SemDIAL 2017


## Papers

### Keynote 1 (Oliver Lemon) Finding the goldilocks zone
* data = porridge ?  what is just right?
* naturalness
	* process real spontaneous dialogue
	* not too natural, with los of boring utterances
* size
	* learn real variations in human behavior
	* data efficient systems

* natural/synthetic data
	* train on synthetic, test on real data
	* 100% on bAbI task 1
	* bAbI small vocab, small interaction structures
	* restarts, repairs, hesitations, fragments
	* how well can such models handlge content-relevant natural dialogue phenomena
	* need to learn targeted semantic updates
	* babi+ dataset -- bit.ly/babi_plus
	* 21% of user turns have a repair (compared to 40% in typical data)
	* repair within single turn -- no long distance 
	* performance goes from 100% -> 28%
	* if trained on babi+ performance goes to 53%
	* increase data: 100000 performance goes to 80.5%

* big data questions
	* some natural phenomena are in long tail so need a lot of data
	* why not use linguistic theories to handle more natural phenomena?
	* generalize around small amounts of seed data

* data efficiency
	* dynamic syntax and type theory with records
	* how does memN2N compare to grammar-based models?

* handling variation
	* dialogue grammar handles syntactic and interactional variation
	* compute semantically equivalent dialogues

* ds-ttr dialogue model
	* process word-by-word
	* bidirectional: parse and generate in same model
	* split utterances, fragments, ellipsis, self-other-repair

* burchak data

* can ds-ttr parse babi+?
	accuracy of semantic parsing babi/babi+ both get 100%

* "bootstrapping incremental dialogue systems from minimal data"

* BABBLE method
	* parse seed dialogues
	* MDP actions are words
	* end-to-end systems
	* leads to generalization (after starting with a seed dialogue)

* Recap
	* can ML methods capture structure dialogue variation?
	* can if they have enough data
	* use formal grammars/semantics
	* not everything needs to be learned from data
	* approach: combine reusable abstractions (e.g. grammars) with learning from data and learning from data

* Alex challenge semi-finals
	* 200 ratings per day
	* socialbots deployed to all US customers

* Noisy and sparse user feedback signals
	* some dialogues are over 100 turns long
	* lots of ratings gathered

* Big & Noisy bot data
	* Reddit/Twitter/Movie subtitles, daytime TV transcripts
	* often inappropriate 

* Approach
	* Explicit rules to catch inappropriate situations
	* Then allow statistical bots to do their work
	* Train statistical bots on clean data (news)
	* can never 100% avoid potentially offensive turns in context if using statistical bots

* Heriot-Watt Alexa system
	* Ensemble model
		* rules, retrieval, seq2seq + ranker
	* Features: 3 turns of context
	* Maintain coherence

* Progress?
	 * real user data/feedback
	 * BUT WHAT ABOUT PLANS, CONSTRAINTS, NEGOTATION, REASONING

* Explainable AI
	* systems don't really know what they're talking about


### Talk after mine
* Get slots and KB queries correct are required and hard
	
* Contributions
	* tackle OOV and KB query problem
	* domain-general dialog models

* adapted from delexicalization process

* type + index
	* type: type of entity
	* index

* entity-index
	* is not associated with entity value, but solely on order of appearance
	* computer mostly corroborate entities from users

* Domain general model
	* one example usage is out-of-domain handling

* Chat data for better OOD recovery
	
* Tic-toc chatbot data

* http://skylar.speech.cs.cmu.edu

* dialport

* delexicalization difficult for large datasets

### Sample-efficient Actor-Critic
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

* RASA

* Online learning and transfer for user adaptation in dialogue systems

* Automatic measures to calculate verbal alignment in human-agent interaction
	* ARIA VALUSPA
	* multimodal interaction
	* adaptation
	* communication accommodation theory
	* interactive alignment theory

	* studying verbal alignment
		* speakers reuse lexical as well as syntactic structures from previous utterances

	* take into account socio-emotional behavior of user -- "social glue"
	* adaptation without the need of extensive user profiling
	* automatic building of expression lexicon
		* surface text attern that has been produced by both speakers in a dialogue


# Keynote 2 - Empowering Human-Robot Dialogue by Affective Computing Research

* nonverbal communication
* enrich useful functions of computers to shape meaning of nonverbal behaviors

## Recognition of social cues
* speech, facial expressions, gaze, postures, body movements (social cues)
* interpersonal attitudes, display of social engagement (interaction patterns)

* Facial features
	* recognize and generate facial expressions

* Features for Vocal Emotion Recognition
	
* Non-Ekmanian Emotions
	
* Accuracy drops with naturalness
	* systems in lab conditions perform poorly in less controlled scenarios

* Interactive Real-life applications
	* Modalities need to be synchronized
	* handling of noisy and corrupted data
	* Processing in real-time

* Contextualized Analysis
	* Gender-specific information
	* dialogue behavior of virtual agent/robot
	* learning context using (B)LSTM

* Multimodal Fusion
	* natural interaction pepole draw on strategies to express emotion

* Event-based Fusion
	
* Synchronous Fusion
	* characterized by consideration of multiple modalities within same time frame

* Asynchronous Fusion
	* refer to past time frames with help of some kind of memory support

* Event-based fusion
	* Take into account temporal relationships between channels and learn when to combine information
	* Move from segmentation based process

* SSI Framework
	* Open source framework for developing affective computing applications

* Generating Social Cues by the Robot
	
* Nonverbal signals 
	* expression emotional states
	* express attitudes

* Expression of Action Tendencies
	* Action tendencies for NAO used body movement, posture, eye color and sound

* Generation of Facial Expressions
	* FACS -- used to generate and recognize facial expressions

* Empathic Listener
	* Perception -> Understanding -> Internal reaction -> External Reaction -> Reaction

* Measurement of Engagement between Human + Robot

* Mutual + Directed Gaze

* Gaze-based Interaction
	* Object grounding
	* Social Grounding
	* Turn management

* Automated Interruption Detection
	

# Turn-taking in Dialogue
* turn-taking is context-dependent

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

# Attentive Listening System with Backchanneling, response generation

* Attentive listening
	* short interjections to stimulate more conversation

* Backchanelling
	* prediction of backchannel timing and form
	* counseling corpus used to train models because of many examnples of attentive listening

* Subjective Experiment 
	* naturalness
	* tempo
	* empathy
	* understanding
	* willingness to talk again
 	* correct timing is more important than correct form

* Statement response generation
 	* generate responses based on focus words extracted from speech of user

* Turn-taking

# Perceptual grounding as interaction

* Connect language, perception, and action

* Grounding
 	* feature selection is dynamic, dependent on feature richness of perceptual scene
 	* task that an agent is engaged with

* Spatial Descriptions

* Scene geometry and spatial templates

* Effect of context on grounding
 	* does perceptual context affect grounding of descriptions in spatial templates
 	* what happens with in compositional phrases

* http://www.dobnik.net/simon/semantic-o-matic


# Challenging Neural Dialogue Models with Natural Data

* incrementality, data-efficiency

* incremental phenomena appear without respecting boundaries of a turn or a sentence

* are dialogue systems ready for real-world data
	* word-by-word incremental processing
	* disfluencies

	* domain specific data is expensive

* restarts, corrections, hesitations

* error analysis? which mix-ins are most problematic?

* why train accuracy so low?

* impractically large datasets
*  closeness between train & test sets not guaranteed

* computational models of dialogue processing as source of bias/prior

* more modularity in DL architectures informed by these

* dynamic syntax and type theory with records

* how slow?


# E2E dataset

* so far limited to small delexicalized datasets
* more challenging -- more sentences per one MR,
* longer sentences
* collected by crowdsourcing 

# Modelling Protagonist Goals ...
* Goal
	* infer from context whether desired fulfilled or not

* Contributions
	* https://nlds.soe.ucsc.educ/DesireDB


# Role of Conversation Context for Sarcasm Detection
* Isn't all sarcasm context dependent?

# ...
* lexical acquisition through implicit confirmation
* trying to acquire ontological categories of unknown terms through implicit confirmation

# Role of Natural Language Understanding in Chatbots
* Microsoft LUIS
* IBM Watson Conversation
* API.ai
* wit.ai -- batch import not working for external data
* Amazon lex -- no batch import
* RASA

* sebischair/NLU-Evaluation-Corpora (github)

## Themes

* LUIS (Microsoft)