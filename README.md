# Course Helper

## 1. Introduction
### 1.1 Motivation
Everything in today’s world is fast paced. People want instant access to information. Students,
who are getting more and more accustomed to the latest technologies, desire quick and easy
solutions. To keep up with this generation, educational institutions need to adapt and build
systems that can help students more effectively. Repetitive and time-consuming tasks such as
inquiries about the admission process or courses offered can be automated.
A smart solution to these problems would be a dialogue system for students where they can
interact with the system and find courses and faculty related information at ease. Having a
spoken dialogue system as opposed to the conventional searching through the portal would
actively engage the students in exploring a wide range of courses offered. This would also
highly benefit new and prospective students who are unfamiliar with the institution’s web portals.
### 1.2 Description of System
The system will be able to help users decide what courses to take in a semester. The system
will be able to look up different courses offered by the CISE department at UF, tell the location,
description, books required, and timing among other things. This will make the process of
searching for class related information easier. The user wouldn’t have to visit the university or
other websites in search of different types of information. The system would assume the
persona similar to that of a librarian/administrative assistant and be known as ‘Vicky’.
## 2. Description of System Architecture
### 2.1. Initial Prototype and Results
The results we received from the mid-semester round robin were very good feedback for us to
refine our system. We learned the following items:
- We needed to find a way for the system to recognize homophones - different ways of
name spellings. (Kristy, Cristie, etc.)
- We need to remember the context of the conversation.
- Ask follow up questions to give the user more options instead of just answers.
- Stop speaking when a user starts talking.
- Improve the intent recognition for some unexpected utterances.
- Handle unrecognized intents, and have a default answer instead of crashing sometimes.
All this feedback helped us refine our system to a better state for the following rounds of testing.
We were able to get the system to a more usable state and to a point where the users were
more comfortable using them, which we realized by the system usability scores. System
usability scores improved greatly after the first round robin testing.
### 2.2. Functionality Expansion and Refinement
We took the feedback from user testing to improve our system and then tested again. We did
this iteratively until we felt that we were at a good stage with the system. We underwent the
following process: developing, testing, refining. This allowed us to refine the system and test the
new iterations quickly as well.
### 2.3. User Studies
Initially on the first iterations of our system, we tested it ourselves with conversations and
utterances we thought would be more common. This allowed us to get a first prototype working
to be able to continue and do more testing. On the first round robin we were able to test our
system with the students in class and the results of both the conversation and our
questionnaires showed us we indeed needed to improve our intent recognition as well as our
speech recognition further. Before the final round robin of the semester we decided to test the
system with friends and family to see how people that were not involved in development would
interact with it. This allowed us to make modifications and improvements to the system. Finally,
we tested our system on the final round robin of the class where we actually received very good
feedback and our system was working as expected with only minor hiccups.
### 2.4. Final Architecture.
We built a mariadb database using information from ONE.UF/SOC
Speech Recognition and Synthesis was done using Google’s Speech API on Android. This app
was connected to the dialogue manager using a websocket connection. The dialogue manager
was built using python.
Packages used in the dialogue manager:
Wit.ai- library was used to connect to the Wit.AI system and get intent for the user input.
Mariadb- used to connect to the mariadb database.
difflib- package used to accurately recognize words that were close to the ones in our database.
## 3. Final Evaluation Round Robin
### 3.1. User Interactions
Overall, we tested the system with 11 users on the first round robin in the middle of the
semester and with 10 people on the second round robin at the end of the semester. That gave
us a total of 21 users for both round robins. The average length of the interaction came out to be
4.2 minutes (254.8 seconds) for the final evaluation.
### 3.2. Descriptive Statistics
Dialogue Turns
Words per Utterance
SUS Scores
### 3.3. Qualitative Reflections
We first noticed some issues with the system on the mid semester round robin. We knew the
system was not perfect at the time, but we did discover some issues that we had not thought of
at first. The users gave us valuable feedback that we later used to improve our system. We
noticed that our system had many flaws. To name a few, it had issues recognizing names of
classes when it was not said the exact way it was written, it did not ‘remember the context’
correctly, we were not ‘handling unhappy paths’ very well so the system was crashing often. It
was also very clear to us that our system was not performing the best since our calculated SUS
Score was 59.8. We took the feedback we received from the mid-semester round robin and
made changes and improvements accordingly for the final round robin.
On the final round robin, we received very good feedback from our users. It was clear that we
had improved the system a lot and this was reflected in our SUS Score. It went up from the
previous 59.8 to an 84.3 which was great. We had minor issues- Users wanted the bot to ‘be
better on recognizing intents’ and ‘recognize me when I ask "xxx course sounds interesting, can
I learn more about that”’ but the users were happy with the functionality and the system in
general. Suggestions were along the lines of ‘The system could maybe recommend classes if
you are not sure what to say’ and building a ‘Better User Interface’. One of our classmates even
mentioned ‘Honestly, this was the best system I have tested in this class so far. Good job!’ in the
survey comment box. We did not have enough time to complete the stretch goals as we later
realized that some of our stretch goals were going to be very difficult to implement like linking
with one.uf and canvas.
## 4. PARADISE Model
For our PARADISE-style model we decided to analyze intent recognition and automatic speech
recognition errors since when looking at our logs those were the two variables that usually led to
an end in the conversation and the user having to start over. We performed a linear regression
with these variables against the SUS score that each of the users reported to see if they are a
good predictor of a good or bad user experience with our system. The following are the results.
Coefficients Standard Error P-value
Intercept 89.1951683 1.2678258 3.0824E-11
Intent_Error -0.1004343 0.66379596 0.88400481
ASR_Error -2.1701954 0.56301002 0.00625482
From the table above we can see that even though we thought intent error would be a predictor
of low SUS Scores it turns out that it is not. However, speech recognition errors did turn out to
be a good predictor of good satisfaction scores for our system.
