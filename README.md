# Spotify Data Analytics Project - Group 8
###### *Authors: Alex Qian, Dmitry Shlykov, Patrick Scerri, Jason Chin, Joe Diaz, Porfirio Mohabir*
###### *CIS 9650 - Programming Analytics*
###### *May 15th, 2021*

# Introduction  

***Problem Statement***: There is a lack of in-depth analysis on the music industry overtime that does not provide accurate analysis to the public and music recommendations based on specific music metrics.  
 
***Mission Statement***: Approaching the project as though we’re analysts at Spotify, we are utilizing a reliable Spotify datasets to enhance in-depth music analytics such as, looking  for correlations, reveal trends/patterns about the music industry, and providing very vivid data visulizations. As well as providing a new recommendation system for new artists. We will do this by creating an interactive Jupyter Notebook that will have a Spotify Analysis Section and a user interactive Recommendation System.  

***Goal Statement***: The goal for this project is to give music industry professionals and enthusiast valuable data visualizations that convey trends/patterns in the music indusrty overtime. This allows the user to understand which songs can be better in a specific setting and provide users an accurate new artist recommendation list. This will also help increase traffic for music streaming platforms. 

# SCOPE  
- The System will contain function definitions
- The System will be a informational/ineractive Jupyter Notebook
- The System will Import (Pandas, numpy, matplotlib, seaborn, functools) python Libaries
- The System will provide the user with 13 data visulizations
- The System will support a simple input/output interactive recommendation system 

# Project Datasets  
[Spotify Dataset Link Here](https://www.kaggle.com/yamaerenay/spotify-dataset-19212020-160k-tracks?select=data.csv)
The Dataset provides Audio Features (metrics) of ~600k tracks released between 1922 and 2021  
- The dataset, data_o.csv, is the full Spotify dataset with a total of 19 columns. It contains song data like artist, release year, popularity, and several different song metrics such as energy, liveness, and tempo. The datasets, data_by_artist.csv and data_by_year.csv, contain most of the same data but examined in different ways.
- The data_by_year_o.csv file aggregates all of the song data for a calendar year and provides composite scores for songs from that year. 
- The tracks.csv dataset is a simple list of tracks that also provides the artist on the track, durations, release date and a few metrics(Dancibility and Energy)

###### Renamed Datasets on local machine:
data_o.csv --> data.csv
tracks.csv --> spotify_tracks
*data_by_year_o.csv was not renamed*

What we plan to do is use a combination of all three datasets to generate song/artist recommendations based on what a customer is in the mood for. We will also perform some analytics on the 3 datasets. 

*Note: Please see The Dataset Dictionary Document in the repository to gain a better understanding on the dataset key terms/meanings*  

# Spotify Analytics Component 
The analytics components provides in depth analysis based on many different music metrics, year, and tracks: 
- Acoustic Metric Vs. Energy Metric
- Average Key through the years with linear regression 
- Valence track (Musical Positiveness conveyed by track)
- Spotify Five Year Track Average Valence by year 2016-2020/Covid Impact
- 2020 Valence for Top 100 track
- Correlation heat map for all data metrics
- Features/Metric histograms
- Popularity Distribution by Density 
- Scatterplots for correlations of all data metrics
- Popularity vs Unpopularity charts
- Kernal Density Estimatmation plot (KDE) to visualize each metric
- Top Ten tracks based on "cumulative" popularity value
- Top ten tracks based on popularity value

The Jupyter notebook Analysis components will have already been executed for user to see and gain full insight. 
 
# Recommendation Systems 
The Recommendation System is the last section of the Jupter Notebook. In this Section, the user will be prompt with a series of inputs based on the recommendation component they would like to execute. 

For this step, please run this code block in our Jupyter Notebook located in the Recommendation System Section. 
```
execute_rec_system()
```
Once executing the recommendation system command, user will have the option to choose which type of recommendation they will like to run or have the ability to look up a song's metrics/statistics. 
```
Welcome to our Recommendation Sytem. Please choose the following:
===========================================================================
[1] Recommendation by feature
[2] Recommendation Top 5 songs based on multiple preferences
[3] Look up a song statistics
Please select an options:[1],[2] or [3]:
```
Recommendation by feature, choice [1], allows the user recieve song recommendations based on one metric. The user can also choose how many recommendations they would like to recieve.
```
Music Recommendation Software
=============================
1 - Acousticness
2 - Danceability
3 - Energy
4 - Instrumentalness
5 - Liveness
6 - Speechiness
7 - Valence
Please select a song characteristic to search by: 2
How 'danceble' would you like your song to be (0-10): 5
How many results would you like to see: 5

            SONG NAME                           ARTIST NAME             
 Don't Stop Believin'               'Journey'                           
 Little Do You Know                 'Alex & Sierra'                     
 Send Me on My Way                  'Rusted Root'                       
 Come As You Are                    'Nirvana'                           
 Mele Kalikimaka (Merry Christmas)  'Bing Crosby', 'The Andrews Sisters'
```
Recommendation Top 5 Songs based on multiple preferences, choice [2], allows the user to get 5 recommendations based on how much of the metrics they would like to have in their recommended list
```
Please select an options:[1],[2] or [3]:2
How much acousticness would you like? (0-10) 3
How much danceability would you like? (0-10) 4
How much energy would you like? (0-10) 5
How much instrumentalness would you like? (0-10) 3
How much liveliness would you like? (0-10) 5
How much speechiness would you like? (0-10) 6
How much valence would you like? (0-10) 4

                artists           \
152883               ['J Dilla']   
166161          ['Bill Engvall']   
87047   ['The Notorious B.I.G.']   
73946                 ['K CAMP']   
88264                 ['Eminem']   

                             name                       
152883                         Last Donut Of The Night  
166161                                        Dorkfish  
87047   Fuck Me (Interlude) - Interlude; 2005 Remaster  
73946                                          Lil Bit  
88264                                Ken Kaniff - Skit
```
The look up song statistics, choice [3], allows the user to look up a specific song (case/spelling sensative) and recieve all the metric values pertaining to that song, as well as an option to continue looking up another songs until the user decides to stop. 
```
What song would you like to see the stats of? Purple Rain
        artists    acousticness  danceability  energy  instrumentalness  \
12420  ['Prince']      0.353         3.67       4.52        0.0228        

       liveness  speechiness  valence  
12420    6.89       0.307      1.89    
Would you like to search another song? (y/n)y
What song would you like to see the stats of? The Phoenix
           artists       acousticness  danceability  energy  instrumentalness  \
37146  ['Fall Out Boy']     0.00539        5.62       9.64       0.000016       
37181  ['Fall Out Boy']     0.00539        5.62       9.64       0.000016       

       liveness  speechiness  valence  
37146    5.79       0.72        4.1    
37181    5.79       0.72        4.1    
Would you like to search another song? (y/n)n
```
The Recommendation system allows the user to restart the sytem so that they can be able to use all 3 components of the system without re-executing the command. 
```
Would you like to restart the recommendation systems [y/n]:y

[1] Recommendation by feature
[2] Recommendation Top 5 songs based on multiple preferences
[3] Look up a song statistics
Please select an options:[1],[2] or [3]:
```
# Conclusion 
We hope that our Jupyter Notebook provides music listeners and music industry professionals/enterprises, a better insight of the music industry and possibly what future music will be.

Link to our final Presentation - [HERE](https://docs.google.com/presentation/d/1pVMnqHtXWboAvLLo_tDosMDX8mqFd_1cT2F9XOrk9Ok/edit#slide=id.gd88be14239_0_12)



  










  

