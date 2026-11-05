# Music Recommender

### **Members**: 

Rafayet Hossain, Christian Rivera, Garrick Du

### **Project Description**:

Our project will develop an AI-based song recommendation system that predicts and recommends music based on a user's musical preferences and listening behavior. Rather than relying on a single recommendation method, the system will investigate whether combining multiple sources of information can produce more accurate and personalized song recommendations. 

We will be focusing on answering the question: 

Does combining collaborative filtering, audio-based features, sequential listening , content-based filtering, and reinforcement learning behavior improve song recommendations compared with using each recommendation method individually?

To test this, we can compare simpler recommendation methods with the individual models and our final combined model. We can evaluate the recommendations using metrics such as Precision@K, Recall@K, and NDCG@K. For reinforcement learning, we can also look at whether the system improves as it receives more feedback from the user.

For our final demo, a user could start with some listening history and receive a list of recommended songs. They could then listen to, skip, like, or dislike those recommendations. The system would use those interactions to adjust future recommendations, showing how the recommender can gradually adapt to the user's music taste.

### **Related Topics**:

* Collaborative filtering  
  * Recommending a song based on users with similar taste in music.  
* CNN  
  * Used to analyze audio representations such as spectrograms to extract musical features and identify similarities between songs.  
* Content filtering  
  * Used to recommend songs based on song characteristics   
* RNN/LSTM  
  * Used to analyze the sequence of songs being listened to by the user and recommending based on that sequence.  
* Reinforced Learning  
  * Adapting to any changes in the listeners music choices.

### **Team Member Roles and Contributions**:

Garrick: CNN \+ Content filtering  
Rafayet: Reinforcement Learning \+ Evaluation  
Christian: RNN/LSTM \+ Collaborative filtering

### **Dataset to be used**:

[Music4All](https://sites.google.com/view/contact4music4all) \- A music database of 109,269 songs. Includes 30-second MP3 audio clips, lyrics, and metadata for every song. Also contains a small listening history of 5.1 million (user, song, timestamp) records. We will use it to identify songs, raw audio for the CNN spectrograms, lyrics, and tags/genres for content filtering.

[Music4All-Onion](https://zenodo.org/records/15394646) \- An extension of Music4All that adds 26 precomputed audio, lyrics, tag, and video feature sets, and a much larger listening history of 252,984,396 [Last.fm](http://Last.fm) listening records from 119,140 users (from 56,512 songs). Features include musicnn, MFCC statistics, and Essentia descriptors. It is available as per-user play counts and as timestamped listening events. This will be the main training and testing data for collaborative filtering and sequence models. On its own it has no audio files, song names, or artists, so we join it to Music4All through the track ID.

Deezer API and iTunes Search API \- Free music track searching which includes full metadata on music, including 30-second audio samples. This will be used for the demo frontend, to search for songs and play previews.

### **Timeline**:

| Phase | Task | Expected Outcome |
| :---: | :---: | :---: |
| One  Week 1 | Organize and finalize dataset, clean data, set up roles through github repo | Overall to set a working data pipeline and repo |
| One Week 2 | Implement baselines and the evaluation framework | Baseline results and reusable evaluation code |
| Two Week 3 \- 4 | Start building the individual models  | Have each model evaluated on its own against baselines |
| Two Week 5 | Start wrapping up individual models and start working towards combining models | Start getting a basis of the combined model and an idea to combine it |
| Three Week 6 | Start adding the RL feedback loop, and start simulating user testing | To start seeing if the combined model is able to adapt and how the like/dislike/skip feature affects it |
| Three Week 7 | Run multiple different kinds of test, such as stress test and start producing reports | Finish up our testing and start gathering data towards report |
| Four Week 8 | Finish demo, and finish report | To be overall complete and organized and have a presentable project/report. |

### **Baselines:**

The baselines we will be working with are:

* Popularity Baseline  
  * Recommend most well played songs to every user

* Collaborative filtering  
  * Learns the users through song vectors from listening history, using an implicit-feedback loop

* Audio only model (CNN)  
  * Recommends songs similar to user’s listening history based on audio spectrograms

* Sequence only model (LSTM)  
  * Predict the next song from the order of the recent listens

* Combined Model  
  * Test the combined model with a RL feedback loop that adapts to likes/dislikes and skips

### 

### **Plans for final demo and other deliverables**:

The plans for the final demo start by having the user select and/or load a listening history, where the model is able to return a ranked list of recommended songs. The user is able to like, dislike, or skip the songs. Furthermore, the system is able to update it’s recommendations live time, using the feedback loop. We will show side-by-side recommendations from our base model towards our combined model for the same user, and see how changes differ from each algorithm to a combined algorithm for the same user. We will also show how the recommendations improve based upon how many feedback is given and accumulated. Lastly we will show code snippets to give a general view and scope of the tests we ran and the results from said tests.

The other deliverables include the github repository, the reports for both the combined model and individual models. As well as a short demo of the final product showcasing the features done or attempted.

**Plans for Evaluation**:

For our evaluation we plan on using metrics such as, precision, recall, NDCG, all of which @k, to measure the ranking quality. This is to allow us to get an overall estimate and hypothesis set up for our initial models. We will also incorporate baselines to test our models upon or compare them to, and run stress tests towards the models to see where the breaking point such as absurd user listening history amounts or wide variety of music listened to. Furthermore we will also data split, in the case where we test on a user’s old listening history and avoid the current and new listening history, to see how the AI fosters an established listening history, to a currently evolving one, off the same user. Lastly we look at the reports we did with the models, the test results and compare them to one another and then compare them to the combined model, to be able to see how the data differs, whether good or bad and see the type of adjustments we need to make. All of which will be shown with a demo and the code snippets to give the overall idea and the functions of the project. 

**Feedback:**  
Masking the algorithm from users so that there’s no bias. (Evaluation bias, order bias)  
We need funds from Google