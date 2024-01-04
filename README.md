# t_swift_and_text_mining
## Introduction and Hypothesis
When we think of the words “heartbreak”, “love”, “growth”, “shake”, and “men”, our automatic first thought is Taylor Swift, the queen of pop. Seeing from the giant success of her eras tour, Taylor Swift creates music that resonates with a universal audience, and has been doing this since her debut album in 2006. Not only is Taylor Swift well-known for her songwriting skills, but she is also known for her ability to socially and culturally influence her fanbase through her music. There is a reason why people listen to Taylor Swift’s songs when they break up or listen to the song “22” when they turn 22. Now in 2023, her music has evolved with her, with each album representing a different “era” of her life. Each era has a different sound and feel, and we wanted to analyze how her sound has changed by examining the themes in her music. Her music addresses many topics that young women can relate to, spanning from heartbreak, love, etc., so we wanted to analyze these main themes to see where her influence mainly lies.

There have been many conflicting opinions on Taylor Swift’s music over the years, with some saying that her music is repetitive in its nature, while others saying that it covers many different feels and topics. We will investigate this conflict in our analysis below.

Hypothesis: Our overall hypothesis is that Taylor Swift's music stays consistent over time, however each era varies with Taylor Swift's feelings and themes. There will be individual hypotheses for each method we used below.

## 2. Data and methods
Data Description: We read in Taylor Swift song lyrics and spotify data from a csv that adashofdata created and housed on a github repository: https://github.com/adashofdata/taylor_swift_data. We checked all her files and checked the lyrics and song names and confirmed that this data was 1) better than any Kaggle Dataset that we found 2) produced the same results as we would if we were to scrape Spotify for every Taylor Swift song.

While adashofdata has way more spreadsheets then we needed, such as we ruled out needing Taylor_Swift_Set_List_Data which hosts a set list from her six tours, and Taylor_Swift_Words, which houses a breakdown of her lyrics into words.

We also reviewed what adashofdata had done with the data, which she used to create a blog post: http://adashofdata.com/2023/03/01/a-data-scientist-breaks-down-all-10-taylor-swift-albums-the-extended-version/, a video virtually a summary of her blog post: https://youtu.be/ZNFms8sUbTw, and a few Reddit threads with the same findings: https://www.reddit.com/r/TaylorSwift/comments/11g46c5/all_the_colors_mentioned_in_each_taylor_swift/, https://www.reddit.com/r/TaylorSwift/comments/11f6xa8/taylor_swift_writes_a_song_in_every_key_on/, and https://www.reddit.com/r/TaylorSwift/comments/11mv3sn/taylor_says_she_imagines_writing_her_songs_with_3/. AdashofData's findings did not align with our discussion as below we look at how her song lyrics can assist in the prediction of which Year the song is released and whether we can classify a song as High Energy or not. Adashofdata's findings are indeed interesting and we support you if you wish to understand more about seasonality of Taylor Swift, which Days of the Week she talked about, swear words and more!

Limitations of the data include the fact that we decided not to include any songs that Taylor Swift re-recorded: Fearless(Taylor's Version), Red(Taylor's Version), Speak Now (Taylor's Version), etc. This was due to the overlap and the fact that we desired to see if her music has potentially evolved or changed since starting her career and thus re-released songs would have potentially hindered our analysis.

Other pitfalls include our data reviews 133 songs below, but songs that she created for another Artist/TV Shows/etc and lawsuits that occurred that made artists place her name on the writers list were not included. Also overlapping songs where she re-recorded with a featured artist were not included as well to avoid repetition.

The data was extremely clean and thus if you search up the lyrics for certain lyrics they will not include quotations around words that the author says, but due to cleaning ours does.

Here are descriptions of the different rows in our dataset from the Spotify Developer API (https://developer.spotify.com/documentation/web-api/reference/get-audio-features):

Album: The name of the Taylor Swift album
Song Name: The name of the Taylor Swift song
Lyrics: The lyrics from each song
Danceability: "How suitable a track is for dancing based on a combination of musical elements including temp, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable"
Energy: Perceptual measure of intensity and activity. Energetic tracks are fast, loud, and noisy.
Key: The key which the track is in. (0 = C, 1 = C#/Db, 2 = D...)
Loudness: Overall loudness of a track. Quality of sound that is the primary psychological correlate of physical strength (amplitude)
Mode: Modality (major or minor) of a track.
Speechiness: Presence of spoken words in track. More exclusively speech-like the recording is the closer it is to 1.
Acousticness: A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic.
Instrumentalness: If the track contains no vocals - "ohh" and "ahh" sounds are treated as instrumental in this context and rap or spoken word tracks are clearly "vocal." The close instrumentalness is to 1 greater likelihood track contains no vocal content.
Liveness: presence of an audience in the recording. Higher represents if the track is live.
Valence: 0.0 to 1.0 musical positiveness conveyed by a track.
Tempo: Overall tempo of a track in beats per minute.
Duration: How long the duration of the song is in milliseconds.
Time signature: How many beats are in each measure. The time signature ranges from 3 to 7 indicating time signatures of "3/4", to "7/4".
Lyrics Length: The length of each song's lyrics.
To analyze our data, we used the methods of sentiment and frequency analysis, song/lyric length (number of words in lyric vs. time) analysis across eras and energy level anylsis of songs, bert classification, and topic modeling. We believe that these are valid methods to analyze our data because they can help reveal how Taylor Swift's music has changed over time. Sentiment and frequency analysis will allow us to see how the sentiment in Taylor Swift's songs has changed. Song/lyric length analysis across eras and energy level anylsis of songs will help us track how much Taylor Swift's music sound and length has changed. BERT classification will allows us to see how lyrics can predict what album they are from. Topic modeling will allow us to see how the themes/topics within Taylor Swift's songs have changed over eras.
