# GraphQL Queries #

**Configure a GraphQL API that can answer the following statements via GraphQL:**

### 1. How many artists are in the database? 

This query is required to be executed as administrator. 

*Request Headers:* 

content-type: application/json

x-hasura-admin-secret: somesecrectkey

**Query:**
```
query CountArtist {
  artist_aggregate {
    aggregate {
      count
    }
  }
}
```
**Response:**
```
{
  "data": {
    "artist_aggregate": {
      "aggregate": {
        "count": 275
      }
    }
  }
}
```

### 2. List the first track of every album by every artist in ascending order. ###

This query is required to be executed as administrator.

Request Headers: 
content-type: application/json
x-hasura-admin-secret: somesecrectkey

**Query:**
```
query FirstTracks1 {
  artist(order_by: {name: asc}) {
    artist_id
    name
    albums(order_by: {title: asc}) {
      album_id
      title
      tracks(order_by: {track_id: asc}, limit: 1) {
        track_id
        name
      }
    }
  }
}
```

**Response:**
```
{
  "data": {
    "artist": [
      {
        "artist_id": 43,
        "name": "A Cor Do Som",
        "albums": []
      },
      {
        "artist_id": 1,
        "name": "AC/DC",
        "albums": [
          {
            "album_id": 1,
            "title": "For Those About To Rock We Salute You",
            "tracks": [
              {
                "track_id": 1,
                "name": "For Those About To Rock (We Salute You)"
              }
            ]
          },
          {
            "album_id": 4,
            "title": "Let There Be Rock",
            "tracks": [
              {
                "track_id": 15,
                "name": "Go Down"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 230,
        "name": "Aaron Copland & London Symphony Orchestra",
        "albums": [
          {
            "album_id": 296,
            "title": "A Copland Celebration, Vol. I",
            "tracks": [
              {
                "track_id": 3427,
                "name": "Fanfare for the Common Man"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 202,
        "name": "Aaron Goldberg",
        "albums": [
          {
            "album_id": 267,
            "title": "Worlds",
            "tracks": [
              {
                "track_id": 3357,
                "name": "OAM's Blues"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 214,
        "name": "Academy of St. Martin in the Fields & Sir Neville Marriner",
        "albums": [
          {
            "album_id": 280,
            "title": "The World of Classical Favourites",
            "tracks": [
              {
                "track_id": 3411,
                "name": "Solomon HWV 67: The Arrival of the Queen of Sheba"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 215,
        "name": "Academy of St. Martin in the Fields Chamber Ensemble & Sir Neville Marriner",
        "albums": [
          {
            "album_id": 281,
            "title": "Sir Neville Marriner: A Celebration",
            "tracks": [
              {
                "track_id": 3412,
                "name": "\"Eine Kleine Nachtmusik\" Serenade In G, K. 525: I. Allegro"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 222,
        "name": "Academy of St. Martin in the Fields, John Birch, Sir Neville Marriner & Sylvia McNair",
        "albums": [
          {
            "album_id": 288,
            "title": "Fauré: Requiem, Ravel: Pavane & Others",
            "tracks": [
              {
                "track_id": 3419,
                "name": "Requiem, Op.48: 4. Pie Jesu"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 257,
        "name": "Academy of St. Martin in the Fields, Sir Neville Marriner & Thurston Dart",
        "albums": [
          {
            "album_id": 327,
            "title": "Bach: Orchestral Suites Nos. 1 - 4",
            "tracks": [
              {
                "track_id": 3482,
                "name": "Suite No. 3 in D, BWV 1068: III. Gavotte I & II"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 239,
        "name": "Academy of St. Martin in the Fields, Sir Neville Marriner & William Bennett",
        "albums": []
      },
      {
        "artist_id": 2,
        "name": "Accept",
        "albums": [
          {
            "album_id": 2,
            "title": "Balls to the Wall",
            "tracks": [
              {
                "track_id": 2,
                "name": "Balls to the Wall"
              }
            ]
          },
          {
            "album_id": 3,
            "title": "Restless and Wild",
            "tracks": [
              {
                "track_id": 3,
                "name": "Fast As a Shark"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 260,
        "name": "Adrian Leaper & Doreen de Feis",
        "albums": [
          {
            "album_id": 330,
            "title": "Górecki: Symphony No. 3",
            "tracks": [
              {
                "track_id": 3485,
                "name": "Symphony No. 3 Op. 36 for Orchestra and Soprano \"Symfonia Piesni Zalosnych\" \\ Lento E Largo - Tranquillissimo"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 3,
        "name": "Aerosmith",
        "albums": [
          {
            "album_id": 5,
            "title": "Big Ones",
            "tracks": [
              {
                "track_id": 23,
                "name": "Walk On Water"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 161,
        "name": "Aerosmith & Sierra Leone's Refugee Allstars",
        "albums": []
      },
      {
        "artist_id": 197,
        "name": "Aisha Duo",
        "albums": [
          {
            "album_id": 262,
            "title": "Quiet Songs",
            "tracks": [
              {
                "track_id": 3349,
                "name": "Amanda"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 4,
        "name": "Alanis Morissette",
        "albums": [
          {
            "album_id": 6,
            "title": "Jagged Little Pill",
            "tracks": [
              {
                "track_id": 38,
                "name": "All I Really Want"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 206,
        "name": "Alberto Turco & Nova Schola Gregoriana",
        "albums": [
          {
            "album_id": 272,
            "title": "Adorate Deum: Gregorian Chant from the Proper of the Mass",
            "tracks": [
              {
                "track_id": 3403,
                "name": "Intoitus: Adorate Deum"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 5,
        "name": "Alice In Chains",
        "albums": [
          {
            "album_id": 7,
            "title": "Facelift",
            "tracks": [
              {
                "track_id": 51,
                "name": "We Die Young"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 252,
        "name": "Amy Winehouse",
        "albums": [
          {
            "album_id": 321,
            "title": "Back to Black",
            "tracks": [
              {
                "track_id": 3455,
                "name": "Rehab"
              }
            ]
          },
          {
            "album_id": 322,
            "title": "Frank",
            "tracks": [
              {
                "track_id": 3467,
                "name": "Intro / Stronger Than Me"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 209,
        "name": "Anne-Sophie Mutter, Herbert Von Karajan & Wiener Philharmoniker",
        "albums": [
          {
            "album_id": 275,
            "title": "Vivaldi: The Four Seasons",
            "tracks": [
              {
                "track_id": 3406,
                "name": "Concerto No. 1 in E Major, RV 269 \"Spring\": I. Allegro"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 243,
        "name": "Antal Doráti & London Symphony Orchestra",
        "albums": [
          {
            "album_id": 308,
            "title": "Tchaikovsky: 1812 Festival Overture, Op.49, Capriccio Italien & Beethoven: Wellington's Victory",
            "tracks": [
              {
                "track_id": 3442,
                "name": "Wellington's Victory or the Battle Symphony, Op.91: 2. Symphony of Triumph"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 6,
        "name": "Antônio Carlos Jobim",
        "albums": [
          {
            "album_id": 34,
            "title": "Chill: Brazil (Disc 2)",
            "tracks": [
              {
                "track_id": 391,
                "name": "Garota De Ipanema"
              }
            ]
          },
          {
            "album_id": 8,
            "title": "Warner 25 Anos",
            "tracks": [
              {
                "track_id": 63,
                "name": "Desafinado"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 7,
        "name": "Apocalyptica",
        "albums": [
          {
            "album_id": 9,
            "title": "Plays Metallica By Four Cellos",
            "tracks": [
              {
                "track_id": 77,
                "name": "Enter Sandman"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 159,
        "name": "Aquaman",
        "albums": [
          {
            "album_id": 254,
            "title": "Aquaman",
            "tracks": [
              {
                "track_id": 3250,
                "name": "Pilot"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 8,
        "name": "Audioslave",
        "albums": [
          {
            "album_id": 10,
            "title": "Audioslave",
            "tracks": [
              {
                "track_id": 85,
                "name": "Cochise"
              }
            ]
          },
          {
            "album_id": 11,
            "title": "Out Of Exile",
            "tracks": [
              {
                "track_id": 99,
                "name": "Your Time Has Come"
              }
            ]
          },
          {
            "album_id": 271,
            "title": "Revelations",
            "tracks": [
              {
                "track_id": 3389,
                "name": "Revelations"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 166,
        "name": "Avril Lavigne",
        "albums": []
      },
      {
        "artist_id": 26,
        "name": "Azymuth",
        "albums": []
      },
      {
        "artist_id": 31,
        "name": "Baby Consuelo",
        "albums": []
      },
      {
        "artist_id": 9,
        "name": "BackBeat",
        "albums": [
          {
            "album_id": 12,
            "title": "BackBeat Soundtrack",
            "tracks": [
              {
                "track_id": 111,
                "name": "Money"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 38,
        "name": "Banda Black Rio",
        "albums": []
      },
      {
        "artist_id": 224,
        "name": "Barry Wordsworth & BBC Concert Orchestra",
        "albums": [
          {
            "album_id": 290,
            "title": "The Last Night of the Proms",
            "tracks": [
              {
                "track_id": 3421,
                "name": "Nimrod (Adagio) from Variations On an Original Theme, Op. 36 \"Enigma\""
              }
            ]
          }
        ]
      },
      {
        "artist_id": 48,
        "name": "Barão Vermelho",
        "albums": []
      },
      {
        "artist_id": 147,
        "name": "Battlestar Galactica",
        "albums": [
          {
            "album_id": 227,
            "title": "Battlestar Galactica, Season 3",
            "tracks": [
              {
                "track_id": 2820,
                "name": "Occupation / Precipice"
              }
            ]
          },
          {
            "album_id": 226,
            "title": "Battlestar Galactica: The Story So Far",
            "tracks": [
              {
                "track_id": 2819,
                "name": "Battlestar Galactica: The Story So Far"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 158,
        "name": "Battlestar Galactica (Classic)",
        "albums": [
          {
            "album_id": 253,
            "title": "Battlestar Galactica (Classic), Season 1",
            "tracks": [
              {
                "track_id": 3226,
                "name": "Battlestar Galactica, Pt. 1"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 29,
        "name": "Bebel Gilberto",
        "albums": []
      },
      {
        "artist_id": 171,
        "name": "Ben Harper",
        "albums": []
      },
      {
        "artist_id": 237,
        "name": "Berliner Philharmoniker & Hans Rosbaud",
        "albums": [
          {
            "album_id": 303,
            "title": "Sibelius: Finlandia",
            "tracks": [
              {
                "track_id": 3436,
                "name": "Karelia Suite, Op.11: 2. Ballade (Tempo Di Menuetto)"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 248,
        "name": "Berliner Philharmoniker & Herbert Von Karajan",
        "albums": [
          {
            "album_id": 316,
            "title": "Grieg: Peer Gynt Suites & Sibelius: Pelléas et Mélisande",
            "tracks": [
              {
                "track_id": 3450,
                "name": "Peer Gynt Suite No.1, Op.46: 1. Morning Mood"
              }
            ]
          },
          {
            "album_id": 320,
            "title": "Mozart: Symphonies Nos. 40 & 41",
            "tracks": [
              {
                "track_id": 3454,
                "name": "Symphony No. 41 in C Major, K. 551, \"Jupiter\": IV. Molto allegro"
              }
            ]
          },
          {
            "album_id": 336,
            "title": "Prokofiev: Symphony No.5 & Stravinksy: Le Sacre Du Printemps",
            "tracks": [
              {
                "track_id": 3491,
                "name": "Le Sacre Du Printemps: I.iv. Spring Rounds"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 216,
        "name": "Berliner Philharmoniker, Claudio Abbado & Sabine Meyer",
        "albums": [
          {
            "album_id": 282,
            "title": "Mozart: Wind Concertos",
            "tracks": [
              {
                "track_id": 3413,
                "name": "Concerto for Clarinet in A Major, K. 622: II. Adagio"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 167,
        "name": "Big & Rich",
        "albums": []
      },
      {
        "artist_id": 10,
        "name": "Billy Cobham",
        "albums": [
          {
            "album_id": 13,
            "title": "The Best Of Billy Cobham",
            "tracks": [
              {
                "track_id": 123,
                "name": "Quadrant"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 169,
        "name": "Black Eyed Peas",
        "albums": []
      },
      {
        "artist_id": 11,
        "name": "Black Label Society",
        "albums": [
          {
            "album_id": 14,
            "title": "Alcohol Fueled Brewtality Live! [Disc 1]",
            "tracks": [
              {
                "track_id": 131,
                "name": "Intro/ Low Down"
              }
            ]
          },
          {
            "album_id": 15,
            "title": "Alcohol Fueled Brewtality Live! [Disc 2]",
            "tracks": [
              {
                "track_id": 144,
                "name": "Heart Of Gold"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 12,
        "name": "Black Sabbath",
        "albums": [
          {
            "album_id": 16,
            "title": "Black Sabbath",
            "tracks": [
              {
                "track_id": 149,
                "name": "Black Sabbath"
              }
            ]
          },
          {
            "album_id": 17,
            "title": "Black Sabbath Vol. 4 (Remaster)",
            "tracks": [
              {
                "track_id": 156,
                "name": "Wheels Of Confusion / The Straightener"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 13,
        "name": "Body Count",
        "albums": [
          {
            "album_id": 18,
            "title": "Body Count",
            "tracks": [
              {
                "track_id": 166,
                "name": "Smoked Pork"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 229,
        "name": "Boston Symphony Orchestra & Seiji Ozawa",
        "albums": [
          {
            "album_id": 295,
            "title": "Carmina Burana",
            "tracks": [
              {
                "track_id": 3426,
                "name": "Carmina Burana: O Fortuna"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 219,
        "name": "Britten Sinfonia, Ivor Bolton & Lesley Garrett",
        "albums": [
          {
            "album_id": 285,
            "title": "A Soprano Inspired",
            "tracks": [
              {
                "track_id": 3416,
                "name": "Ave Maria"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 14,
        "name": "Bruce Dickinson",
        "albums": [
          {
            "album_id": 19,
            "title": "Chemical Wedding",
            "tracks": [
              {
                "track_id": 183,
                "name": "King In Crimson"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 15,
        "name": "Buddy Guy",
        "albums": [
          {
            "album_id": 20,
            "title": "The Best Of Buddy Guy - The Millenium Collection",
            "tracks": [
              {
                "track_id": 194,
                "name": "First Time I Met The Blues"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 273,
        "name": "C. Monteverdi, Nigel Rogers - Chiaroscuro; London Baroque; London Cornett & Sackbu",
        "albums": [
          {
            "album_id": 345,
            "title": "Monteverdi: L'Orfeo",
            "tracks": [
              {
                "track_id": 3501,
                "name": "L'orfeo, Act 3, Sinfonia (Orchestra)"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 16,
        "name": "Caetano Veloso",
        "albums": [
          {
            "album_id": 21,
            "title": "Prenda Minha",
            "tracks": [
              {
                "track_id": 205,
                "name": "Jorge Da Capadócia"
              }
            ]
          },
          {
            "album_id": 22,
            "title": "Sozinho Remix Ao Vivo",
            "tracks": [
              {
                "track_id": 223,
                "name": "Sozinho (Hitmakers Classic Mix)"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 196,
        "name": "Cake",
        "albums": [
          {
            "album_id": 260,
            "title": "Cake: B-Sides and Rarities",
            "tracks": [
              {
                "track_id": 3336,
                "name": "War Pigs"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 253,
        "name": "Calexico",
        "albums": [
          {
            "album_id": 323,
            "title": "Carried to Dust (Bonus Track Version)",
            "tracks": [
              {
                "track_id": 3478,
                "name": "Slowness"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 262,
        "name": "Charles Dutoit & L'Orchestre Symphonique de Montréal",
        "albums": [
          {
            "album_id": 332,
            "title": "The Ultimate Relexation Album",
            "tracks": [
              {
                "track_id": 3487,
                "name": "3 Gymnopédies: No.1 - Lent Et Grave, No.3 - Lent Et Douloureux"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 185,
        "name": "Charlie Brown Jr.",
        "albums": []
      },
      {
        "artist_id": 220,
        "name": "Chicago Symphony Chorus, Chicago Symphony Orchestra & Sir Georg Solti",
        "albums": [
          {
            "album_id": 286,
            "title": "Great Opera Choruses",
            "tracks": [
              {
                "track_id": 3417,
                "name": "Nabucco: Chorus, \"Va, Pensiero, Sull'ali Dorate\""
              }
            ]
          }
        ]
      },
      {
        "artist_id": 233,
        "name": "Chicago Symphony Orchestra & Fritz Reiner",
        "albums": [
          {
            "album_id": 299,
            "title": "Scheherazade",
            "tracks": [
              {
                "track_id": 3432,
                "name": "Scheherazade, Op. 35: I. The Sea and Sindbad's Ship"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 17,
        "name": "Chico Buarque",
        "albums": [
          {
            "album_id": 23,
            "title": "Minha Historia",
            "tracks": [
              {
                "track_id": 226,
                "name": "Carolina"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 18,
        "name": "Chico Science & Nação Zumbi",
        "albums": [
          {
            "album_id": 24,
            "title": "Afrociberdelia",
            "tracks": [
              {
                "track_id": 246,
                "name": "Mateus Enter"
              }
            ]
          },
          {
            "album_id": 25,
            "title": "Da Lama Ao Caos",
            "tracks": [
              {
                "track_id": 269,
                "name": "Banditismo Por Uma Questa"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 244,
        "name": "Choir Of Westminster Abbey & Simon Preston",
        "albums": [
          {
            "album_id": 309,
            "title": "Palestrina: Missa Papae Marcelli & Allegri: Miserere",
            "tracks": [
              {
                "track_id": 3443,
                "name": "Missa Papae Marcelli: Kyrie"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 246,
        "name": "Chor der Wiener Staatsoper, Herbert Von Karajan & Wiener Philharmoniker",
        "albums": [
          {
            "album_id": 313,
            "title": "Bizet: Carmen Highlights",
            "tracks": [
              {
                "track_id": 3447,
                "name": "Carmen: Overture"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 205,
        "name": "Chris Cornell",
        "albums": [
          {
            "album_id": 270,
            "title": "Carry On",
            "tracks": [
              {
                "track_id": 3375,
                "name": "No Such Thing"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 160,
        "name": "Christina Aguilera featuring BigElf",
        "albums": []
      },
      {
        "artist_id": 250,
        "name": "Christopher O'Riley",
        "albums": [
          {
            "album_id": 318,
            "title": "SCRIABIN: Vers la flamme",
            "tracks": [
              {
                "track_id": 3452,
                "name": "SCRIABIN: Prelude in B Major, Op. 11, No. 11"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 19,
        "name": "Cidade Negra",
        "albums": [
          {
            "album_id": 26,
            "title": "Acústico MTV [Live]",
            "tracks": [
              {
                "track_id": 282,
                "name": "Girassol"
              }
            ]
          },
          {
            "album_id": 27,
            "title": "Cidade Negra - Hits",
            "tracks": [
              {
                "track_id": 299,
                "name": "Onde Você Mora?"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 20,
        "name": "Cláudio Zoli",
        "albums": [
          {
            "album_id": 28,
            "title": "Na Pista",
            "tracks": [
              {
                "track_id": 313,
                "name": "Noite Do Prazer"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 163,
        "name": "Corinne Bailey Rae",
        "albums": []
      },
      {
        "artist_id": 76,
        "name": "Creedence Clearwater Revival",
        "albums": [
          {
            "album_id": 54,
            "title": "Chronicle, Vol. 1",
            "tracks": [
              {
                "track_id": 675,
                "name": "Susie Q"
              }
            ]
          },
          {
            "album_id": 55,
            "title": "Chronicle, Vol. 2",
            "tracks": [
              {
                "track_id": 695,
                "name": "Walking On The Water"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 77,
        "name": "Cássia Eller",
        "albums": [
          {
            "album_id": 56,
            "title": "Cássia Eller - Coleção Sem Limite [Disc 2]",
            "tracks": [
              {
                "track_id": 715,
                "name": "Gatas Extraordinárias"
              }
            ]
          },
          {
            "album_id": 57,
            "title": "Cássia Eller - Sem Limite [Disc 1]",
            "tracks": [
              {
                "track_id": 730,
                "name": "Malandragem"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 192,
        "name": "DJ Dolores & Orchestra Santa Massa",
        "albums": []
      },
      {
        "artist_id": 277,
        "name": "Daljeet",
        "albums": [
          {
            "album_id": 348,
            "title": "Ghost",
            "tracks": []
          }
        ]
      },
      {
        "artist_id": 278,
        "name": "Daljeet",
        "albums": [
          {
            "album_id": 349,
            "title": "Ghost",
            "tracks": []
          }
        ]
      },
      {
        "artist_id": 276,
        "name": "Daljeet",
        "albums": []
      },
      {
        "artist_id": 55,
        "name": "David Coverdale",
        "albums": [
          {
            "album_id": 40,
            "title": "Into The Light",
            "tracks": [
              {
                "track_id": 489,
                "name": "Into The Light"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 58,
        "name": "Deep Purple",
        "albums": [
          {
            "album_id": 58,
            "title": "Come Taste The Band",
            "tracks": [
              {
                "track_id": 745,
                "name": "Comin' Home"
              }
            ]
          },
          {
            "album_id": 59,
            "title": "Deep Purple In Rock",
            "tracks": [
              {
                "track_id": 754,
                "name": "Speed King"
              }
            ]
          },
          {
            "album_id": 60,
            "title": "Fireball",
            "tracks": [
              {
                "track_id": 761,
                "name": "Fireball"
              }
            ]
          },
          {
            "album_id": 61,
            "title": "Knocking at Your Back Door: The Best Of Deep Purple in the 80's",
            "tracks": [
              {
                "track_id": 768,
                "name": "Knocking At Your Back Door"
              }
            ]
          },
          {
            "album_id": 43,
            "title": "MK III The Final Concerts [Disc 1]",
            "tracks": [
              {
                "track_id": 543,
                "name": "Burn"
              }
            ]
          },
          {
            "album_id": 62,
            "title": "Machine Head",
            "tracks": [
              {
                "track_id": 779,
                "name": "Highway Star"
              }
            ]
          },
          {
            "album_id": 63,
            "title": "Purpendicular",
            "tracks": [
              {
                "track_id": 786,
                "name": "Vavoom : Ted The Mechanic"
              }
            ]
          },
          {
            "album_id": 64,
            "title": "Slaves And Masters",
            "tracks": [
              {
                "track_id": 798,
                "name": "King Of Dreams"
              }
            ]
          },
          {
            "album_id": 65,
            "title": "Stormbringer",
            "tracks": [
              {
                "track_id": 807,
                "name": "Stormbringer"
              }
            ]
          },
          {
            "album_id": 66,
            "title": "The Battle Rages On",
            "tracks": [
              {
                "track_id": 816,
                "name": "The Battle Rages On"
              }
            ]
          },
          {
            "album_id": 50,
            "title": "The Final Concerts (Disc 2)",
            "tracks": [
              {
                "track_id": 620,
                "name": "Space Truckin'"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 78,
        "name": "Def Leppard",
        "albums": [
          {
            "album_id": 67,
            "title": "Vault: Def Leppard's Greatest Hits",
            "tracks": [
              {
                "track_id": 826,
                "name": "Pour Some Sugar On Me"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 79,
        "name": "Dennis Chambers",
        "albums": [
          {
            "album_id": 68,
            "title": "Outbreak",
            "tracks": [
              {
                "track_id": 842,
                "name": "Roll Call"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 164,
        "name": "Dhani Harrison & Jakob Dylan",
        "albums": []
      },
      {
        "artist_id": 80,
        "name": "Djavan",
        "albums": [
          {
            "album_id": 69,
            "title": "Djavan Ao Vivo - Vol. 02",
            "tracks": [
              {
                "track_id": 851,
                "name": "Pétala"
              }
            ]
          },
          {
            "album_id": 70,
            "title": "Djavan Ao Vivo - Vol. 1",
            "tracks": [
              {
                "track_id": 864,
                "name": "Samurai"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 157,
        "name": "Dread Zeppelin",
        "albums": [
          {
            "album_id": 252,
            "title": "Un-Led-Ed",
            "tracks": [
              {
                "track_id": 3225,
                "name": "Your Time Is Gonna Come"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 37,
        "name": "Ed Motta",
        "albums": [
          {
            "album_id": 47,
            "title": "The Best of Ed Motta",
            "tracks": [
              {
                "track_id": 583,
                "name": "Solução"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 242,
        "name": "Edo de Waart & San Francisco Symphony",
        "albums": [
          {
            "album_id": 307,
            "title": "Adams, John: The Chairman Dances",
            "tracks": [
              {
                "track_id": 3441,
                "name": "Two Fanfares for Orchestra: II. Short Ride in a Fast Machine"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 49,
        "name": "Edson, DJ Marky & DJ Patife Featuring Fernanda Porto",
        "albums": []
      },
      {
        "artist_id": 41,
        "name": "Elis Regina",
        "albums": [
          {
            "album_id": 71,
            "title": "Elis Regina-Minha História",
            "tracks": [
              {
                "track_id": 877,
                "name": "O Bêbado e a Equilibrista"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 235,
        "name": "Emanuel Ax, Eugene Ormandy & Philadelphia Orchestra",
        "albums": [
          {
            "album_id": 301,
            "title": "Chopin: Piano Concertos Nos. 1 & 2",
            "tracks": [
              {
                "track_id": 3434,
                "name": "Concerto for Piano No. 2 in F Minor, Op. 21: II. Larghetto"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 272,
        "name": "Emerson String Quartet",
        "albums": [
          {
            "album_id": 344,
            "title": "Schubert: The Late String Quartets & String Quintet (3 CD's)",
            "tracks": [
              {
                "track_id": 3500,
                "name": "String Quartet No. 12 in C Minor, D. 703 \"Quartettsatz\": II. Andante - Allegro assai"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 208,
        "name": "English Concert & Trevor Pinnock",
        "albums": [
          {
            "album_id": 315,
            "title": "Handel: Music for the Royal Fireworks (Original Version 1749)",
            "tracks": [
              {
                "track_id": 3449,
                "name": "Music for the Royal Fireworks, HWV351 (1749): La Réjouissance"
              }
            ]
          },
          {
            "album_id": 274,
            "title": "Pachelbel: Canon & Gigue",
            "tracks": [
              {
                "track_id": 3405,
                "name": "Canon and Gigue in D Major: I. Canon"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 263,
        "name": "Equale Brass Ensemble, John Eliot Gardiner & Munich Monteverdi Orchestra and Choir",
        "albums": [
          {
            "album_id": 333,
            "title": "Purcell: Music for the Queen Mary",
            "tracks": [
              {
                "track_id": 3488,
                "name": "Music for the Funeral of Queen Mary: VI. \"Thou Knowest, Lord, the Secrets of Our Hearts\""
              }
            ]
          }
        ]
      },
      {
        "artist_id": 81,
        "name": "Eric Clapton",
        "albums": [
          {
            "album_id": 72,
            "title": "The Cream Of Clapton",
            "tracks": [
              {
                "track_id": 891,
                "name": "Layla"
              }
            ]
          },
          {
            "album_id": 73,
            "title": "Unplugged",
            "tracks": [
              {
                "track_id": 909,
                "name": "Signe"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 226,
        "name": "Eugene Ormandy",
        "albums": [
          {
            "album_id": 292,
            "title": "Holst: The Planets, Op. 32 & Vaughan Williams: Fantasies",
            "tracks": [
              {
                "track_id": 3423,
                "name": "Jupiter, the Bringer of Jollity"
              }
            ]
          },
          {
            "album_id": 343,
            "title": "Respighi:Pines of Rome",
            "tracks": [
              {
                "track_id": 3499,
                "name": "Pini Di Roma (Pinien Von Rom) \\ I Pini Della Via Appia"
              }
            ]
          },
          {
            "album_id": 311,
            "title": "Strauss: Waltzes",
            "tracks": [
              {
                "track_id": 3445,
                "name": "On the Beautiful Blue Danube"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 82,
        "name": "Faith No More",
        "albums": [
          {
            "album_id": 74,
            "title": "Album Of The Year",
            "tracks": [
              {
                "track_id": 923,
                "name": "Collision"
              }
            ]
          },
          {
            "album_id": 75,
            "title": "Angel Dust",
            "tracks": [
              {
                "track_id": 935,
                "name": "Land Of Sunshine"
              }
            ]
          },
          {
            "album_id": 76,
            "title": "King For A Day Fool For A Lifetime",
            "tracks": [
              {
                "track_id": 949,
                "name": "Get Out"
              }
            ]
          },
          {
            "album_id": 77,
            "title": "The Real Thing",
            "tracks": [
              {
                "track_id": 964,
                "name": "From Out Of Nowhere"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 83,
        "name": "Falamansa",
        "albums": [
          {
            "album_id": 78,
            "title": "Deixa Entrar",
            "tracks": [
              {
                "track_id": 975,
                "name": "Deixa Entrar"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 241,
        "name": "Felix Schmidt, London Symphony Orchestra & Rafael Frühbeck de Burgos",
        "albums": [
          {
            "album_id": 306,
            "title": "Elgar: Cello Concerto & Vaughan Williams: Fantasias",
            "tracks": [
              {
                "track_id": 3440,
                "name": "Concerto for Cello and Orchestra in E minor, Op. 85: I. Adagio - Moderato"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 39,
        "name": "Fernanda Porto",
        "albums": []
      },
      {
        "artist_id": 84,
        "name": "Foo Fighters",
        "albums": [
          {
            "album_id": 79,
            "title": "In Your Honor [Disc 1]",
            "tracks": [
              {
                "track_id": 989,
                "name": "In Your Honor"
              }
            ]
          },
          {
            "album_id": 80,
            "title": "In Your Honor [Disc 2]",
            "tracks": [
              {
                "track_id": 999,
                "name": "Still"
              }
            ]
          },
          {
            "album_id": 81,
            "title": "One By One",
            "tracks": [
              {
                "track_id": 1009,
                "name": "All My Life"
              }
            ]
          },
          {
            "album_id": 82,
            "title": "The Colour And The Shape",
            "tracks": [
              {
                "track_id": 1020,
                "name": "Doll"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 85,
        "name": "Frank Sinatra",
        "albums": [
          {
            "album_id": 83,
            "title": "My Way: The Best Of Frank Sinatra [Disc 1]",
            "tracks": [
              {
                "track_id": 1033,
                "name": "My Way"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 23,
        "name": "Frank Zappa & Captain Beefheart",
        "albums": [
          {
            "album_id": 31,
            "title": "Bongo Fury",
            "tracks": [
              {
                "track_id": 351,
                "name": "Debra Kadabra"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 251,
        "name": "Fretwork",
        "albums": [
          {
            "album_id": 319,
            "title": "Armada: Music from the Courts of England and Spain",
            "tracks": [
              {
                "track_id": 3453,
                "name": "Pavan, Lachrimae Antiquae"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 86,
        "name": "Funk Como Le Gusta",
        "albums": [
          {
            "album_id": 84,
            "title": "Roda De Funk",
            "tracks": [
              {
                "track_id": 1057,
                "name": "Entrando Na Sua (Intro)"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 69,
        "name": "Gene Krupa",
        "albums": [
          {
            "album_id": 51,
            "title": "Up An' Atom",
            "tracks": [
              {
                "track_id": 624,
                "name": "Jeepers Creepers"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 270,
        "name": "Gerald Moore",
        "albums": [
          {
            "album_id": 341,
            "title": "Great Recordings of the Century - Shubert: Schwanengesang, 4 Lieder",
            "tracks": [
              {
                "track_id": 3497,
                "name": "Erlkonig, D.328"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 27,
        "name": "Gilberto Gil",
        "albums": [
          {
            "album_id": 85,
            "title": "As Canções de Eu Tu Eles",
            "tracks": [
              {
                "track_id": 1073,
                "name": "Óia Eu Aqui De Novo"
              }
            ]
          },
          {
            "album_id": 86,
            "title": "Quanta Gente Veio Ver (Live)",
            "tracks": [
              {
                "track_id": 1087,
                "name": "Introdução (Live)"
              }
            ]
          },
          {
            "album_id": 87,
            "title": "Quanta Gente Veio ver--Bônus De Carnaval",
            "tracks": [
              {
                "track_id": 1102,
                "name": "Doce De Carnaval (Candy All)"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 87,
        "name": "Godsmack",
        "albums": [
          {
            "album_id": 88,
            "title": "Faceless",
            "tracks": [
              {
                "track_id": 1121,
                "name": "Straight Out Of Line"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 56,
        "name": "Gonzaguinha",
        "albums": [
          {
            "album_id": 41,
            "title": "Meus Momentos",
            "tracks": [
              {
                "track_id": 501,
                "name": "Grito De Alerta"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 54,
        "name": "Green Day",
        "albums": [
          {
            "album_id": 89,
            "title": "American Idiot",
            "tracks": [
              {
                "track_id": 1133,
                "name": "American Idiot"
              }
            ]
          },
          {
            "album_id": 39,
            "title": "International Superhits",
            "tracks": [
              {
                "track_id": 468,
                "name": "Maria"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 88,
        "name": "Guns N' Roses",
        "albums": [
          {
            "album_id": 90,
            "title": "Appetite for Destruction",
            "tracks": [
              {
                "track_id": 1146,
                "name": "Welcome to the Jungle"
              }
            ]
          },
          {
            "album_id": 91,
            "title": "Use Your Illusion I",
            "tracks": [
              {
                "track_id": 1158,
                "name": "Right Next Door to Hell"
              }
            ]
          },
          {
            "album_id": 92,
            "title": "Use Your Illusion II",
            "tracks": [
              {
                "track_id": 1174,
                "name": "Civil War"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 240,
        "name": "Gustav Mahler",
        "albums": [
          {
            "album_id": 305,
            "title": "Great Recordings of the Century - Mahler: Das Lied von der Erde",
            "tracks": [
              {
                "track_id": 3439,
                "name": "Das Lied Von Der Erde, Von Der Jugend"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 183,
        "name": "Gustavo & Andres Veiga & Salazar",
        "albums": []
      },
      {
        "artist_id": 267,
        "name": "Göteborgs Symfoniker & Neeme Järvi",
        "albums": [
          {
            "album_id": 338,
            "title": "Nielsen: The Six Symphonies",
            "tracks": [
              {
                "track_id": 3494,
                "name": "Symphony No. 2, Op. 16 -  \"The Four Temperaments\": II. Allegro Comodo e Flemmatico"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 198,
        "name": "Habib Koité and Bamada",
        "albums": [
          {
            "album_id": 263,
            "title": "Muso Ko",
            "tracks": [
              {
                "track_id": 3351,
                "name": "Din Din Wo (Little Child)"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 225,
        "name": "Herbert Von Karajan, Mirella Freni & Wiener Philharmoniker",
        "albums": [
          {
            "album_id": 291,
            "title": "Puccini: Madama Butterfly - Highlights",
            "tracks": [
              {
                "track_id": 3422,
                "name": "Madama Butterfly: Un Bel Dì Vedremo"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 47,
        "name": "Hermeto Pascoal",
        "albums": []
      },
      {
        "artist_id": 148,
        "name": "Heroes",
        "albums": [
          {
            "album_id": 228,
            "title": "Heroes, Season 1",
            "tracks": [
              {
                "track_id": 2839,
                "name": "Genesis"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 210,
        "name": "Hilary Hahn, Jeffrey Kahane, Los Angeles Chamber Orchestra & Margaret Batjer",
        "albums": [
          {
            "album_id": 276,
            "title": "Bach: Violin Concertos",
            "tracks": [
              {
                "track_id": 3407,
                "name": "Concerto for 2 Violins in D Minor, BWV 1043: I. Vivace"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 180,
        "name": "House Of Pain",
        "albums": [
          {
            "album_id": 258,
            "title": "House of Pain",
            "tracks": [
              {
                "track_id": 3300,
                "name": "Jump Around"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 89,
        "name": "Incognito",
        "albums": [
          {
            "album_id": 93,
            "title": "Blue Moods",
            "tracks": [
              {
                "track_id": 1188,
                "name": "Colibri"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 190,
        "name": "Instituto",
        "albums": []
      },
      {
        "artist_id": 90,
        "name": "Iron Maiden",
        "albums": [
          {
            "album_id": 94,
            "title": "A Matter of Life and Death",
            "tracks": [
              {
                "track_id": 1201,
                "name": "Different World"
              }
            ]
          },
          {
            "album_id": 95,
            "title": "A Real Dead One",
            "tracks": [
              {
                "track_id": 1212,
                "name": "The Number Of The Beast"
              }
            ]
          },
          {
            "album_id": 96,
            "title": "A Real Live One",
            "tracks": [
              {
                "track_id": 1224,
                "name": "Be Quick Or Be Dead"
              }
            ]
          },
          {
            "album_id": 97,
            "title": "Brave New World",
            "tracks": [
              {
                "track_id": 1235,
                "name": "The Wicker Man"
              }
            ]
          },
          {
            "album_id": 98,
            "title": "Dance Of Death",
            "tracks": [
              {
                "track_id": 1245,
                "name": "Wildest Dreams"
              }
            ]
          },
          {
            "album_id": 99,
            "title": "Fear Of The Dark",
            "tracks": [
              {
                "track_id": 1256,
                "name": "Be Quick Or Be Dead"
              }
            ]
          },
          {
            "album_id": 100,
            "title": "Iron Maiden",
            "tracks": [
              {
                "track_id": 1268,
                "name": "01 - Prowler"
              }
            ]
          },
          {
            "album_id": 101,
            "title": "Killers",
            "tracks": [
              {
                "track_id": 1277,
                "name": "The Ides Of March"
              }
            ]
          },
          {
            "album_id": 102,
            "title": "Live After Death",
            "tracks": [
              {
                "track_id": 1287,
                "name": "Intro- Churchill S Speech"
              }
            ]
          },
          {
            "album_id": 103,
            "title": "Live At Donington 1992 (Disc 1)",
            "tracks": [
              {
                "track_id": 1305,
                "name": "Be Quick Or Be Dead"
              }
            ]
          },
          {
            "album_id": 104,
            "title": "Live At Donington 1992 (Disc 2)",
            "tracks": [
              {
                "track_id": 1315,
                "name": "Bring Your Daughter... To The Slaughter..."
              }
            ]
          },
          {
            "album_id": 105,
            "title": "No Prayer For The Dying",
            "tracks": [
              {
                "track_id": 1325,
                "name": "Tailgunner"
              }
            ]
          },
          {
            "album_id": 106,
            "title": "Piece Of Mind",
            "tracks": [
              {
                "track_id": 1335,
                "name": "Where Eagles Dare"
              }
            ]
          },
          {
            "album_id": 107,
            "title": "Powerslave",
            "tracks": [
              {
                "track_id": 1344,
                "name": "Aces High"
              }
            ]
          },
          {
            "album_id": 108,
            "title": "Rock In Rio [CD1]",
            "tracks": [
              {
                "track_id": 1352,
                "name": "Intro"
              }
            ]
          },
          {
            "album_id": 109,
            "title": "Rock In Rio [CD2]",
            "tracks": [
              {
                "track_id": 1362,
                "name": "Dream Of Mirrors"
              }
            ]
          },
          {
            "album_id": 110,
            "title": "Seventh Son of a Seventh Son",
            "tracks": [
              {
                "track_id": 1371,
                "name": "Moonchild"
              }
            ]
          },
          {
            "album_id": 111,
            "title": "Somewhere in Time",
            "tracks": [
              {
                "track_id": 1379,
                "name": "Caught Somewhere in Time"
              }
            ]
          },
          {
            "album_id": 112,
            "title": "The Number of The Beast",
            "tracks": [
              {
                "track_id": 1387,
                "name": "22 Acacia Avenue"
              }
            ]
          },
          {
            "album_id": 113,
            "title": "The X Factor",
            "tracks": [
              {
                "track_id": 1395,
                "name": "Sign Of The Cross"
              }
            ]
          },
          {
            "album_id": 114,
            "title": "Virtual XI",
            "tracks": [
              {
                "track_id": 1406,
                "name": "Futureal"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 268,
        "name": "Itzhak Perlman",
        "albums": [
          {
            "album_id": 339,
            "title": "Great Recordings of the Century: Paganini's 24 Caprices",
            "tracks": [
              {
                "track_id": 3495,
                "name": "24 Caprices, Op. 1, No. 24, for Solo Violin, in A Minor"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 93,
        "name": "JET",
        "albums": [
          {
            "album_id": 119,
            "title": "Get Born",
            "tracks": [
              {
                "track_id": 1466,
                "name": "Last Chance"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 170,
        "name": "Jack Johnson",
        "albums": []
      },
      {
        "artist_id": 177,
        "name": "Jack's Mannequin & Mick Fleetwood",
        "albums": []
      },
      {
        "artist_id": 165,
        "name": "Jackson Browne",
        "albums": []
      },
      {
        "artist_id": 175,
        "name": "Jaguares",
        "albums": []
      },
      {
        "artist_id": 91,
        "name": "James Brown",
        "albums": [
          {
            "album_id": 115,
            "title": "Sex Machine",
            "tracks": [
              {
                "track_id": 1414,
                "name": "Please Please Please"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 236,
        "name": "James Levine",
        "albums": [
          {
            "album_id": 302,
            "title": "Mascagni: Cavalleria Rusticana",
            "tracks": [
              {
                "track_id": 3435,
                "name": "Cavalleria Rusticana \\ Act \\ Intermezzo Sinfonico"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 92,
        "name": "Jamiroquai",
        "albums": [
          {
            "album_id": 116,
            "title": "Emergency On Planet Earth",
            "tracks": [
              {
                "track_id": 1434,
                "name": "When You Gonna Learn (Digeridoo)"
              }
            ]
          },
          {
            "album_id": 117,
            "title": "Synkronized",
            "tracks": [
              {
                "track_id": 1444,
                "name": "Canned Heat"
              }
            ]
          },
          {
            "album_id": 118,
            "title": "The Return Of The Space Cowboy",
            "tracks": [
              {
                "track_id": 1455,
                "name": "Just Another Story"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 94,
        "name": "Jimi Hendrix",
        "albums": [
          {
            "album_id": 120,
            "title": "Are You Experienced?",
            "tracks": [
              {
                "track_id": 1479,
                "name": "Foxy Lady"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 95,
        "name": "Joe Satriani",
        "albums": [
          {
            "album_id": 121,
            "title": "Surfing with the Alien (Remastered)",
            "tracks": [
              {
                "track_id": 1496,
                "name": "Surfing with the Alien"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 46,
        "name": "Jorge Ben",
        "albums": [
          {
            "album_id": 122,
            "title": "Jorge Ben Jor 25 Anos",
            "tracks": [
              {
                "track_id": 1506,
                "name": "Engenho De Dentro"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 30,
        "name": "Jorge Vercilo",
        "albums": []
      },
      {
        "artist_id": 96,
        "name": "Jota Quest",
        "albums": [
          {
            "album_id": 123,
            "title": "Jota Quest-1995",
            "tracks": [
              {
                "track_id": 1520,
                "name": "Rapidamente"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 28,
        "name": "João Gilberto",
        "albums": []
      },
      {
        "artist_id": 97,
        "name": "João Suplicy",
        "albums": [
          {
            "album_id": 124,
            "title": "Cafezinho",
            "tracks": [
              {
                "track_id": 1532,
                "name": "Pura Elegancia"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 98,
        "name": "Judas Priest",
        "albums": [
          {
            "album_id": 125,
            "title": "Living After Midnight",
            "tracks": [
              {
                "track_id": 1546,
                "name": "The Green Manalishi"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 265,
        "name": "Julian Bream",
        "albums": [
          {
            "album_id": 335,
            "title": "J.S. Bach: Chaconne, Suite in E Minor, Partita in E Major & Prelude, Fugue and Allegro",
            "tracks": [
              {
                "track_id": 3490,
                "name": "Partita in E Major, BWV 1006A: I. Prelude"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 199,
        "name": "Karsh Kale",
        "albums": [
          {
            "album_id": 264,
            "title": "Realize",
            "tracks": [
              {
                "track_id": 3352,
                "name": "Distance"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 264,
        "name": "Kent Nagano and Orchestre de l'Opéra de Lyon",
        "albums": [
          {
            "album_id": 334,
            "title": "Weill: The Seven Deadly Sins",
            "tracks": [
              {
                "track_id": 3489,
                "name": "Symphony No. 2: III. Allegro vivace"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 44,
        "name": "Kid Abelha",
        "albums": []
      },
      {
        "artist_id": 52,
        "name": "Kiss",
        "albums": [
          {
            "album_id": 37,
            "title": "Greatest Kiss",
            "tracks": [
              {
                "track_id": 436,
                "name": "Detroit Rock City"
              }
            ]
          },
          {
            "album_id": 126,
            "title": "Unplugged [Live]",
            "tracks": [
              {
                "track_id": 1562,
                "name": "Comin' Home"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 22,
        "name": "Led Zeppelin",
        "albums": [
          {
            "album_id": 30,
            "title": "BBC Sessions [Disc 1] [Live]",
            "tracks": [
              {
                "track_id": 337,
                "name": "You Shook Me"
              }
            ]
          },
          {
            "album_id": 127,
            "title": "BBC Sessions [Disc 2] [Live]",
            "tracks": [
              {
                "track_id": 1577,
                "name": "Immigrant Song"
              }
            ]
          },
          {
            "album_id": 128,
            "title": "Coda",
            "tracks": [
              {
                "track_id": 1587,
                "name": "We're Gonna Groove"
              }
            ]
          },
          {
            "album_id": 129,
            "title": "Houses Of The Holy",
            "tracks": [
              {
                "track_id": 1595,
                "name": "The Song Remains The Same"
              }
            ]
          },
          {
            "album_id": 131,
            "title": "IV",
            "tracks": [
              {
                "track_id": 1610,
                "name": "Black Dog"
              }
            ]
          },
          {
            "album_id": 130,
            "title": "In Through The Out Door",
            "tracks": [
              {
                "track_id": 1603,
                "name": "In The Evening"
              }
            ]
          },
          {
            "album_id": 132,
            "title": "Led Zeppelin I",
            "tracks": [
              {
                "track_id": 1618,
                "name": "Good Times Bad Times"
              }
            ]
          },
          {
            "album_id": 133,
            "title": "Led Zeppelin II",
            "tracks": [
              {
                "track_id": 1627,
                "name": "Whole Lotta Love"
              }
            ]
          },
          {
            "album_id": 134,
            "title": "Led Zeppelin III",
            "tracks": [
              {
                "track_id": 1636,
                "name": "Immigrant Song"
              }
            ]
          },
          {
            "album_id": 44,
            "title": "Physical Graffiti [Disc 1]",
            "tracks": [
              {
                "track_id": 550,
                "name": "Custard Pie"
              }
            ]
          },
          {
            "album_id": 135,
            "title": "Physical Graffiti [Disc 2]",
            "tracks": [
              {
                "track_id": 1646,
                "name": "In The Light"
              }
            ]
          },
          {
            "album_id": 136,
            "title": "Presence",
            "tracks": [
              {
                "track_id": 1655,
                "name": "Achilles Last Stand"
              }
            ]
          },
          {
            "album_id": 137,
            "title": "The Song Remains The Same (Disc 1)",
            "tracks": [
              {
                "track_id": 1662,
                "name": "Rock & Roll"
              }
            ]
          },
          {
            "album_id": 138,
            "title": "The Song Remains The Same (Disc 2)",
            "tracks": [
              {
                "track_id": 1667,
                "name": "No Quarter"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 99,
        "name": "Legião Urbana",
        "albums": [
          {
            "album_id": 139,
            "title": "A TempestadeTempestade Ou O Livro Dos Dias",
            "tracks": [
              {
                "track_id": 1671,
                "name": "Natália"
              }
            ]
          },
          {
            "album_id": 140,
            "title": "Mais Do Mesmo",
            "tracks": [
              {
                "track_id": 1686,
                "name": "Será"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 100,
        "name": "Lenny Kravitz",
        "albums": [
          {
            "album_id": 141,
            "title": "Greatest Hits",
            "tracks": [
              {
                "track_id": 1702,
                "name": "Are You Gonna Go My Way"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 228,
        "name": "Leonard Bernstein & New York Philharmonic",
        "albums": [
          {
            "album_id": 294,
            "title": "Great Performances - Barber's Adagio and Other Romantic Favorites for Strings",
            "tracks": [
              {
                "track_id": 3425,
                "name": "Adagio for Strings from the String Quartet, Op. 11"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 258,
        "name": "Les Arts Florissants & William Christie",
        "albums": [
          {
            "album_id": 328,
            "title": "Charpentier: Divertissements, Airs & Concerts",
            "tracks": [
              {
                "track_id": 3483,
                "name": "Concert pour 4 Parties de V**les, H. 545: I. Prelude"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 223,
        "name": "London Symphony Orchestra & Sir Charles Mackerras",
        "albums": [
          {
            "album_id": 289,
            "title": "Tchaikovsky: The Nutcracker",
            "tracks": [
              {
                "track_id": 3420,
                "name": "The Nutcracker, Op. 71a, Act II: Scene 14: Pas de deux: Dance of the Prince & the Sugar-Plum Fairy"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 187,
        "name": "Los Hermanos",
        "albums": []
      },
      {
        "artist_id": 162,
        "name": "Los Lonely Boys",
        "albums": []
      },
      {
        "artist_id": 149,
        "name": "Lost",
        "albums": [
          {
            "album_id": 261,
            "title": "LOST, Season 4",
            "tracks": [
              {
                "track_id": 3337,
                "name": "Past, Present, and Future"
              }
            ]
          },
          {
            "album_id": 230,
            "title": "Lost, Season 1",
            "tracks": [
              {
                "track_id": 2858,
                "name": "Lost (Pilot, Part 1) [Premiere]"
              }
            ]
          },
          {
            "album_id": 231,
            "title": "Lost, Season 2",
            "tracks": [
              {
                "track_id": 2859,
                "name": "Man of Science, Man of Faith (Premiere)"
              }
            ]
          },
          {
            "album_id": 229,
            "title": "Lost, Season 3",
            "tracks": [
              {
                "track_id": 2857,
                "name": "A Tale of Two Cities"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 201,
        "name": "Luciana Souza/Romero Lubambo",
        "albums": [
          {
            "album_id": 266,
            "title": "Duos II",
            "tracks": [
              {
                "track_id": 3356,
                "name": "Muita Bobeira"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 227,
        "name": "Luciano Pavarotti",
        "albums": [
          {
            "album_id": 293,
            "title": "Pavarotti's Opera Made Easy",
            "tracks": [
              {
                "track_id": 3424,
                "name": "Turandot, Act III, Nessun dorma!"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 33,
        "name": "Luiz Melodia",
        "albums": []
      },
      {
        "artist_id": 101,
        "name": "Lulu Santos",
        "albums": [
          {
            "album_id": 142,
            "title": "Lulu Santos - RCA 100 Anos De Música - Álbum 01",
            "tracks": [
              {
                "track_id": 1717,
                "name": "Assim Caminha A Humanidade"
              }
            ]
          },
          {
            "album_id": 143,
            "title": "Lulu Santos - RCA 100 Anos De Música - Álbum 02",
            "tracks": [
              {
                "track_id": 1718,
                "name": "Honolulu"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 24,
        "name": "Marcos Valle",
        "albums": [
          {
            "album_id": 33,
            "title": "Chill: Brazil (Disc 1)",
            "tracks": [
              {
                "track_id": 374,
                "name": "Guanabara"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 102,
        "name": "Marillion",
        "albums": [
          {
            "album_id": 144,
            "title": "Misplaced Childhood",
            "tracks": [
              {
                "track_id": 1745,
                "name": "Pseudo Silk Kimono"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 103,
        "name": "Marisa Monte",
        "albums": [
          {
            "album_id": 145,
            "title": "Barulhinho Bom",
            "tracks": [
              {
                "track_id": 1755,
                "name": "Arrepio"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 266,
        "name": "Martin Roscoe",
        "albums": [
          {
            "album_id": 337,
            "title": "Szymanowski: Piano Works, Vol. 1",
            "tracks": [
              {
                "track_id": 3493,
                "name": "Metopes, Op. 29: Calypso"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 104,
        "name": "Marvin Gaye",
        "albums": [
          {
            "album_id": 146,
            "title": "Seek And Shall Find: More Of The Best (1963-1981)",
            "tracks": [
              {
                "track_id": 1773,
                "name": "Wherever I Lay My Hat"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 173,
        "name": "Matisyahu",
        "albums": []
      },
      {
        "artist_id": 238,
        "name": "Maurizio Pollini",
        "albums": [
          {
            "album_id": 304,
            "title": "Beethoven Piano Sonatas: Moonlight & Pastorale",
            "tracks": [
              {
                "track_id": 3437,
                "name": "Piano Sonata No. 14 in C Sharp Minor, Op. 27, No. 2, \"Moonlight\": I. Adagio sostenuto"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 271,
        "name": "Mela Tenenbaum, Pro Musica Prague & Richard Kapp",
        "albums": [
          {
            "album_id": 342,
            "title": "Locatelli: Concertos for Violin, Strings and Continuo, Vol. 3",
            "tracks": [
              {
                "track_id": 3498,
                "name": "Concerto for Violin, Strings and Continuo in G Major, Op. 3, No. 9: I. Allegro"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 105,
        "name": "Men At Work",
        "albums": [
          {
            "album_id": 147,
            "title": "The Best Of Men At Work",
            "tracks": [
              {
                "track_id": 1791,
                "name": "Down Under"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 50,
        "name": "Metallica",
        "albums": [
          {
            "album_id": 156,
            "title": "...And Justice For All",
            "tracks": [
              {
                "track_id": 1893,
                "name": "Blackened"
              }
            ]
          },
          {
            "album_id": 148,
            "title": "Black Album",
            "tracks": [
              {
                "track_id": 1801,
                "name": "Enter Sandman"
              }
            ]
          },
          {
            "album_id": 35,
            "title": "Garage Inc. (Disc 1)",
            "tracks": [
              {
                "track_id": 408,
                "name": "Free Speech For The Dumb"
              }
            ]
          },
          {
            "album_id": 149,
            "title": "Garage Inc. (Disc 2)",
            "tracks": [
              {
                "track_id": 1813,
                "name": "Helpless"
              }
            ]
          },
          {
            "album_id": 150,
            "title": "Kill 'Em All",
            "tracks": [
              {
                "track_id": 1829,
                "name": "Hit The Lights"
              }
            ]
          },
          {
            "album_id": 151,
            "title": "Load",
            "tracks": [
              {
                "track_id": 1839,
                "name": "Ain't My Bitch"
              }
            ]
          },
          {
            "album_id": 152,
            "title": "Master Of Puppets",
            "tracks": [
              {
                "track_id": 1853,
                "name": "Battery"
              }
            ]
          },
          {
            "album_id": 153,
            "title": "ReLoad",
            "tracks": [
              {
                "track_id": 1861,
                "name": "Fuel"
              }
            ]
          },
          {
            "album_id": 154,
            "title": "Ride The Lightning",
            "tracks": [
              {
                "track_id": 1874,
                "name": "Fight Fire With Fire"
              }
            ]
          },
          {
            "album_id": 155,
            "title": "St. Anger",
            "tracks": [
              {
                "track_id": 1882,
                "name": "Frantic"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 245,
        "name": "Michael Tilson Thomas & San Francisco Symphony",
        "albums": [
          {
            "album_id": 312,
            "title": "Berlioz: Symphonie Fantastique",
            "tracks": [
              {
                "track_id": 3446,
                "name": "Symphonie Fantastique, Op. 14: V. Songe d'une nuit du sabbat"
              }
            ]
          },
          {
            "album_id": 310,
            "title": "Prokofiev: Romeo & Juliet",
            "tracks": [
              {
                "track_id": 3444,
                "name": "Romeo et Juliette: No. 11 - Danse des Chevaliers"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 269,
        "name": "Michele Campanella",
        "albums": [
          {
            "album_id": 340,
            "title": "Liszt - 12 Études D'Execution Transcendante",
            "tracks": [
              {
                "track_id": 3496,
                "name": "Étude 1, In C Major - Preludio (Presto) - Liszt"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 68,
        "name": "Miles Davis",
        "albums": [
          {
            "album_id": 157,
            "title": "Miles Ahead",
            "tracks": [
              {
                "track_id": 1902,
                "name": "Springsville"
              }
            ]
          },
          {
            "album_id": 48,
            "title": "The Essential Miles Davis [Disc 1]",
            "tracks": [
              {
                "track_id": 597,
                "name": "Now's The Time"
              }
            ]
          },
          {
            "album_id": 49,
            "title": "The Essential Miles Davis [Disc 2]",
            "tracks": [
              {
                "track_id": 610,
                "name": "My Funny Valentine (Live)"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 42,
        "name": "Milton Nascimento",
        "albums": [
          {
            "album_id": 158,
            "title": "Milton Nascimento Ao Vivo",
            "tracks": [
              {
                "track_id": 1916,
                "name": "Coração De Estudante"
              }
            ]
          },
          {
            "album_id": 159,
            "title": "Minas",
            "tracks": [
              {
                "track_id": 1929,
                "name": "Minas"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 25,
        "name": "Milton Nascimento & Bebeto",
        "albums": []
      },
      {
        "artist_id": 106,
        "name": "Motörhead",
        "albums": [
          {
            "album_id": 160,
            "title": "Ace Of Spades",
            "tracks": [
              {
                "track_id": 1942,
                "name": "Ace Of Spades"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 107,
        "name": "Motörhead & Girlschool",
        "albums": []
      },
      {
        "artist_id": 188,
        "name": "Mundo Livre S/A",
        "albums": []
      },
      {
        "artist_id": 108,
        "name": "Mônica Marianno",
        "albums": [
          {
            "album_id": 161,
            "title": "Demorou...",
            "tracks": [
              {
                "track_id": 1957,
                "name": "Kir Royal"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 109,
        "name": "Mötley Crüe",
        "albums": [
          {
            "album_id": 162,
            "title": "Motley Crue Greatest Hits",
            "tracks": [
              {
                "track_id": 1969,
                "name": "Bitter Pill"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 34,
        "name": "Nando Reis",
        "albums": []
      },
      {
        "artist_id": 274,
        "name": "Nash Ensemble",
        "albums": [
          {
            "album_id": 346,
            "title": "Mozart: Chamber Music",
            "tracks": [
              {
                "track_id": 3502,
                "name": "Quintet for Horn, Violin, 2 Violas, and Cello in E Flat Major, K. 407/386c: III. Allegro"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 191,
        "name": "Nação Zumbi",
        "albums": []
      },
      {
        "artist_id": 182,
        "name": "Nega Gizza",
        "albums": []
      },
      {
        "artist_id": 32,
        "name": "Ney Matogrosso",
        "albums": []
      },
      {
        "artist_id": 203,
        "name": "Nicolaus Esterhazy Sinfonia",
        "albums": [
          {
            "album_id": 268,
            "title": "The Best of Beethoven",
            "tracks": [
              {
                "track_id": 3359,
                "name": "Symphony No. 3 in E-flat major, Op. 55, \"Eroica\" - Scherzo: Allegro Vivace"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 110,
        "name": "Nirvana",
        "albums": [
          {
            "album_id": 163,
            "title": "From The Muddy Banks Of The Wishkah [Live]",
            "tracks": [
              {
                "track_id": 1986,
                "name": "Intro"
              }
            ]
          },
          {
            "album_id": 164,
            "title": "Nevermind",
            "tracks": [
              {
                "track_id": 2003,
                "name": "Smells Like Teen Spirit"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 36,
        "name": "O Rappa",
        "albums": [
          {
            "album_id": 259,
            "title": "Radio Brasil (O Som da Jovem Vanguarda) - Seleccao de Henrique Amaro",
            "tracks": [
              {
                "track_id": 3319,
                "name": "Instinto Colectivo"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 111,
        "name": "O Terço",
        "albums": [
          {
            "album_id": 165,
            "title": "Compositores",
            "tracks": [
              {
                "track_id": 2015,
                "name": "Time"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 112,
        "name": "Olodum",
        "albums": [
          {
            "album_id": 166,
            "title": "Olodum",
            "tracks": [
              {
                "track_id": 2030,
                "name": "Requebra"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 234,
        "name": "Orchestra of The Age of Enlightenment",
        "albums": [
          {
            "album_id": 300,
            "title": "Bach: The Brandenburg Concertos",
            "tracks": [
              {
                "track_id": 3433,
                "name": "Concerto No.2 in F Major, BWV1047, I. Allegro"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 218,
        "name": "Orchestre Révolutionnaire et Romantique & John Eliot Gardiner",
        "albums": [
          {
            "album_id": 284,
            "title": "Beethoven: Symhonies Nos. 5 & 6",
            "tracks": [
              {
                "track_id": 3415,
                "name": "Symphony No.5 in C Minor: I. Allegro con brio"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 40,
        "name": "Os Cariocas",
        "albums": []
      },
      {
        "artist_id": 57,
        "name": "Os Mutantes",
        "albums": [
          {
            "album_id": 42,
            "title": "Minha História",
            "tracks": [
              {
                "track_id": 529,
                "name": "Balada Do Louco"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 113,
        "name": "Os Paralamas Do Sucesso",
        "albums": [
          {
            "album_id": 167,
            "title": "Acústico MTV",
            "tracks": [
              {
                "track_id": 2044,
                "name": "Vulcão Dub - Fui Eu"
              }
            ]
          },
          {
            "album_id": 168,
            "title": "Arquivo II",
            "tracks": [
              {
                "track_id": 2065,
                "name": "Trac Trac"
              }
            ]
          },
          {
            "album_id": 169,
            "title": "Arquivo Os Paralamas Do Sucesso",
            "tracks": [
              {
                "track_id": 2077,
                "name": "Caleidoscópio"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 189,
        "name": "Otto",
        "albums": []
      },
      {
        "artist_id": 254,
        "name": "Otto Klemperer & Philharmonia Orchestra",
        "albums": [
          {
            "album_id": 324,
            "title": "Beethoven: Symphony No. 6 'Pastoral' Etc.",
            "tracks": [
              {
                "track_id": 3479,
                "name": "Prometheus Overture, Op. 43"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 114,
        "name": "Ozzy Osbourne",
        "albums": [
          {
            "album_id": 170,
            "title": "Bark at the Moon (Remastered)",
            "tracks": [
              {
                "track_id": 2093,
                "name": "Bark at the Moon"
              }
            ]
          },
          {
            "album_id": 171,
            "title": "Blizzard of Ozz",
            "tracks": [
              {
                "track_id": 2094,
                "name": "I Don't Know"
              }
            ]
          },
          {
            "album_id": 172,
            "title": "Diary of a Madman (Remastered)",
            "tracks": [
              {
                "track_id": 2096,
                "name": "Flying High Again"
              }
            ]
          },
          {
            "album_id": 173,
            "title": "No More Tears (Remastered)",
            "tracks": [
              {
                "track_id": 2097,
                "name": "Mama, I'm Coming Home"
              }
            ]
          },
          {
            "album_id": 256,
            "title": "Speak of the Devil",
            "tracks": [
              {
                "track_id": 3276,
                "name": "Sympton of the Universe"
              }
            ]
          },
          {
            "album_id": 174,
            "title": "Tribute",
            "tracks": [
              {
                "track_id": 2099,
                "name": "I Don't Know"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 115,
        "name": "Page & Plant",
        "albums": [
          {
            "album_id": 175,
            "title": "Walking Into Clarksdale",
            "tracks": [
              {
                "track_id": 2113,
                "name": "Shining In The Light"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 116,
        "name": "Passengers",
        "albums": [
          {
            "album_id": 176,
            "title": "Original Soundtracks 1",
            "tracks": [
              {
                "track_id": 2125,
                "name": "United Colours"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 117,
        "name": "Paul D'Ianno",
        "albums": [
          {
            "album_id": 177,
            "title": "The Beast Live",
            "tracks": [
              {
                "track_id": 2139,
                "name": "Wrathchild"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 118,
        "name": "Pearl Jam",
        "albums": [
          {
            "album_id": 178,
            "title": "Live On Two Legs [Live]",
            "tracks": [
              {
                "track_id": 2149,
                "name": "Corduroy"
              }
            ]
          },
          {
            "album_id": 179,
            "title": "Pearl Jam",
            "tracks": [
              {
                "track_id": 2165,
                "name": "Life Wasted"
              }
            ]
          },
          {
            "album_id": 180,
            "title": "Riot Act",
            "tracks": [
              {
                "track_id": 2178,
                "name": "Can't Keep"
              }
            ]
          },
          {
            "album_id": 181,
            "title": "Ten",
            "tracks": [
              {
                "track_id": 2193,
                "name": "Once"
              }
            ]
          },
          {
            "album_id": 182,
            "title": "Vs.",
            "tracks": [
              {
                "track_id": 2204,
                "name": "Go"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 35,
        "name": "Pedro Luís & A Parede",
        "albums": []
      },
      {
        "artist_id": 186,
        "name": "Pedro Luís E A Parede",
        "albums": []
      },
      {
        "artist_id": 119,
        "name": "Peter Tosh",
        "albums": []
      },
      {
        "artist_id": 256,
        "name": "Philharmonia Orchestra & Sir Neville Marriner",
        "albums": [
          {
            "album_id": 326,
            "title": "Mendelssohn: A Midsummer Night's Dream",
            "tracks": [
              {
                "track_id": 3481,
                "name": "A Midsummer Night's Dream, Op.61 Incidental Music: No.7 Notturno"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 275,
        "name": "Philip Glass Ensemble",
        "albums": [
          {
            "album_id": 347,
            "title": "Koyaanisqatsi (Soundtrack from the Motion Picture)",
            "tracks": [
              {
                "track_id": 3503,
                "name": "Koyaanisqatsi"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 120,
        "name": "Pink Floyd",
        "albums": [
          {
            "album_id": 183,
            "title": "Dark Side Of The Moon",
            "tracks": [
              {
                "track_id": 2229,
                "name": "Speak To Me/Breathe"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 121,
        "name": "Planet Hemp",
        "albums": [
          {
            "album_id": 184,
            "title": "Os Cães Ladram Mas A Caravana Não Pára",
            "tracks": [
              {
                "track_id": 2238,
                "name": "ZeroVinteUm"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 51,
        "name": "Queen",
        "albums": [
          {
            "album_id": 185,
            "title": "Greatest Hits I",
            "tracks": [
              {
                "track_id": 2254,
                "name": "Bohemian Rhapsody"
              }
            ]
          },
          {
            "album_id": 36,
            "title": "Greatest Hits II",
            "tracks": [
              {
                "track_id": 419,
                "name": "A Kind Of Magic"
              }
            ]
          },
          {
            "album_id": 186,
            "title": "News Of The World",
            "tracks": [
              {
                "track_id": 2271,
                "name": "We Will Rock You"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 124,
        "name": "R.E.M.",
        "albums": [
          {
            "album_id": 188,
            "title": "Green",
            "tracks": [
              {
                "track_id": 2285,
                "name": "Pop Song 89"
              }
            ]
          },
          {
            "album_id": 189,
            "title": "New Adventures In Hi-Fi",
            "tracks": [
              {
                "track_id": 2296,
                "name": "How The West Was Won And Where It Got Us"
              }
            ]
          },
          {
            "album_id": 190,
            "title": "The Best Of R.E.M.: The IRS Years",
            "tracks": [
              {
                "track_id": 2318,
                "name": "Carnival Of Sorts"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 123,
        "name": "R.E.M. Feat. KRS-One",
        "albums": []
      },
      {
        "artist_id": 122,
        "name": "R.E.M. Feat. Kate Pearson",
        "albums": [
          {
            "album_id": 187,
            "title": "Out Of Time",
            "tracks": [
              {
                "track_id": 2282,
                "name": "Shiny Happy People"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 125,
        "name": "Raimundos",
        "albums": [
          {
            "album_id": 191,
            "title": "Cesta Básica",
            "tracks": [
              {
                "track_id": 2334,
                "name": "Infeliz Natal"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 126,
        "name": "Raul Seixas",
        "albums": [
          {
            "album_id": 192,
            "title": "Raul Seixas",
            "tracks": [
              {
                "track_id": 2344,
                "name": "Maluco Beleza"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 127,
        "name": "Red Hot Chili Peppers",
        "albums": [
          {
            "album_id": 193,
            "title": "Blood Sugar Sex Magik",
            "tracks": [
              {
                "track_id": 2358,
                "name": "The Power Of Equality"
              }
            ]
          },
          {
            "album_id": 194,
            "title": "By The Way",
            "tracks": [
              {
                "track_id": 2375,
                "name": "By The Way"
              }
            ]
          },
          {
            "album_id": 195,
            "title": "Californication",
            "tracks": [
              {
                "track_id": 2391,
                "name": "Around The World"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 178,
        "name": "Regina Spektor",
        "albums": []
      },
      {
        "artist_id": 207,
        "name": "Richard Marlow & The Choir of Trinity College, Cambridge",
        "albums": [
          {
            "album_id": 273,
            "title": "Allegri: Miserere",
            "tracks": [
              {
                "track_id": 3404,
                "name": "Miserere mei, Deus"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 184,
        "name": "Rodox",
        "albums": []
      },
      {
        "artist_id": 261,
        "name": "Roger Norrington, London Classical Players",
        "albums": [
          {
            "album_id": 331,
            "title": "Purcell: The Fairy Queen",
            "tracks": [
              {
                "track_id": 3486,
                "name": "Act IV, Symphony"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 217,
        "name": "Royal Philharmonic Orchestra & Sir Thomas Beecham",
        "albums": [
          {
            "album_id": 283,
            "title": "Haydn: Symphonies 99 - 104",
            "tracks": [
              {
                "track_id": 3414,
                "name": "Symphony No. 104 in D Major \"London\": IV. Finale: Spiritoso"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 128,
        "name": "Rush",
        "albums": [
          {
            "album_id": 196,
            "title": "Retrospective I (1974-1980)",
            "tracks": [
              {
                "track_id": 2406,
                "name": "The Spirit Of Radio"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 194,
        "name": "Sabotage E Instituto",
        "albums": []
      },
      {
        "artist_id": 45,
        "name": "Sandra De Sá",
        "albums": []
      },
      {
        "artist_id": 59,
        "name": "Santana",
        "albums": [
          {
            "album_id": 197,
            "title": "Santana - As Years Go By",
            "tracks": [
              {
                "track_id": 2420,
                "name": "Jingo"
              }
            ]
          },
          {
            "album_id": 198,
            "title": "Santana Live",
            "tracks": [
              {
                "track_id": 2428,
                "name": "Evil Ways"
              }
            ]
          },
          {
            "album_id": 46,
            "title": "Supernatural",
            "tracks": [
              {
                "track_id": 570,
                "name": "(Da Le) Yaleo"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 60,
        "name": "Santana Feat. Dave Matthews",
        "albums": []
      },
      {
        "artist_id": 66,
        "name": "Santana Feat. Eagle-Eye Cherry",
        "albums": []
      },
      {
        "artist_id": 67,
        "name": "Santana Feat. Eric Clapton",
        "albums": []
      },
      {
        "artist_id": 61,
        "name": "Santana Feat. Everlast",
        "albums": []
      },
      {
        "artist_id": 63,
        "name": "Santana Feat. Lauryn Hill & Cee-Lo",
        "albums": []
      },
      {
        "artist_id": 65,
        "name": "Santana Feat. Maná",
        "albums": []
      },
      {
        "artist_id": 62,
        "name": "Santana Feat. Rob Thomas",
        "albums": []
      },
      {
        "artist_id": 64,
        "name": "Santana Feat. The Project G&B",
        "albums": []
      },
      {
        "artist_id": 213,
        "name": "Scholars Baroque Ensemble",
        "albums": [
          {
            "album_id": 279,
            "title": "Handel: The Messiah (Highlights)",
            "tracks": [
              {
                "track_id": 3410,
                "name": "The Messiah: Behold, I Tell You a Mystery... The Trumpet Shall Sound"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 179,
        "name": "Scorpions",
        "albums": [
          {
            "album_id": 257,
            "title": "20th Century Masters - The Millennium Collection: The Best of Scorpions",
            "tracks": [
              {
                "track_id": 3288,
                "name": "Rock You Like a Hurricane"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 232,
        "name": "Sergei Prokofiev & Yuri Temirkanov",
        "albums": [
          {
            "album_id": 298,
            "title": "Prokofiev: Symphony No.1",
            "tracks": [
              {
                "track_id": 3431,
                "name": "Symphony No.1 in D Major, Op.25 \"Classical\", Allegro Con Brio"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 193,
        "name": "Seu Jorge",
        "albums": []
      },
      {
        "artist_id": 129,
        "name": "Simply Red",
        "albums": []
      },
      {
        "artist_id": 221,
        "name": "Sir Georg Solti & Wiener Philharmoniker",
        "albums": [
          {
            "album_id": 287,
            "title": "Wagner: Favourite Overtures",
            "tracks": [
              {
                "track_id": 3418,
                "name": "Die Walküre: The Ride of the Valkyries"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 249,
        "name": "Sir Georg Solti, Sumi Jo & Wiener Philharmoniker",
        "albums": [
          {
            "album_id": 317,
            "title": "Mozart Gala: Famous Arias",
            "tracks": [
              {
                "track_id": 3451,
                "name": "Die Zauberflöte, K.620: \"Der Hölle Rache Kocht in Meinem Herze\""
              }
            ]
          }
        ]
      },
      {
        "artist_id": 130,
        "name": "Skank",
        "albums": [
          {
            "album_id": 199,
            "title": "Maquinarama",
            "tracks": [
              {
                "track_id": 2449,
                "name": "Água E Fogo"
              }
            ]
          },
          {
            "album_id": 200,
            "title": "O Samba Poconé",
            "tracks": [
              {
                "track_id": 2461,
                "name": "É Uma Partida De Futebol"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 131,
        "name": "Smashing Pumpkins",
        "albums": [
          {
            "album_id": 201,
            "title": "Judas 0: B-Sides and Rarities",
            "tracks": [
              {
                "track_id": 2472,
                "name": "Lucky 13"
              }
            ]
          },
          {
            "album_id": 202,
            "title": "Rotten Apples: Greatest Hits",
            "tracks": [
              {
                "track_id": 2488,
                "name": "Siva"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 172,
        "name": "Snow Patrol",
        "albums": []
      },
      {
        "artist_id": 132,
        "name": "Soundgarden",
        "albums": [
          {
            "album_id": 203,
            "title": "A-Sides",
            "tracks": [
              {
                "track_id": 2506,
                "name": "Nothing To Say"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 53,
        "name": "Spyro Gyra",
        "albums": [
          {
            "album_id": 38,
            "title": "Heart of the Night",
            "tracks": [
              {
                "track_id": 456,
                "name": "Heart of the Night"
              }
            ]
          },
          {
            "album_id": 204,
            "title": "Morning Dance",
            "tracks": [
              {
                "track_id": 2523,
                "name": "Morning Dance"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 195,
        "name": "Stereo Maracana",
        "albums": []
      },
      {
        "artist_id": 133,
        "name": "Stevie Ray Vaughan & Double Trouble",
        "albums": [
          {
            "album_id": 205,
            "title": "In Step",
            "tracks": [
              {
                "track_id": 2532,
                "name": "The House Is Rockin'"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 134,
        "name": "Stone Temple Pilots",
        "albums": [
          {
            "album_id": 206,
            "title": "Core",
            "tracks": [
              {
                "track_id": 2542,
                "name": "Dead And Bloated"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 135,
        "name": "System Of A Down",
        "albums": [
          {
            "album_id": 207,
            "title": "Mezmerize",
            "tracks": [
              {
                "track_id": 2554,
                "name": "Soldier Side - Intro"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 204,
        "name": "Temple of the Dog",
        "albums": [
          {
            "album_id": 269,
            "title": "Temple of the Dog",
            "tracks": [
              {
                "track_id": 3365,
                "name": "Say Hello 2 Heaven"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 136,
        "name": "Terry Bozzio, Tony Levin & Steve Stevens",
        "albums": [
          {
            "album_id": 208,
            "title": "[1997] Black Light Syndrome",
            "tracks": [
              {
                "track_id": 2565,
                "name": "The Sun Road"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 259,
        "name": "The 12 Cellists of The Berlin Philharmonic",
        "albums": [
          {
            "album_id": 329,
            "title": "South American Getaway",
            "tracks": [
              {
                "track_id": 3484,
                "name": "Adios nonino"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 137,
        "name": "The Black Crowes",
        "albums": [
          {
            "album_id": 209,
            "title": "Live [Disc 1]",
            "tracks": [
              {
                "track_id": 2572,
                "name": "Midnight From The Inside Out"
              }
            ]
          },
          {
            "album_id": 210,
            "title": "Live [Disc 2]",
            "tracks": [
              {
                "track_id": 2582,
                "name": "Black Moon Creeping"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 138,
        "name": "The Clash",
        "albums": [
          {
            "album_id": 211,
            "title": "The Singles",
            "tracks": [
              {
                "track_id": 2591,
                "name": "White Riot"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 139,
        "name": "The Cult",
        "albums": [
          {
            "album_id": 212,
            "title": "Beyond Good And Evil",
            "tracks": [
              {
                "track_id": 2609,
                "name": "War (The Process)"
              }
            ]
          },
          {
            "album_id": 213,
            "title": "Pure Cult: The Best Of The Cult (For Rockers, Ravers, Lovers & Sinners) [UK]",
            "tracks": [
              {
                "track_id": 2621,
                "name": "She Sells Sanctuary"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 140,
        "name": "The Doors",
        "albums": [
          {
            "album_id": 214,
            "title": "The Doors",
            "tracks": [
              {
                "track_id": 2639,
                "name": "Break on Through"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 176,
        "name": "The Flaming Lips",
        "albums": []
      },
      {
        "artist_id": 247,
        "name": "The King's Singers",
        "albums": [
          {
            "album_id": 314,
            "title": "English Renaissance",
            "tracks": [
              {
                "track_id": 3448,
                "name": "Lamentations of Jeremiah, First Set \\ Incipit Lamentatio"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 156,
        "name": "The Office",
        "albums": [
          {
            "album_id": 249,
            "title": "The Office, Season 1",
            "tracks": [
              {
                "track_id": 3172,
                "name": "The Office: An American Workplace (Pilot)"
              }
            ]
          },
          {
            "album_id": 250,
            "title": "The Office, Season 2",
            "tracks": [
              {
                "track_id": 3178,
                "name": "The Dundies"
              }
            ]
          },
          {
            "album_id": 251,
            "title": "The Office, Season 3",
            "tracks": [
              {
                "track_id": 3200,
                "name": "Gay Witch Hunt"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 141,
        "name": "The Police",
        "albums": [
          {
            "album_id": 215,
            "title": "The Police Greatest Hits",
            "tracks": [
              {
                "track_id": 2650,
                "name": "Roxanne"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 200,
        "name": "The Posies",
        "albums": [
          {
            "album_id": 265,
            "title": "Every Kind of Light",
            "tracks": [
              {
                "track_id": 3353,
                "name": "I Guess You're Right"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 174,
        "name": "The Postal Service",
        "albums": []
      },
      {
        "artist_id": 142,
        "name": "The Rolling Stones",
        "albums": [
          {
            "album_id": 216,
            "title": "Hot Rocks, 1964-1971 (Disc 1)",
            "tracks": [
              {
                "track_id": 2664,
                "name": "Time Is On My Side"
              }
            ]
          },
          {
            "album_id": 217,
            "title": "No Security",
            "tracks": [
              {
                "track_id": 2676,
                "name": "Intro"
              }
            ]
          },
          {
            "album_id": 218,
            "title": "Voodoo Lounge",
            "tracks": [
              {
                "track_id": 2690,
                "name": "Love Is Strong"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 143,
        "name": "The Tea Party",
        "albums": [
          {
            "album_id": 219,
            "title": "Tangents",
            "tracks": [
              {
                "track_id": 2705,
                "name": "Walking Wounded"
              }
            ]
          },
          {
            "album_id": 220,
            "title": "Transmission",
            "tracks": [
              {
                "track_id": 2720,
                "name": "Temptation"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 144,
        "name": "The Who",
        "albums": [
          {
            "album_id": 221,
            "title": "My Generation - The Very Best Of The Who",
            "tracks": [
              {
                "track_id": 2731,
                "name": "I Can't Explain"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 145,
        "name": "Tim Maia",
        "albums": [
          {
            "album_id": 222,
            "title": "Serie Sem Limite (Disc 1)",
            "tracks": [
              {
                "track_id": 2751,
                "name": "Primavera"
              }
            ]
          },
          {
            "album_id": 223,
            "title": "Serie Sem Limite (Disc 2)",
            "tracks": [
              {
                "track_id": 2766,
                "name": "O Que Me Importa"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 146,
        "name": "Titãs",
        "albums": [
          {
            "album_id": 224,
            "title": "Acústico",
            "tracks": [
              {
                "track_id": 2781,
                "name": "Comida"
              }
            ]
          },
          {
            "album_id": 225,
            "title": "Volume Dois",
            "tracks": [
              {
                "track_id": 2803,
                "name": "Sonifera Ilha"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 231,
        "name": "Ton Koopman",
        "albums": [
          {
            "album_id": 297,
            "title": "Bach: Toccata & Fugue in D Minor",
            "tracks": [
              {
                "track_id": 3430,
                "name": "Toccata and Fugue in D Minor, BWV 565: I. Toccata"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 70,
        "name": "Toquinho & Vinícius",
        "albums": [
          {
            "album_id": 52,
            "title": "Vinícius De Moraes - Sem Limite",
            "tracks": [
              {
                "track_id": 646,
                "name": "Samba Da Bênção"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 150,
        "name": "U2",
        "albums": [
          {
            "album_id": 232,
            "title": "Achtung Baby",
            "tracks": [
              {
                "track_id": 2926,
                "name": "Zoo Station"
              }
            ]
          },
          {
            "album_id": 233,
            "title": "All That You Can't Leave Behind",
            "tracks": [
              {
                "track_id": 2938,
                "name": "Beautiful Day"
              }
            ]
          },
          {
            "album_id": 234,
            "title": "B-Sides 1980-1990",
            "tracks": [
              {
                "track_id": 2949,
                "name": "The Three Sunrises"
              }
            ]
          },
          {
            "album_id": 235,
            "title": "How To Dismantle An Atomic Bomb",
            "tracks": [
              {
                "track_id": 2964,
                "name": "Vertigo"
              }
            ]
          },
          {
            "album_id": 255,
            "title": "Instant Karma: The Amnesty International Campaign to Save Darfur",
            "tracks": [
              {
                "track_id": 3253,
                "name": "Instant Karma"
              }
            ]
          },
          {
            "album_id": 236,
            "title": "Pop",
            "tracks": [
              {
                "track_id": 2975,
                "name": "Discotheque"
              }
            ]
          },
          {
            "album_id": 237,
            "title": "Rattle And Hum",
            "tracks": [
              {
                "track_id": 2987,
                "name": "Helter Skelter"
              }
            ]
          },
          {
            "album_id": 238,
            "title": "The Best Of 1980-1990",
            "tracks": [
              {
                "track_id": 3004,
                "name": "Pride (In The Name Of Love)"
              }
            ]
          },
          {
            "album_id": 239,
            "title": "War",
            "tracks": [
              {
                "track_id": 3018,
                "name": "Sunday Bloody Sunday"
              }
            ]
          },
          {
            "album_id": 240,
            "title": "Zooropa",
            "tracks": [
              {
                "track_id": 3028,
                "name": "Zooropa"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 151,
        "name": "UB40",
        "albums": [
          {
            "album_id": 241,
            "title": "UB40 The Best Of - Volume Two [UK]",
            "tracks": [
              {
                "track_id": 3038,
                "name": "Breakfast In Bed"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 152,
        "name": "Van Halen",
        "albums": [
          {
            "album_id": 242,
            "title": "Diver Down",
            "tracks": [
              {
                "track_id": 3052,
                "name": "Where Have All The Good Times Gone?"
              }
            ]
          },
          {
            "album_id": 243,
            "title": "The Best Of Van Halen, Vol. I",
            "tracks": [
              {
                "track_id": 3064,
                "name": "Eruption"
              }
            ]
          },
          {
            "album_id": 244,
            "title": "Van Halen",
            "tracks": [
              {
                "track_id": 3081,
                "name": "Runnin' With The Devil"
              }
            ]
          },
          {
            "album_id": 245,
            "title": "Van Halen III",
            "tracks": [
              {
                "track_id": 3092,
                "name": "Neworld"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 21,
        "name": "Various Artists",
        "albums": [
          {
            "album_id": 29,
            "title": "Axé Bahia 2001",
            "tracks": [
              {
                "track_id": 323,
                "name": "Dig-Dig, Lambe-Lambe (Ao Vivo)"
              }
            ]
          },
          {
            "album_id": 32,
            "title": "Carnaval 2001",
            "tracks": [
              {
                "track_id": 360,
                "name": "Vai-Vai 2001"
              }
            ]
          },
          {
            "album_id": 45,
            "title": "Sambas De Enredo 2001",
            "tracks": [
              {
                "track_id": 556,
                "name": "Imperatriz"
              }
            ]
          },
          {
            "album_id": 53,
            "title": "Vozes do MPB",
            "tracks": [
              {
                "track_id": 661,
                "name": "Linha de Passe (João Bosco)"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 153,
        "name": "Velvet Revolver",
        "albums": [
          {
            "album_id": 246,
            "title": "Contraband",
            "tracks": [
              {
                "track_id": 3104,
                "name": "Sucker Train Blues"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 75,
        "name": "Vinicius, Toquinho & Quarteto Em Cy",
        "albums": []
      },
      {
        "artist_id": 72,
        "name": "Vinícius De Moraes",
        "albums": [
          {
            "album_id": 247,
            "title": "Vinicius De Moraes",
            "tracks": [
              {
                "track_id": 3117,
                "name": "Pela Luz Dos Olhos Teus"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 71,
        "name": "Vinícius De Moraes & Baden Powell",
        "albums": []
      },
      {
        "artist_id": 74,
        "name": "Vinícius E Odette Lara",
        "albums": []
      },
      {
        "artist_id": 73,
        "name": "Vinícius E Qurteto Em Cy",
        "albums": []
      },
      {
        "artist_id": 154,
        "name": "Whitesnake",
        "albums": []
      },
      {
        "artist_id": 211,
        "name": "Wilhelm Kempff",
        "albums": [
          {
            "album_id": 277,
            "title": "Bach: Goldberg Variations",
            "tracks": [
              {
                "track_id": 3408,
                "name": "Aria Mit 30 Veränderungen, BWV 988 \"Goldberg Variations\": Aria"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 181,
        "name": "Xis",
        "albums": []
      },
      {
        "artist_id": 255,
        "name": "Yehudi Menuhin",
        "albums": [
          {
            "album_id": 325,
            "title": "Bartok: Violin & Viola Concertos",
            "tracks": [
              {
                "track_id": 3480,
                "name": "Sonata for Solo Violin: IV: Presto"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 212,
        "name": "Yo-Yo Ma",
        "albums": [
          {
            "album_id": 278,
            "title": "Bach: The Cello Suites",
            "tracks": [
              {
                "track_id": 3409,
                "name": "Suite for Solo Cello No. 1 in G Major, BWV 1007: I. Prélude"
              }
            ]
          }
        ]
      },
      {
        "artist_id": 168,
        "name": "Youssou N'Dour",
        "albums": []
      },
      {
        "artist_id": 155,
        "name": "Zeca Pagodinho",
        "albums": [
          {
            "album_id": 248,
            "title": "Ao Vivo [IMPORT]",
            "tracks": [
              {
                "track_id": 3146,
                "name": "Faixa Amarela"
              }
            ]
          }
        ]
      }
    ]
  }
}
```

