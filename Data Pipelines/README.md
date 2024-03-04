## Project 1 Implementation:-

## Project Abstract

In the digital age, understanding celebrity influence on today's generation is crucial. This project explores this phenomenon using the YouTube Data API and Reddit to collect and analyze data for meaningful insights. The objective is to collect real-time data and analyze and derive meaningful insights from the celebrity-based data, their online presence, and their impact on today’s generation. This entails scrutinizing the nature of discussions surrounding celebrities, discerning whether they predominantly manifest in a positive or negative light. By navigating the intricate interplay between celebrities and their admirers, we aim to shed light on the profound ways in which these figures shape beliefs, behaviors, and preferences within today's digital age. 

## Team

Bhavit Yogesh Shah bshah5@binghamton.edu
Rushabh Kothari rkothar1@binghamton.edu
Shruti Iyengar siyenga1@binghamton.edu
Mukul Dev mchhang1@binghamton.edu


## Tech-stack

* `python` - The project is developed and tested using python v3.8. [Python Website](https://www.python.org/)
* `request` - Request is a popular HTTP networking module(aka library) for python programming language. [Request Website](https://docs.python-requests.org/en/latest/#)
* `datetime` - The datetime library used for manipulating dates and times [Python documentation Website]( https://docs.python.org/3/library/datetime.html)
* `Json` - Json is python build in package used to work on JSON data got from different API get request[Python documentation Website](https://docs.python.org/3/library/datetime.html)
* `base64` - base64 is python library used for data encoding [Python documentation Website](https://docs.python.org/3/library/datetime.html)
* `MongoDB` - MongoDB is NoSQL document database used to store data collected from Reddit and YouTube websites [MongoDB Website]( https://www.mongodb.com/)
* `PyMongo` - PyMongo is Python distribution containing tool used to work with MongoDB using Python [PyMongo Website]
( https://pymongo.readthedocs.io/en/stable/)


For Installation of different packages:-

Use requirements.txt file(Mentioned in how-to-run steps.)

## Two data-source documentation

* `Reddit` - We are using `/cristianoronaldo`,`/messi`,`/SelenaGomez`,`/KylieJenner`,`/DwayneJohnson`,`/ArianaGrande`,`/KimKardashianPics`,`/Beyonce`,`/KhloeKardash`, `/KendallJenner` etc.
* [https://www.reddit.com/api/v1/access_token]( https://www.reddit.com/dev/api/  ) - <this Reddit endpoint URL provide data for post related to all 10 celebrities.>

* `YouTube` -
*"auth_uri": "https://accounts.google.com/o/oauth2/auth",
        "token_uri": "https://oauth2.googleapis.com/token",
        "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs", - <this YouTUbe end point url provides data for celebrities >

Note:-
For Youtube, we also filter/ handle exceptions that are due to videos that have "Disabled Comments". 

 (One thing we observed is that YouTube API has a fetch request limit, if we cross that it will throw an error that more API calls will be taking place)

 {Also, a process is already running such that API fetch request will fetch every 1 hour and get the result in the Reddit and YouTube collections as discussed above.)

To view the information of this process:- Go to VM and log in such that you are in user@CS515-25:- (user will be your username)
Run command: -  ps -ef | grep python3. 

You will be able to see more details in the MongoDB collections which display individual posts and comments.

 ## How to run the project?

Go inside project-1-implementation-team-caffeine folder:-
1)Using a virtual environment

python3 -m venv venv


2)Activate the virtual environment:

On Linux/macOS:
source venv/bin/activate

On Windows:
. venv/bin/activate

3)Installing all required packages 

python -m pip install --upgrade pip
Use this before installing the below requirements.txt  if  direct install doesn't work 

then,

pip install -r requirements.txt

3)run the main script 

python3 main.py

Please Note

1: Reddit API calls take some time to fetch as compared to youtube.

2: r/politics subreddit added as per our discussion with professor. This is loaded in a separate collection named "politics_data" and for checking the count, we are using a collection called "store_count". 


## Database schema - NoSQL MongoDB


collection_1: YouTube_data structure sample:-
{
  "_id": {
    "$oid": "65417320ea8ac22301457ef5"
  },
  "Name": "Selena Gomez",
  "video_info": {
    "kind": "youtube#video",
    "etag": "KyCSzF3W1hq4p9kHYE_c7X5kuhM",
    "id": "3AtDnEC4zak",
    "snippet": {
      "publishedAt": "2016-08-02T20:00:26Z",
      "channelId": "UCwppdrjsBPAZg5_cUwQjfMQ",
      "title": "Charlie Puth - We Don't Talk Anymore (feat. Selena Gomez) [Official Video]",
      "description": "Charlie Puth - We Don't Talk Anymore (feat. Selena Gomez) [Official Video]\nFrom Charlie's debut album Nine Track Mind!\nDownload/Stream: https://Atlantic.lnk.to/NineTrackMindID \n\nExclusive Nine Track Mind Bundles Available Here: http://smarturl.it/NTMBundlesYT\n\nLight Switch out now!\nDownload/stream: https://charlieputh.lnk.to/LightSwitchID\n\nSubscribe for more official content from Charlie Puth:\nhttps://Atlantic.lnk.to/CPsubscribeID\n\nFollow Charlie\nhttp://charlieputh.com \nhttp://twitter.com/charlieputh \nhttp://facebook.com/charlieputh \nhttp://instagram.com/charlieputh\nhttps://soundcloud.com/charlieputh\nhttps://www.tiktok.com/@charlieputh\n\nDirector: Phil Pinto\n\nThe official YouTube channel of Atlantic Records artist Charlie Puth. Subscribe for the latest music videos, performances, and more.\n\n#CharliePuth #WeDontTalkAnymore #MusicVideo",
      "thumbnails": {
        "default": {
          "url": "https://i.ytimg.com/vi/3AtDnEC4zak/default.jpg",
          "width": 120,
          "height": 90
        },
        "medium": {
          "url": "https://i.ytimg.com/vi/3AtDnEC4zak/mqdefault.jpg",
          "width": 320,
          "height": 180
        },
        "high": {
          "url": "https://i.ytimg.com/vi/3AtDnEC4zak/hqdefault.jpg",
          "width": 480,
          "height": 360
        },
        "standard": {
          "url": "https://i.ytimg.com/vi/3AtDnEC4zak/sddefault.jpg",
          "width": 640,
          "height": 480
        },
        "maxres": {
          "url": "https://i.ytimg.com/vi/3AtDnEC4zak/maxresdefault.jpg",
          "width": 1280,
          "height": 720
        }
      },
      "channelTitle": "Charlie Puth",
      "tags": [
        "Charlie Puth",
        "Selena Gomez",
        "We Don't Talk Anymore",
        "Official Video",
        "Atlantic Records",
        "Nine Track Mind",
        "Charlie Puth - We Don't Talk Anymore (feat. Selena Gomez) [Official Video]",
        "wdta",
        "charlie puth",
        "charlie selina",
        "we dont talk anymore",
        "we dont talk anymore cover",
        "gomez puth",
        "selena gomez charile puth",
        "nine track mind",
        "we dont talk anymore selena",
        "we dont talk anymore like we used to do",
        "we dont"
      ],
      "categoryId": "10",
      "liveBroadcastContent": "none",
      "localized": {
        "title": "Charlie Puth - We Don't Talk Anymore (feat. Selena Gomez) [Official Video]",
        "description": "Charlie Puth - We Don't Talk Anymore (feat. Selena Gomez) [Official Video]\nFrom Charlie's debut album Nine Track Mind!\nDownload/Stream: https://Atlantic.lnk.to/NineTrackMindID \n\nExclusive Nine Track Mind Bundles Available Here: http://smarturl.it/NTMBundlesYT\n\nLight Switch out now!\nDownload/stream: https://charlieputh.lnk.to/LightSwitchID\n\nSubscribe for more official content from Charlie Puth:\nhttps://Atlantic.lnk.to/CPsubscribeID\n\nFollow Charlie\nhttp://charlieputh.com \nhttp://twitter.com/charlieputh \nhttp://facebook.com/charlieputh \nhttp://instagram.com/charlieputh\nhttps://soundcloud.com/charlieputh\nhttps://www.tiktok.com/@charlieputh\n\nDirector: Phil Pinto\n\nThe official YouTube channel of Atlantic Records artist Charlie Puth. Subscribe for the latest music videos, performances, and more.\n\n#CharliePuth #WeDontTalkAnymore #MusicVideo"
      }
    },
    "statistics": {
      "viewCount": "3072807750",
      "likeCount": "14199256",
      "favoriteCount": "0",
      "commentCount": "402664"
    }
  },
  "comments": [
    "un gran duo  van a pasar años y todavia va a ser de las mejores 💗",
    "I left talking with her from today .....1.11.2023 . We don't talk text see smile think anymore.",
    "No nut November remember everyone we are disciples of god.We can do it 👍",
    "Any international fans?\nComment your country",
    "Nov.?",
    "❤❤❤ for 2030 anyone",
    "31Oct2023,6:40PM,Tue",
    "Who listens in November 2023🌝❤️",
    "fell it 🥺",
    "احب هاي اغنيه من دهر زمان"
  ],
  "view_count": "3072807750"
}

collection_2: Reddit_data structure sample:-

{
  "_id": {
    "$oid": "6541737bea8ac22301457f21"
  },
  "id": "17k4nes",
  "subreddit": "messi",
  "title": "[France Football] Lionel Messi has won the 2023 Ballon d’Or",
  "selftext": "",
  "upvote_ratio": "messi",
  "ups": 8,
  "downs": 0,
  "score": 8,
  "num_comments": 3,
  "permalink": "/r/messi/comments/17k4nes/france_football_lionel_messi_has_won_the_2023/",
  "comments": [
    {
      "id": "k75k4l7",
      "subreddit": "messi",
      "comment_text": "G.O.A.T"
    },
    {
      "id": "k75ejy3",
      "subreddit": "messi",
      "comment_text": "！！lets gooo"
    }
  ]
}