3. Get all albums for artist id = 5 without specifying a where clause.

This query is required to be executed as Artist (because where clause is now allowed.)

Request Headers: 
content-type: application/json
x-hasura-admin-secret: somesecrectkey
x-hasura-role: artist
x-hasura-artist-id: 5

Query: 
query getAlbums {
  album {
    album_id
    artist_id
    title
  }
}

Response:
{
  "data": {
    "album": [
      {
        "album_id": 7,
        "artist_id": 5,
        "title": "Facelift"
      }
    ]
  }
}
```

**4. Using a GraphQL mutation, add your favorite artist and one of their albums that isn’t in the dataset.**

Request Headers: 

content-type: application/json

x-hasura-admin-secret: somesecrectkey

**Query:**
```
mutation MyMutation($album_id: Int!, $artist_id: Int!, $name: String!, $title: String!) {
  insert_album_one(object: {album_id: $album_id, artist: {data: {artist_id: $artist_id, name: $name}}, title: $title}, on_conflict: {constraint: album_pkey}) {
    album_id
    title
    artist_id
  }
}
```

**Query Variables:**
```
{
  "album_id": 348,
  "artist_id": 276,
  "name": "Daljeet",
  "title": "Ghost"
}
```

**Response:**
```
{
  "data": {
    "insert_album_one": {
      "album_id": 348,
      "title": "Ghost",
      "artist_id": 276
    }
  }
}
```

**5. How did you identify which ID to include in the mutation?**

**Query:**
```
query AlbumCount {
  album_aggregate {
    aggregate {
      count
    }
  }
}
```

**Response:**

```
{
  "data": {
    "album_aggregate": {
      "aggregate": {
        "count": 347
      }
    }
  }
}
```

**Query:**

```
query ArtistCount {
  artist_aggregate {
    aggregate {
      count
    }
  }
}
```

**Response:**

```
{
  "data": {
    "artist_aggregate": {
      "aggregate": {
        "count": 275
      }
    }
  }
}
```

**Added one in the count to find the ID to include in the mutation.** 
