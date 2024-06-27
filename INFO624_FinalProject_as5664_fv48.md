# INFO 624 Final Project Source Code

## 1. Student(s)

+ Allie Schneider, as5664@drexel.edu
+ Francis Villamater, fv48@drexel.edu

## Index

```json
PUT as5664_info624_202202_music
```

## Mapping

```json
PUT as5664_info624_202202_music
{
  "mappings": {
    "properties": {
      "row_identifier": {"type": "integer"},
      "artist_name": {"type": "text", "analyzer": "standard"},
      "track_name": {"type": "text", "analyzer": "standard"},
      "release_date": {"type": "integer"},
      "genre": {"type": "text", "analyzer": "standard"},
      "lyrics" : {"type": "text", "analyzer": "english"},
      "len": {"type": "integer"},
      "dating": {"type": "float"},
      "violence": {"type": "float"},
      "world/life": {"type": "float"},
      "night/time": {"type": "float"},
      "shake the audience": {"type": "float"},
      "family/gospel": {"type": "float"},
      "romantic": {"type": "float"},
      "communication": {"type": "float"},
      "obscene": {"type": "float"},
      "music": {"type": "float"},
      "movement/places": {"type": "float"},
      "light/visual perceptions": {"type": "float"},
      "family/spiritual": {"type": "float"},
      "like/girls": {"type": "float"},
      "sadness": {"type": "float"},
      "feelings": {"type": "float"},
      "danceability": {"type": "float"},
      "loudness": {"type": "float"},
      "acousticness": {"type": "float"},
      "instrumentalness": {"type": "float"},
      "valence": {"type": "float"},
      "energy": {"type": "float"},
      "topic": {"type": "text", "analyzer": "standard"},
      "age": {"type": "integer"}
    }
  }
}
```

## Load Data

Note: Loaded data via Kibana's XLSX Import feature. 


## Use Case 1: Query

Keywords: scent bone heart stick emptiness (on lyrics)
Information Need: to find songs that have the exact lyrics of "scent bone heart stick emptiness", should result in the song titled "Rifle Range" by Blondie released in 1976

Request:
```json
GET as5664_info624_202202_music/_search
{
  "query": {
    "multi_match": {
      "query": "scent bone heart stick emptiness",
      "fields": ["artist_name", "track_name", "genre", "lyrics^3"]
    }
  }
}
```

Response:
```json
{
  "took" : 20,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 8758,
      "relation" : "eq"
    },
    "max_score" : 55.7433,
    "hits" : [
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line2125-xaiaAokVZ6wVhJcr1SsmCS",
        "_score" : 55.7433,
        "_source" : {
          "row_identifier" : "6313",
          "artist_name" : "blondie",
          "track_name" : "rifle range",
          "release_date" : "1976",
          "genre" : "pop",
          "lyrics" : "scent bone heart stick emptiness zone care want hear voice maiden play rifle range lose heart rifle range start rifle range leave rifle range like victim truce string noose crack news prey loose turn stare face wear gallows heart rifle range lose heart rifle range start rifle range hear shoot rifle range lose head certainly dead visions acid wish bleed drummings fear cause get near think devour yeah yeah yeah rifle range lose heart rifle range start rifle range hear shoot rifle range leave rifle range bang bang rifle range bang bang rifle range bang bang",
          "len" : "96",
          "dating" : "0.001119821",
          "violence" : "0.388677945",
          "world/life" : "0.001119821",
          "night/time" : "0.001119821",
          "shake_the_audience" : "0.068233706",
          "family/gospel" : "0.001119821",
          "romantic" : "0.001119821",
          "communication" : "0.001119821",
          "obscene" : "0.001119821",
          "music" : "0.08115995",
          "movement/places" : "0.001119821",
          "light/visual_perceptions" : "0.001119821",
          "family/spiritual" : "0.001119821",
          "like/girls" : "0.001119821",
          "sadness" : "0.421927245",
          "feelings" : "0.001119821",
          "danceability" : "0.310083397",
          "loudness" : "0.66035946",
          "acousticness" : "0.019276124",
          "instrumentalness" : "0.004726721",
          "valence" : "0.640354493",
          "energy" : "0.670660385",
          "topic" : "sadness",
          "age" : "0.628571429"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line27362-bMEsbfaVmJEMPetDXxz2dK",
        "_score" : 39.698986,
        "_source" : {
          "row_identifier" : "80676",
          "artist_name" : "grandson",
          "track_name" : "stick up",
          "release_date" : "2018",
          "genre" : "rock",
          "lyrics" : "good father sons daughter wake ask bother fee family wage pay insanity deal calamity lose occupation wasn immigration machine automation replace politicians leave corruption recession grab wesson say teach lesson like grind stick sound hiccup empty round play game go flame rain stick sound hiccup empty round play game lyric commercial",
          "len" : "51",
          "dating" : "0.001644737",
          "violence" : "0.001644737",
          "world/life" : "0.001644737",
          "night/time" : "0.001644737",
          "shake_the_audience" : "0.001644737",
          "family/gospel" : "0.001644737",
          "romantic" : "0.001644737",
          "communication" : "0.001644737",
          "obscene" : "0.386544277",
          "music" : "0.001644737",
          "movement/places" : "0.302679222",
          "light/visual_perceptions" : "0.042318789",
          "family/spiritual" : "0.054057154",
          "like/girls" : "0.001644737",
          "sadness" : "0.001644737",
          "feelings" : "0.048002523",
          "danceability" : "0.268926676",
          "loudness" : "0.792067277",
          "acousticness" : "0.000261044",
          "instrumentalness" : "3.76E-06",
          "valence" : "0.288953009",
          "energy" : "0.932930838",
          "topic" : "obscene",
          "age" : "0.028571429"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line937-afmpchv54uazUPLgkgYRBS",
        "_score" : 38.472557,
        "_source" : {
          "row_identifier" : "2490",
          "artist_name" : "the zombies",
          "track_name" : "sticks and stones",
          "release_date" : "1965",
          "genre" : "pop",
          "lyrics" : "people talk break stick stone break bone talk bother people talk break scandalize stick stone break bone abuse home abuse abuse right start people talk break stick stone break bone talk bother abuse home abuse abuse right start people talk break stick stone break bone talk bother abuse home abuse abuse right start people talk break stick stone break bone talk bother",
          "len" : "62",
          "dating" : "0.001074114",
          "violence" : "0.347037204",
          "world/life" : "0.001074114",
          "night/time" : "0.001074114",
          "shake_the_audience" : "0.001074114",
          "family/gospel" : "0.001074114",
          "romantic" : "0.001074114",
          "communication" : "0.263631886",
          "obscene" : "0.001074114",
          "music" : "0.065482838",
          "movement/places" : "0.001074114",
          "light/visual_perceptions" : "0.001074114",
          "family/spiritual" : "0.102395565",
          "like/girls" : "0.001074114",
          "sadness" : "0.206414914",
          "feelings" : "0.001074114",
          "danceability" : "0.446550417",
          "loudness" : "0.788375253",
          "acousticness" : "0.259035401",
          "instrumentalness" : "0.000124494",
          "valence" : "0.857790602",
          "energy" : "0.786780128",
          "topic" : "violence",
          "age" : "0.785714286"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line16834-5Dca6jqMUH6Nu8r7ujxANp",
        "_score" : 36.030186,
        "_source" : {
          "row_identifier" : "53644",
          "artist_name" : "alice cooper",
          "track_name" : "paranormal",
          "release_date" : "2017",
          "genre" : "blues",
          "lyrics" : "condemn long endless night live absense light life watch sleep night cool skin bone wrap sheet ring dead telephone scar home like spider kiss face familiar smell scent leave lace condemn long endless night live absense light",
          "len" : "37",
          "dating" : "0.001949318",
          "violence" : "0.314578873",
          "world/life" : "0.100013861",
          "night/time" : "0.219131425",
          "shake_the_audience" : "0.001949318",
          "family/gospel" : "0.001949318",
          "romantic" : "0.051389713",
          "communication" : "0.001949318",
          "obscene" : "0.001949318",
          "music" : "0.127533049",
          "movement/places" : "0.001949318",
          "light/visual_perceptions" : "0.12323254",
          "family/spiritual" : "0.001949318",
          "like/girls" : "0.001949318",
          "sadness" : "0.001949318",
          "feelings" : "0.001949318",
          "danceability" : "0.317664898",
          "loudness" : "0.704740661",
          "acousticness" : "0.03965767",
          "instrumentalness" : "0.181174089",
          "valence" : "0.152926628",
          "energy" : "0.662652127",
          "topic" : "violence",
          "age" : "0.042857143"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line25719-irdoWaJEboYbuZdbKS8Z7N",
        "_score" : 34.569954,
        "_source" : {
          "row_identifier" : "76622",
          "artist_name" : "metallica",
          "track_name" : "mama said",
          "release_date" : "1996",
          "genre" : "rock",
          "lyrics" : "mama teach tell young life open book close fore brightest flame burn quickest hear heart own mother heart grow mama heart heart rebel wild blood vein apron string neck remain leave home early hear wrong ask forgiveness say heart grow mama heart heart give give emptiness grave give give emptiness grave heart mama come home wish mother unspoken help take grant things say yeahyeah need arm welcome cold stone heart grow mama heart heart heart mama heart heart heart give give emptiness grave give give emptiness grave heart",
          "len" : "88",
          "dating" : "0.000720981",
          "violence" : "0.170471752",
          "world/life" : "0.134743044",
          "night/time" : "0.000720981",
          "shake_the_audience" : "0.000720981",
          "family/gospel" : "0.170367886",
          "romantic" : "0.000720981",
          "communication" : "0.000720981",
          "obscene" : "0.000720981",
          "music" : "0.0470167",
          "movement/places" : "0.000720981",
          "light/visual_perceptions" : "0.000720981",
          "family/spiritual" : "0.062246758",
          "like/girls" : "0.000720981",
          "sadness" : "0.405781113",
          "feelings" : "0.000720981",
          "danceability" : "0.42163977",
          "loudness" : "0.71694485",
          "acousticness" : "0.018673714",
          "instrumentalness" : "0.000511134",
          "valence" : "0.384789777",
          "energy" : "0.497481803",
          "topic" : "sadness",
          "age" : "0.342857143"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line26505-6PDiFA1anbCfGWctezbqxf",
        "_score" : 32.09764,
        "_source" : {
          "row_identifier" : "78381",
          "artist_name" : "mudvayne",
          "track_name" : "do what you do",
          "release_date" : "2008",
          "genre" : "rock",
          "lyrics" : "lips bleed ring little bruise little things provoke segregation lead separation cage clip wing little noise little scream stop operation conscious amputation stick draw chalk line scene break heart lose beat little softly weep overwhelm emotion view burn explosion lose tree little whisper little dream spark recollection constant suffocation stick draw chalk line scene feel life change change feel heart jade jade leave stick leave stone word hurt mend bone feel life change solo stick draw chalk line scene erase past leave pain cleanse wound forget lose away spread grave lose tongue away",
          "len" : "93",
          "dating" : "0.000809717",
          "violence" : "0.385206563",
          "world/life" : "0.131053727",
          "night/time" : "0.000809717",
          "shake_the_audience" : "0.000809717",
          "family/gospel" : "0.110720242",
          "romantic" : "0.024049414",
          "communication" : "0.000809717",
          "obscene" : "0.000809717",
          "music" : "0.01944749",
          "movement/places" : "0.000809717",
          "light/visual_perceptions" : "0.059485617",
          "family/spiritual" : "0.000809717",
          "like/girls" : "0.000809717",
          "sadness" : "0.172469302",
          "feelings" : "0.029074592",
          "danceability" : "0.472544135",
          "loudness" : "0.846293875",
          "acousticness" : "0.002037151",
          "instrumentalness" : "0",
          "valence" : "0.641384996",
          "energy" : "0.974974193",
          "topic" : "violence",
          "age" : "0.171428571"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line8322-xm1FeTHBR2cug929yH2HKW",
        "_score" : 31.815243,
        "_source" : {
          "row_identifier" : "23635",
          "artist_name" : "derek & the dominos",
          "track_name" : "i am yours",
          "release_date" : "1970",
          "genre" : "country",
          "lyrics" : "distant blow wind waft scent sing call memory leave linger forever distant blow wind waft scent sing call memory leave linger forever distant blow wind waft scent sing call memory leave linger forever",
          "len" : "33",
          "dating" : "0.002392345",
          "violence" : "0.002392345",
          "world/life" : "0.002392345",
          "night/time" : "0.002392345",
          "shake_the_audience" : "0.002392344",
          "family/gospel" : "0.002392344",
          "romantic" : "0.002392345",
          "communication" : "0.002392345",
          "obscene" : "0.002392345",
          "music" : "0.609112968",
          "movement/places" : "0.002392345",
          "light/visual_perceptions" : "0.002392345",
          "family/spiritual" : "0.002392345",
          "like/girls" : "0.002392344",
          "sadness" : "0.213853539",
          "feelings" : "0.002392344",
          "danceability" : "0.664247807",
          "loudness" : "0.508576263",
          "acousticness" : "0.405621893",
          "instrumentalness" : "0.259109312",
          "valence" : "0.602225886",
          "energy" : "0.313291867",
          "topic" : "music",
          "age" : "0.714285714"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line14012-nwEgSc7dkynj5tRVwwiGAr",
        "_score" : 31.779816,
        "_source" : {
          "row_identifier" : "44867",
          "artist_name" : "the fall",
          "track_name" : "dice man",
          "release_date" : "1979",
          "genre" : "blues",
          "lyrics" : "dice go go branch tree showbusiness musicians social conscience room dice stay mass chance empty ashtrays push push push push throw bone poison dice time small moralists dice music like read story wanna read horror story people go people go branch tree showbusiness dice ballsontheline baby",
          "len" : "46",
          "dating" : "0.039585443",
          "violence" : "0.388332497",
          "world/life" : "0.001949318",
          "night/time" : "0.079633977",
          "shake_the_audience" : "0.001949318",
          "family/gospel" : "0.001949318",
          "romantic" : "0.001949318",
          "communication" : "0.001949318",
          "obscene" : "0.001949318",
          "music" : "0.061000489",
          "movement/places" : "0.001949318",
          "light/visual_perceptions" : "0.001949318",
          "family/spiritual" : "0.15431803",
          "like/girls" : "0.001949318",
          "sadness" : "0.001949318",
          "feelings" : "0.150358383",
          "danceability" : "0.594931225",
          "loudness" : "0.754813732",
          "acousticness" : "0.796184534",
          "instrumentalness" : "0.009271255",
          "valence" : "0.689818631",
          "energy" : "0.836831741",
          "topic" : "violence",
          "age" : "0.585714286"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line290-e47L6BRuCr4csJhRBPiY1H",
        "_score" : 31.137354,
        "_source" : {
          "row_identifier" : "746",
          "artist_name" : "ritchie valens",
          "track_name" : "paddiwack song",
          "release_date" : "1959",
          "genre" : "pop",
          "lyrics" : "play play knickknack thumb knick knack paddiwack bone come home play play knickknack shoe knick knack paddiwack bone come home play play knickknack door knick knack paddiwack bone come home instrumental play play knickknack jive knick knack paddiwack bone come home play play knickknack stick knick knack paddiwack bone come home play play knickknack heaven knick knack paddiwack bone come home play play knickknack gate knick knack paddiwack bone come home",
          "len" : "71",
          "dating" : "0.105038687",
          "violence" : "0.262785878",
          "world/life" : "0.001315789",
          "night/time" : "0.001315789",
          "shake_the_audience" : "0.001315789",
          "family/gospel" : "0.001315789",
          "romantic" : "0.001315789",
          "communication" : "0.001315789",
          "obscene" : "0.00131579",
          "music" : "0.611122803",
          "movement/places" : "0.00131579",
          "light/visual_perceptions" : "0.00131579",
          "family/spiritual" : "0.00131579",
          "like/girls" : "0.001315789",
          "sadness" : "0.001315789",
          "feelings" : "0.001315789",
          "danceability" : "0.518033142",
          "loudness" : "0.718611389",
          "acousticness" : "0.841365303",
          "instrumentalness" : "1.66E-06",
          "valence" : "0.881492168",
          "energy" : "0.914912258",
          "topic" : "music",
          "age" : "0.871428571"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line13437-dUCKnSp3UNG2tVgR1uGS2L",
        "_score" : 30.801258,
        "_source" : {
          "row_identifier" : "42855",
          "artist_name" : "joe cocker",
          "track_name" : "sticks and stones",
          "release_date" : "1970",
          "genre" : "blues",
          "lyrics" : "people talkin tryin break stick stone break bone talk bother people talkin tryin break know care people gonna abuse abuse heart accuse accuse accuse rebuke stomp people talkin tryin break scandalize feel sham abuse abuse heart accuse accuse accuse rebuke stomp people talkin tryin break scandalize feel sham",
          "len" : "48",
          "dating" : "0.001754386",
          "violence" : "0.066436534",
          "world/life" : "0.001754386",
          "night/time" : "0.001754386",
          "shake_the_audience" : "0.001754386",
          "family/gospel" : "0.001754386",
          "romantic" : "0.001754386",
          "communication" : "0.001754386",
          "obscene" : "0.430201349",
          "music" : "0.001754386",
          "movement/places" : "0.001754386",
          "light/visual_perceptions" : "0.001754386",
          "family/spiritual" : "0.16206378",
          "like/girls" : "0.001754386",
          "sadness" : "0.237434627",
          "feelings" : "0.044397604",
          "danceability" : "0.430304343",
          "loudness" : "0.773402046",
          "acousticness" : "0.295180015",
          "instrumentalness" : "0",
          "valence" : "0.814509481",
          "energy" : "0.973973161",
          "topic" : "obscene",
          "age" : "0.714285714"
        }
      }
    ]
  }
}
```

## Use Case 2: Query

Keywords: 0.97 (on danceability)
Information Need: to find multiple songs with a high danceability score

Request:
```json
GET as5664_info624_202202_music/_search
{
  "query": {
    "range": {
      "danceability": {
        "gt": 0.97
      }
    }
  },
  "sort": [
    {"danceability": {"order": "desc"}}
    ]
}
```

Response:
```json
{
  "took" : 10,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 11,
      "relation" : "eq"
    },
    "max_score" : null,
    "hits" : [
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line27614-f14pmqCLzU2ceJBr4H5tmj",
        "_score" : null,
        "_source" : {
          "row_identifier" : "81243",
          "artist_name" : "vanilla ice",
          "track_name" : "ice ice baby (re-recorded version)",
          "release_date" : "2008",
          "genre" : "hip hop",
          "lyrics" : "kick baby baby right stop collaborate listen brand invention grab hold tightly flow like harpoon daily nightly stop know turn light glow extreme like vandal light stage chump like candle dance rush speaker boom kill brain like poisonous mushroom deadly play dope best felony leave better gain better bull play problem solve check revolve baby vanilla baby vanilla baby vanilla baby vanilla party jump bass kick vegas pumpin quick point point fake lyric commercial",
          "len" : "74",
          "dating" : "0.158433757",
          "violence" : "0.001169591",
          "world/life" : "0.001169591",
          "night/time" : "0.001169591",
          "shake_the_audience" : "0.001169591",
          "family/gospel" : "0.001169591",
          "romantic" : "0.001169591",
          "communication" : "0.001169591",
          "obscene" : "0.636479056",
          "music" : "0.001169591",
          "movement/places" : "0.001169591",
          "light/visual_perceptions" : "0.104296178",
          "family/spiritual" : "0.001169591",
          "like/girls" : "0.001169591",
          "sadness" : "0.001169591",
          "feelings" : "0.001169591",
          "danceability" : "0.99350157",
          "loudness" : "0.842832603",
          "acousticness" : "0.002509039",
          "instrumentalness" : "7.80E-06",
          "valence" : "0.576463314",
          "energy" : "0.792786321",
          "topic" : "obscene",
          "age" : "0.171428571"
        },
        "sort" : [
          0.99350154
        ]
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line18885-6QZXNQ2MndhfVGCwfwuX7H",
        "_score" : null,
        "_source" : {
          "row_identifier" : "58609",
          "artist_name" : "jungle brothers",
          "track_name" : "black is black",
          "release_date" : "1988",
          "genre" : "jazz",
          "lyrics" : "tribe call quest tonight jungle brothers thing call black black black black black black black black america today regret somethin somethin right deal black white tell society fill propaganda meander zone hate peace cease black mighty white hand brother brother sister sister miss mister listen fact black black black black think crime black black black black think crime black black black black brothers great fight civil right scar soul take sight common plainly streets segregation vietnam swing shout situation sort change make matter strange disguise know fate lie lack fact black black black think crime black black black black think crime black black black black judge race color know need need need soon light complexion mean think dream time break black black blue purple black like circle round round know listen fantasy kill reality real reality black black tell people create equal master plan hard understand today change things better tomorrow drown pool sorrow daylight shin fight unity picture fix black white fight uplift race uplift race soul face black black right think crime think crime black black black black black black black black",
          "len" : "184",
          "dating" : "0.000362976",
          "violence" : "0.576316597",
          "world/life" : "0.064286916",
          "night/time" : "0.022137981",
          "shake_the_audience" : "0.000362976",
          "family/gospel" : "0.025335734",
          "romantic" : "0.000362976",
          "communication" : "0.165767618",
          "obscene" : "0.058584077",
          "music" : "0.01237928",
          "movement/places" : "0.000362976",
          "light/visual_perceptions" : "0.023595764",
          "family/spiritual" : "0.04796627",
          "like/girls" : "0.000362976",
          "sadness" : "0.000362976",
          "feelings" : "0.000362976",
          "danceability" : "0.991335427",
          "loudness" : "0.666179525",
          "acousticness" : "0.063352473",
          "instrumentalness" : "0",
          "valence" : "0.805234955",
          "energy" : "0.502486965",
          "topic" : "violence",
          "age" : "0.457142857"
        },
        "sort" : [
          0.99133545
        ]
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line5621-jzfEBwvPuJy3QQuWJWnoz1",
        "_score" : null,
        "_source" : {
          "row_identifier" : "16170",
          "artist_name" : "timbaland",
          "track_name" : "give it to me",
          "release_date" : "2007",
          "genre" : "pop",
          "lyrics" : "go go go go know lookin yeah come type girl look dead real come know flyyyyy see try switch girl dope wonder woman rope supermodel mami mami amnesty international bangkok montauk lock video promiscuous style ulous ulous club actin real nice floor watchin night hurt wanna work body timbo party everybody hand half beat couple graaand upper hand respect california japan real producer piano songs chart hear faaan niggas talkin greasy give somebody need tell like club actin real nice floor watchin night hurt wanna work body speak stop mumumbling think come clear sittin hard hear tryin cute clear miss chart week damn right wasn sesexy leave everybody shiiit hate come club walk cause club actin real nice floor watchin night hurt wanna work body club actin real nice floor watchin night hurt wanna work body club actin real nice floor watchin night hurt wanna work body",
          "len" : "147",
          "dating" : "0.000496524",
          "violence" : "0.048473039",
          "world/life" : "0.000496524",
          "night/time" : "0.05982548",
          "shake_the_audience" : "0.022204015",
          "family/gospel" : "0.041933808",
          "romantic" : "0.000496524",
          "communication" : "0.072739474",
          "obscene" : "0.448468081",
          "music" : "0.022049429",
          "movement/places" : "0.000496524",
          "light/visual_perceptions" : "0.000496524",
          "family/spiritual" : "0.000496524",
          "like/girls" : "0.085239557",
          "sadness" : "0.052752909",
          "feelings" : "0.087265461",
          "danceability" : "0.987003141",
          "loudness" : "0.81121965",
          "acousticness" : "0.170681898",
          "instrumentalness" : "0.000285425",
          "valence" : "0.749587799",
          "energy" : "0.723715095",
          "topic" : "obscene",
          "age" : "0.185714286"
        },
        "sort" : [
          0.98700315
        ]
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line5479-orEGsG8nAvEdgzLGWTjskS",
        "_score" : null,
        "_source" : {
          "row_identifier" : "15749",
          "artist_name" : "justin timberlake",
          "track_name" : "sexyback (feat. timbaland)",
          "release_date" : "2006",
          "genre" : "pop",
          "lyrics" : "kiyoko need feat kehlani kiyoko hnly cabello love control demi lovato heart attack puth feat kehlani lipa kiss glynne hold hand clean bandit feat glynne lorde team lady gaga paparazzi timberlake sexyback feat timbaland minogue head spear slave firework beyoncé crazy feat jayz rihanna stop music shania twain feel like woman panic disco amen saturday night petras want disclosure latch feat kiyoko curious remix swift delicate kehlani",
          "len" : "67",
          "dating" : "0.108263709",
          "violence" : "0.117465031",
          "world/life" : "0.002770083",
          "night/time" : "0.002770083",
          "shake_the_audience" : "0.002770084",
          "family/gospel" : "0.002770083",
          "romantic" : "0.406676284",
          "communication" : "0.002770083",
          "obscene" : "0.002770083",
          "music" : "0.056678782",
          "movement/places" : "0.002770083",
          "light/visual_perceptions" : "0.002770083",
          "family/spiritual" : "0.002770083",
          "like/girls" : "0.069568049",
          "sadness" : "0.002770083",
          "feelings" : "0.043493223",
          "danceability" : "0.980504711",
          "loudness" : "0.769120324",
          "acousticness" : "0.068171755",
          "instrumentalness" : "0",
          "valence" : "0.969084913",
          "energy" : "0.599587094",
          "topic" : "romantic",
          "age" : "0.2"
        },
        "sort" : [
          0.9805047
        ]
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line19665-3f8z4V1HFiSwgcsSJr6XCt",
        "_score" : null,
        "_source" : {
          "row_identifier" : "60325",
          "artist_name" : "georg levin",
          "track_name" : "(i got) somebody new",
          "release_date" : "2002",
          "genre" : "jazz",
          "lyrics" : "somebody different view somebody different view reminisce think thing miss reminisce turn like right outside door right outside door somebody different view somebody different view reminisce think thing miss reminisce turn like right outside door right outside door right outside door right outside door oooh somebody somebody somebody somebody somebody forever somebody forever somebody forever somebody forever somebody forever somebody forever somebody forever",
          "len" : "63",
          "dating" : "0.000892061",
          "violence" : "0.000892061",
          "world/life" : "0.000892061",
          "night/time" : "0.087348836",
          "shake_the_audience" : "0.000892061",
          "family/gospel" : "0.000892061",
          "romantic" : "0.000892061",
          "communication" : "0.165704434",
          "obscene" : "0.000892061",
          "music" : "0.000892061",
          "movement/places" : "0.255239618",
          "light/visual_perceptions" : "0.000892061",
          "family/spiritual" : "0.000892061",
          "like/girls" : "0.000892061",
          "sadness" : "0.000892061",
          "feelings" : "0.311055101",
          "danceability" : "0.97942164",
          "loudness" : "0.643591519",
          "acousticness" : "0.021183756",
          "instrumentalness" : "0.054453441",
          "valence" : "0.891797197",
          "energy" : "0.398379609",
          "topic" : "feelings",
          "age" : "0.257142857"
        },
        "sort" : [
          0.9794216
        ]
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line6847-5g8E7uniTJPvXJzCrHeEY4",
        "_score" : null,
        "_source" : {
          "row_identifier" : "19688",
          "artist_name" : "selena gomez",
          "track_name" : "bad liar",
          "release_date" : "2017",
          "genre" : "pop",
          "lyrics" : "walk street tryna distract face tryna play tryna disappear like battle subtle room size space bigger want rent place amenity dream take fraction mind ooooh time watch serpentine tryin tryin tryin tryin tryin tryin tryin tryin tryin tryin think think tryin tryin tryin tryin tryin tryin tryin tryin tryin tryin feel guess liar attention build like look mirror touch like pill fear possibly happen focus paint kiss chest brush take fraction mind ooooh time watch serpentine tryin tryin tryin tryin tryin tryin tryin tryin tryin tryin think think tryin tryin tryin tryin tryin tryin tryin tryin tryin tryin feel guess liar baby reality actuality reality baby reality actuality reality tryin tryin tryin tryin tryin tryin tryin tryin tryin tryin think think tryin tryin tryin tryin tryin tryin tryin tryin tryin tryin feel guess liar",
          "len" : "134",
          "dating" : "0.020314698",
          "violence" : "0.000491884",
          "world/life" : "0.000491884",
          "night/time" : "0.000491884",
          "shake_the_audience" : "0.000491884",
          "family/gospel" : "0.000491884",
          "romantic" : "0.014543037",
          "communication" : "0.000491884",
          "obscene" : "0.866942843",
          "music" : "0.000491884",
          "movement/places" : "0.000491884",
          "light/visual_perceptions" : "0.000491884",
          "family/spiritual" : "0.000491884",
          "like/girls" : "0.000491884",
          "sadness" : "0.077598505",
          "feelings" : "0.013714541",
          "danceability" : "0.978338568",
          "loudness" : "0.749916673",
          "acousticness" : "0.189758223",
          "instrumentalness" : "0",
          "valence" : "0.725886232",
          "energy" : "0.414396125",
          "topic" : "obscene",
          "age" : "0.042857143"
        },
        "sort" : [
          0.97833854
        ]
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line21068-beACfceNoj2bm74wHneNTo",
        "_score" : null,
        "_source" : {
          "row_identifier" : "63570",
          "artist_name" : "jimmy cliff",
          "track_name" : "struggling man",
          "release_date" : "1973",
          "genre" : "reggae",
          "lyrics" : "right live struggle survive fight stay alive struggle struggle time lose struggle light moon light night struggle keep reach higher heights plan tomorrow live today like bloom later fade away struggle struggle time lose struggle struggle struggle time lose struggle struggle struggle struggle struggle struggle struggle",
          "len" : "46",
          "dating" : "0.001879699",
          "violence" : "0.001879699",
          "world/life" : "0.359248819",
          "night/time" : "0.296144231",
          "shake_the_audience" : "0.001879699",
          "family/gospel" : "0.001879699",
          "romantic" : "0.001879699",
          "communication" : "0.001879699",
          "obscene" : "0.001879699",
          "music" : "0.001879699",
          "movement/places" : "0.001879699",
          "light/visual_perceptions" : "0.249682178",
          "family/spiritual" : "0.001879699",
          "like/girls" : "0.001879699",
          "sadness" : "0.001879699",
          "feelings" : "0.001879699",
          "danceability" : "0.976172425",
          "loudness" : "0.631848832",
          "acousticness" : "0.496987447",
          "instrumentalness" : "0.000327935",
          "valence" : "0.90004122",
          "energy" : "0.577564384",
          "topic" : "world/life",
          "age" : "0.671428571"
        },
        "sort" : [
          0.97617245
        ]
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line22968-wMAgBETuzAJfD8kJ3rVhF4",
        "_score" : null,
        "_source" : {
          "row_identifier" : "68926",
          "artist_name" : "fortunate youth",
          "track_name" : "melody",
          "release_date" : "2013",
          "genre" : "reggae",
          "lyrics" : "wake morning sing stick head leave grab word inspiration flow righteously respect oooo live true world madness end pressure society thier view theyre bend world fear value protection higher power guide darkest hour life ignore sparingly word live life righteously",
          "len" : "40",
          "dating" : "0.002105263",
          "violence" : "0.320455547",
          "world/life" : "0.41614475",
          "night/time" : "0.002105263",
          "shake_the_audience" : "0.002105263",
          "family/gospel" : "0.002105263",
          "romantic" : "0.002105263",
          "communication" : "0.002105263",
          "obscene" : "0.002105263",
          "music" : "0.069906157",
          "movement/places" : "0.002105263",
          "light/visual_perceptions" : "0.161914597",
          "family/spiritual" : "0.002105263",
          "like/girls" : "0.002105263",
          "sadness" : "0.002105263",
          "feelings" : "0.002105263",
          "danceability" : "0.976172425",
          "loudness" : "0.683870472",
          "acousticness" : "0.541164198",
          "instrumentalness" : "0.000760121",
          "valence" : "0.952596867",
          "energy" : "0.453436384",
          "topic" : "world/life",
          "age" : "0.1"
        },
        "sort" : [
          0.97617245
        ]
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line28101-nj7zKgdcqETaNrPiRKrUtn",
        "_score" : null,
        "_source" : {
          "row_identifier" : "82048",
          "artist_name" : "machine gun kelly",
          "track_name" : "trap paris",
          "release_date" : "2017",
          "genre" : "hip hop",
          "lyrics" : "wake wake soundin real godly quavo city rollie go flash wake paris break mirror lean watch night turnt catch fuck camera embarrass pull home flag tat fuck bout homebred hometown world miyagi sake run streets city like champ champ fangs like vamp package stamp bust open roll till cramp ring hand smoke ring grams lady tramp bitch trap lyric commercial",
          "len" : "60",
          "dating" : "0.001422475",
          "violence" : "0.001422475",
          "world/life" : "0.001422475",
          "night/time" : "0.001422475",
          "shake_the_audience" : "0.001422475",
          "family/gospel" : "0.001422475",
          "romantic" : "0.001422475",
          "communication" : "0.001422475",
          "obscene" : "0.311110171",
          "music" : "0.001422475",
          "movement/places" : "0.47889837",
          "light/visual_perceptions" : "0.081874817",
          "family/spiritual" : "0.001422475",
          "like/girls" : "0.001422475",
          "sadness" : "0.001422475",
          "feelings" : "0.001422475",
          "danceability" : "0.976172425",
          "loudness" : "0.792631336",
          "acousticness" : "0.022890585",
          "instrumentalness" : "2.83E-06",
          "valence" : "0.160140148",
          "energy" : "0.647636643",
          "topic" : "obscene",
          "age" : "0.042857143"
        },
        "sort" : [
          0.97617245
        ]
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line27471-oH5R4n5yePph9Bet1crSD3",
        "_score" : null,
        "_source" : {
          "row_identifier" : "80964",
          "artist_name" : "boogie down productions",
          "track_name" : "jack of spades",
          "release_date" : "1989",
          "genre" : "hip hop",
          "lyrics" : "start heart take time heart come everybody fear crashin door whore bringin gold chain krsone see human make excuse losers chainsnatchers pimp drug abusers like gotta pushin somebody start mushin suckers claimin rule environment buyin think everybody teach buy take short cause hasn pay spade dnice scratch calm kind courageous loyal temper boil cause like whistle blow right go crime commit right tail bail thinkin bout jail end justify mean scene track movement lose cause come attack crack cocaine cop fiends heat gold chain game destroy stereotype hype crack pip like criminals crime mind come kungfu hammer slammer renegade teacher scholar gotta fall line hear rhyme cause time theme song call spade dnice scratch know spade posse wanna watch throw hand scream yeah yeahhh time yeahhh flash rhyme cool loud quiet head cause spade riot cleanin community debris crime road long scary average couldn average take piece brother gotta admit martyr soldier hero start zero battle clearly understand power payin people hour sell stand gettin everybody high high cable cash table currency able cop prop pay come spade dnice scratch break dnice scratch fresh spade suckers",
          "len" : "186",
          "dating" : "0.000526316",
          "violence" : "0.140418711",
          "world/life" : "0.000526316",
          "night/time" : "0.061762813",
          "shake_the_audience" : "0.023666499",
          "family/gospel" : "0.000526316",
          "romantic" : "0.000526316",
          "communication" : "0.000526316",
          "obscene" : "0.531389894",
          "music" : "0.024000688",
          "movement/places" : "0.113269963",
          "light/visual_perceptions" : "0.000526316",
          "family/spiritual" : "0.000526316",
          "like/girls" : "0.000526316",
          "sadness" : "0.069033773",
          "feelings" : "0.015027618",
          "danceability" : "0.971840139",
          "loudness" : "0.582929518",
          "acousticness" : "0.010340372",
          "instrumentalness" : "2.04E-06",
          "valence" : "0.444558945",
          "energy" : "0.5004849",
          "topic" : "obscene",
          "age" : "0.442857143"
        },
        "sort" : [
          0.97184014
        ]
      }
    ]
  }
}

```


## Use Case 3: Query

Keywords: blues (on genre)
Information Need: find a range of songs in the genre of blues

Request:
```json
GET as5664_info624_202202_music/_search
{
  "query": {
    "multi_match": {
      "query": "blues",
      "fields": ["artist_name", "track_name", "genre^3", "lyrics"]
    }
  }
}
```

Response:
```json
{
  "took" : 11,
  "timed_out" : false,
  "_shards" : {
    "total" : 1,
    "successful" : 1,
    "skipped" : 0,
    "failed" : 0
  },
  "hits" : {
    "total" : {
      "value" : 6380,
      "relation" : "eq"
    },
    "max_score" : 6.63513,
    "hits" : [
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line18731-kUEMW5Z5phGENC4Xkbo7ii",
        "_score" : 6.63513,
        "_source" : {
          "row_identifier" : "58278",
          "artist_name" : "wynton marsalis",
          "track_name" : "blues",
          "release_date" : "1985",
          "genre" : "jazz",
          "lyrics" : "tell go tell go tell go tell go tell go tell go tell go tell go tell go tell go tell go tell go",
          "len" : "24",
          "dating" : "0.002105263",
          "violence" : "0.002105263",
          "world/life" : "0.002105263",
          "night/time" : "0.002105263",
          "shake_the_audience" : "0.002105263",
          "family/gospel" : "0.002105263",
          "romantic" : "0.002105263",
          "communication" : "0.492894856",
          "obscene" : "0.002105263",
          "music" : "0.002105263",
          "movement/places" : "0.002105263",
          "light/visual_perceptions" : "0.002105263",
          "family/spiritual" : "0.002105263",
          "like/girls" : "0.002105263",
          "sadness" : "0.002105263",
          "feelings" : "0.47131567",
          "danceability" : "0.503953211",
          "loudness" : "0.342486475",
          "acousticness" : "0.955823249",
          "instrumentalness" : "0.909919028",
          "valence" : "0.368301731",
          "energy" : "0.008437501",
          "topic" : "feelings",
          "age" : "0.5"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line3802-eh4fZpypQkWxgk8nbfTeLa",
        "_score" : 5.8244166,
        "_source" : {
          "row_identifier" : "11139",
          "artist_name" : "blues traveler",
          "track_name" : "all in the groove",
          "release_date" : "1991",
          "genre" : "pop",
          "lyrics" : "worry tendency hurry vision blurry blind shake stammer dance like hammer pomp glamour remind go mind blow need tow calmly prove things groove groove groove groove groove destiny fight state unite difficult worthwhile babel card table swear able mile ramble ignore money know pearl cast wish picture hang louvre like say groove groove groove groove groove instance swing sway groove funkily play crime pay crime life blood flow water daughter send away order celebration time till feel like begin improve mind rhythm groove groove groove groove groove groove groove",
          "len" : "89",
          "dating" : "0.001283697",
          "violence" : "0.188705963",
          "world/life" : "0.001283697",
          "night/time" : "0.001283697",
          "shake_the_audience" : "0.001283697",
          "family/gospel" : "0.001283697",
          "romantic" : "0.001283697",
          "communication" : "0.213028639",
          "obscene" : "0.337287045",
          "music" : "0.001283697",
          "movement/places" : "0.001283697",
          "light/visual_perceptions" : "0.001283697",
          "family/spiritual" : "0.040619109",
          "like/girls" : "0.001283697",
          "sadness" : "0.092872582",
          "feelings" : "0.038319562",
          "danceability" : "0.663164735",
          "loudness" : "0.694177371",
          "acousticness" : "0.059738012",
          "instrumentalness" : "6.44E-06",
          "valence" : "0.888705688",
          "energy" : "0.832827612",
          "topic" : "obscene",
          "age" : "0.414285714"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line4216-FzyMtf7gBrBwk95EZaTfp",
        "_score" : 5.8244166,
        "_source" : {
          "row_identifier" : "12226",
          "artist_name" : "blues traveler",
          "track_name" : "hook",
          "release_date" : "1994",
          "genre" : "pop",
          "lyrics" : "matter long sing inflection make feel convey inner truth vast reflection say long take matter resolve break hook bring tellin hook bring rely amiss insincere fact mean confession draw near confuse issue refer familiar heroes long matter love refuse grow hook bring tell hook bring rely suck suck suck boleyn desperate begin free kill desperately sing thee sure rage hate pain fear self feel shelf try fact lie financial suicide pride inside hide slide decide ride die shall abide tide catchy little tune minute ditties wanna bust balloon wanna burn cities grind mess play hear prayer pray feel stick need rely luck hook bring tell hook rely",
          "len" : "107",
          "dating" : "0.000848896",
          "violence" : "0.3392241",
          "world/life" : "0.000848896",
          "night/time" : "0.037684882",
          "shake_the_audience" : "0.000848896",
          "family/gospel" : "0.021572844",
          "romantic" : "0.021295252",
          "communication" : "0.225862214",
          "obscene" : "0.000848897",
          "music" : "0.171102392",
          "movement/places" : "0.034934221",
          "light/visual_perceptions" : "0.000848896",
          "family/spiritual" : "0.039161587",
          "like/girls" : "0.000848896",
          "sadness" : "0.000848896",
          "feelings" : "0.063833801",
          "danceability" : "0.633921802",
          "loudness" : "0.751967797",
          "acousticness" : "0.057529174",
          "instrumentalness" : "1.37E-06",
          "valence" : "0.773289365",
          "energy" : "0.755748127",
          "topic" : "violence",
          "age" : "0.371428571"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line14966-6cxYw5YmdMjwxkRcVXRwbh",
        "_score" : 5.8244166,
        "_source" : {
          "row_identifier" : "47779",
          "artist_name" : "blues traveler",
          "track_name" : "optimistic thought",
          "release_date" : "1991",
          "genre" : "blues",
          "lyrics" : "wake shady remember lady maybe have lot see wear leather navel feather crack smile close eye prayer begin say life embrace shall honour disgrace forgive replace go pain clearly come nearly human early swear forget explorer go wander satisfy ponder basically meander unsure brave danger family stranger time time turn run mind say life embrace shall disgrace forgive replace go pain clearly come nearly human early swear forget multitude story clean gory need worry sell buy spin granite like planet need contemplate optimistic think life embrace shall disgrace forgive replace go pain clearly come nearly human early swear forget life embrace shall disgrace forgive replace go pain clearly come nearly human early swear forget",
          "len" : "114",
          "dating" : "0.041437437",
          "violence" : "0.213042116",
          "world/life" : "0.338093367",
          "night/time" : "0.000711238",
          "shake_the_audience" : "0.000711238",
          "family/gospel" : "0.000711238",
          "romantic" : "0.000711238",
          "communication" : "0.1229048",
          "obscene" : "0.000711238",
          "music" : "0.000711238",
          "movement/places" : "0.071228364",
          "light/visual_perceptions" : "0.000711238",
          "family/spiritual" : "0.076764828",
          "like/girls" : "0.000711238",
          "sadness" : "0.000711238",
          "feelings" : "0.127994237",
          "danceability" : "0.643669447",
          "loudness" : "0.67902469",
          "acousticness" : "0.097087447",
          "instrumentalness" : "2.48E-05",
          "valence" : "0.848516076",
          "energy" : "0.805799741",
          "topic" : "world/life",
          "age" : "0.414285714"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line15048-4sQJDDgVdDqtLvjkhZuPix",
        "_score" : 5.8244166,
        "_source" : {
          "row_identifier" : "48064",
          "artist_name" : "blues traveler",
          "track_name" : "whoops",
          "release_date" : "1993",
          "genre" : "blues",
          "lyrics" : "see atom little bits float good look collectively compose include brilliant puzzle live rubix cube think figure solve monkey scratch head try open ears chord resolve wisdom intellect truest sense word security mean accord hear ease heart mind feel free reach paradise hilltop try possibility exist matter scary paradise world wasn dream earth heaven know rule break maybe late clever hell whoop whoop whoop whoop corner weigh weight imaginable life surround corner weigh sound user friendly idea finally bring pesky mountain gentlemen sound harmonica solo come fight look horizon quiet know bison gentlemen land waste gotta wonder know chop breathe fodder right starve death want goddamn thing look shrug imagine straightest line finger control frustration yield relief mortal mean torture chimpanzee infect disease scream like human child study desperate pleas possibility exist matter scary paradise world wasn dream earth heaven know rule break maybe late clever hell whoop whoop subject know conscience hurt away concoct pill think clever look mirror polish glass need cringe forget sink feel dinosaur drunken binge fossil fossil dust dust earthy crust whoop whoop",
          "len" : "178",
          "dating" : "0.000572082",
          "violence" : "0.302405762",
          "world/life" : "0.09248122",
          "night/time" : "0.000572082",
          "shake_the_audience" : "0.000572082",
          "family/gospel" : "0.012430007",
          "romantic" : "0.000572082",
          "communication" : "0.329142091",
          "obscene" : "0.000572082",
          "music" : "0.000572082",
          "movement/places" : "0.000572082",
          "light/visual_perceptions" : "0.073619514",
          "family/spiritual" : "0.069615914",
          "like/girls" : "0.000572082",
          "sadness" : "0.074148487",
          "feelings" : "0.026002068",
          "danceability" : "0.536445359",
          "loudness" : "0.598415506",
          "acousticness" : "0.000201807",
          "instrumentalness" : "0.000482794",
          "valence" : "0.611500412",
          "energy" : "0.546532384",
          "topic" : "violence",
          "age" : "0.385714286"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line15059-77eEVDGDVYrQ4W73Q3a1sM",
        "_score" : 5.8244166,
        "_source" : {
          "row_identifier" : "48106",
          "artist_name" : "blues traveler",
          "track_name" : "love of my life",
          "release_date" : "1993",
          "genre" : "blues",
          "lyrics" : "couldn matter hard know share dead give letter word write swear say say say life night rain talk forever life carefree show potential life tell today place go carefree realize say say life finally carefree wasn mean pain feel understand think pull away hand life tell today place go carefree realize know realize learn days burn need learn days burn need learn days burn say say life arm hold tight need life believe know leave life tell today place go carefree realize realize occur life start",
          "len" : "86",
          "dating" : "0.000657895",
          "violence" : "0.032361477",
          "world/life" : "0.457255054",
          "night/time" : "0.000657895",
          "shake_the_audience" : "0.000657895",
          "family/gospel" : "0.000657895",
          "romantic" : "0.049889526",
          "communication" : "0.351701493",
          "obscene" : "0.000657895",
          "music" : "0.000657895",
          "movement/places" : "0.000657895",
          "light/visual_perceptions" : "0.066168784",
          "family/spiritual" : "0.000657895",
          "like/girls" : "0.000657895",
          "sadness" : "0.000657895",
          "feelings" : "0.034071035",
          "danceability" : "0.357738547",
          "loudness" : "0.582544932",
          "acousticness" : "0.000511045",
          "instrumentalness" : "0.004251012",
          "valence" : "0.309563067",
          "energy" : "0.534519997",
          "topic" : "world/life",
          "age" : "0.385714286"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line15096-qehxFsr1BoEmoog6qRDBi9",
        "_score" : 5.8244166,
        "_source" : {
          "row_identifier" : "48212",
          "artist_name" : "blues traveler",
          "track_name" : "trina magna",
          "release_date" : "1993",
          "genre" : "blues",
          "lyrics" : "teach lead come live leave lesson store like guess asses try guess turn forgive chalk knowledge change life shall learn follow fee leaders bring revolutions understand like pretend guess couldn tell turn forgive chalk knowledge change life cycle share pass hand hand pride despair parent child apathy everybody care vanish time time legacy history hold question story begin blind pass goddamn horizon see father life death merely pretend infinite end gonna teach learn gonna shall fee ancient brand spank shall follow lead cause simply prove traditions brink heaven hell turn forgive knowledge change life knowledge change life knowledge change life",
          "len" : "100",
          "dating" : "0.000711238",
          "violence" : "0.115954841",
          "world/life" : "0.574299639",
          "night/time" : "0.000711238",
          "shake_the_audience" : "0.014590193",
          "family/gospel" : "0.000711238",
          "romantic" : "0.000711238",
          "communication" : "0.153977299",
          "obscene" : "0.000711238",
          "music" : "0.000711238",
          "movement/places" : "0.000711238",
          "light/visual_perceptions" : "0.000711238",
          "family/spiritual" : "0.101723713",
          "like/girls" : "0.000711238",
          "sadness" : "0.000711238",
          "feelings" : "0.000711238",
          "danceability" : "0.396729124",
          "loudness" : "0.667999897",
          "acousticness" : "0.003091369",
          "instrumentalness" : "0.00037753",
          "valence" : "0.674361088",
          "energy" : "0.715706837",
          "topic" : "world/life",
          "age" : "0.385714286"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line15139-8E5N7qR7jmPx1jFNxXKUeG",
        "_score" : 5.8244166,
        "_source" : {
          "row_identifier" : "48356",
          "artist_name" : "blues traveler",
          "track_name" : "fallible",
          "release_date" : "1994",
          "genre" : "blues",
          "lyrics" : "indignation smile paint porcelain face suppose trust decorum place question suddenly smile doth crack slip beneath mask fallible yeah fallible hold mirror hate trek westward infallibly wanna touch place wanna hide dare come commit narcisside punish guilty intent bust prison baby go fallible yeah fallible hold mirror hate trek westward infallibly power center hand crave revolution possession stand moment come go best stay awake path cause fallible yeah fallible hold mirror hate trek westward infallibly infallibly",
          "len" : "76",
          "dating" : "0.05260428",
          "violence" : "0.395124456",
          "world/life" : "0.00122399",
          "night/time" : "0.00122399",
          "shake_the_audience" : "0.07420004",
          "family/gospel" : "0.00122399",
          "romantic" : "0.130854276",
          "communication" : "0.076073538",
          "obscene" : "0.00122399",
          "music" : "0.00122399",
          "movement/places" : "0.00122399",
          "light/visual_perceptions" : "0.00122399",
          "family/spiritual" : "0.00122399",
          "like/girls" : "0.00122399",
          "sadness" : "0.153726023",
          "feelings" : "0.037708095",
          "danceability" : "0.570020578",
          "loudness" : "0.74458375",
          "acousticness" : "0.008041173",
          "instrumentalness" : "0.000152834",
          "valence" : "0.541426216",
          "energy" : "0.931929806",
          "topic" : "violence",
          "age" : "0.371428571"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line15142-933UZhD2SVUazspJopj6yr",
        "_score" : 5.8244166,
        "_source" : {
          "row_identifier" : "48367",
          "artist_name" : "blues traveler",
          "track_name" : "the good, the bad and the ugly",
          "release_date" : "1994",
          "genre" : "blues",
          "lyrics" : "musical opus kinchla blue traveler instrumental",
          "len" : "6",
          "dating" : "0.026315789",
          "violence" : "0.026315789",
          "world/life" : "0.026315789",
          "night/time" : "0.026315789",
          "shake_the_audience" : "0.026315789",
          "family/gospel" : "0.026315789",
          "romantic" : "0.026315789",
          "communication" : "0.026315789",
          "obscene" : "0.026315789",
          "music" : "0.526315789",
          "movement/places" : "0.02631579",
          "light/visual_perceptions" : "0.026315789",
          "family/spiritual" : "0.026315789",
          "like/girls" : "0.026315789",
          "sadness" : "0.026315789",
          "feelings" : "0.026315789",
          "danceability" : "0.297086537",
          "loudness" : "0.707278927",
          "acousticness" : "0.000425703",
          "instrumentalness" : "0.519230769",
          "valence" : "0.701154163",
          "energy" : "0.944943225",
          "topic" : "music",
          "age" : "0.371428571"
        }
      },
      {
        "_index" : "as5664_info624_202202_music",
        "_type" : "_doc",
        "_id" : "line15147-eBDqzAdWA6htR6TAPGWW4p",
        "_score" : 5.8244166,
        "_source" : {
          "row_identifier" : "48391",
          "artist_name" : "blues traveler",
          "track_name" : "stand",
          "release_date" : "1994",
          "genre" : "blues",
          "lyrics" : "stand stand walk tragedy cheap talk decision come cause long fall thunder scare lightning little pressure dime wound heal time cause long fall answer get harder answer get harder answer get harder answer come pray answer get harder answer come pray answer get harder answer come pray answer get harder harder bargain barter angst ardor faint fight gonna challenge paradise accept lose stand tall know long fall yeah cause long fall long fall badiddela badidela deddle stand stand wallk stand",
          "len" : "80",
          "dating" : "0.000956938",
          "violence" : "0.471220558",
          "world/life" : "0.000956938",
          "night/time" : "0.148329363",
          "shake_the_audience" : "0.020364847",
          "family/gospel" : "0.033567213",
          "romantic" : "0.000956938",
          "communication" : "0.195624675",
          "obscene" : "0.000956938",
          "music" : "0.000956938",
          "movement/places" : "0.000956938",
          "light/visual_perceptions" : "0.000956938",
          "family/spiritual" : "0.000956938",
          "like/girls" : "0.000956938",
          "sadness" : "0.098142488",
          "feelings" : "0.000956938",
          "danceability" : "0.498537853",
          "loudness" : "0.75432659",
          "acousticness" : "0.105420789",
          "instrumentalness" : "0.000151822",
          "valence" : "0.501236603",
          "energy" : "0.861857548",
          "topic" : "violence",
          "age" : "0.371428571"
        }
      }
    ]
  }
}

```


## Use Case 1: Relevance Assessment

|                               Use Case 1                                                                   |
|------------------------------------------------------------------------------------------------------------|
| Query Keywords: scent bone heart stick emptiness                                                           |
| Query Information Need: to find songs that have the exact lyrics of "scent bone heart stick emptiness"     |
|------------------------------------------------------------------------------------------------------------|
| Doc ID                              | Artist             | Track_Name       | Genre  | Score   | Relevance |
|------------------------------------------------------------------------------------------------------------|
| line2125-xaiaAokVZ6wVhJcr1SsmCS     | blondie            | rifle range      | pop    | 55.74   |     1     |
| line27362-bMEsbfaVmJEMPetDXxz2dK    | grandson           | stick up         | rock   | 39.70   |     0     |
| line937-afmpchv54uazUPLgkgYRBS      | the zombies        | sticks and stones| pop    | 38.47   |     0     |
| line16834-5Dca6jqMUH6Nu8r7ujxANp    | alice cooper       | paranormal       | blues  | 36.03   |     0     |
| line25719-irdoWaJEboYbuZdbKS8Z7N    | metallica          | mama said        | rock   | 34.57   |     0     |
| line26505-6PDiFA1anbCfGWctezbqxf    | mudvayne           | do what you do   | rock   | 32.10   |     0     |
| line8322-xm1FeTHBR2cug929yH2HKW     | derek & the dominos| i am yours       | country| 31.82   |     0     |
| line14012-nwEgSc7dkynj5tRVwwiGAr    | the fall           | dice man         | blues  | 31.78   |     0     |
| line290-e47L6BRuCr4csJhRBPiY1H      | ritchie valens     | paddiwack song   | pop    | 31.13   |     0     |
| line13437-dUCKnSp3UNG2tVgR1uGS2L    | joe cocker         | ticks and stones | blues  | 30.80   |     0     |





## Use Case 2: Relevance Assessment

|                               Use Case 2                                                                                   |
|----------------------------------------------------------------------------------------------------------------------------|
| Query Keywords:  0.97                                                                                                      |
| Query Information Need: to find multiple songs with a high danceability score                                              |
|----------------------------------------------------------------------------------------------------------------------------|
| Doc ID                              | Artist                | Track_Name       | Genre  | Danceability Score   | Relevance |
|----------------------------------------------------------------------------------------------------------------------------|
| line27614-f14pmqCLzU2ceJBr4H5tmj    | vanilla ice           | ice ice baby     | hip hop| 0.99350157           |     1     |
| line18885-6QZXNQ2MndhfVGCwfwuX7H    | jungle brothers       | black is black   | jazz   | 0.991335427          |     1     |
| line5621-jzfEBwvPuJy3QQuWJWnoz1     | timbaland             | give it to me    | pop    | 0.987003141          |     1     |
| line5479-orEGsG8nAvEdgzLGWTjskS     |justin timberlake      | sexyback         | pop    | 0.980504711          |     1     |
| line19665-3f8z4V1HFiSwgcsSJr6XCt    | georg levin           | somebody new     | jazz   | 0.97942164           |     1     |
| line6847-5g8E7uniTJPvXJzCrHeEY4     | selena gomez          | bad liar         | pop    | 0.978338568          |     1     |
| line21068-beACfceNoj2bm74wHneNTo    | jimmy cliff           | struggling man   | reggae | 0.976172425          |     1     |
| line22968-wMAgBETuzAJfD8kJ3rVhF4    | fortunate youth       | melody           | reggae | 0.976172425          |     1     |
| line28101-nj7zKgdcqETaNrPiRKrUtn    |machine gun kelly      | trap paris       | hip hop| 0.976172425          |     1     |
| line27471-oH5R4n5yePph9Bet1crSD3    |boogie down productions| jack of spades   | hip hop| 0.971840139          |     1     |


## Use Case 3: Relevance Assessment

|                               Use Case 3                                                                           |
|--------------------------------------------------------------------------------------------------------------------|
| Query Keywords: blues                                                                                              |
| Query Information Need: find a range of songs in the genre of blues                                                |
|--------------------------------------------------------------------------------------------------------------------|
| Doc ID                              | Artist         | Track_Name                   | Genre  | Score   | Relevance |
|--------------------------------------------------------------------------------------------------------------------|
| line18731-kUEMW5Z5phGENC4Xkbo7ii    | wynton marsalis| blues                        | jazz   | 6.63    |     0     |
| line3802-eh4fZpypQkWxgk8nbfTeLa     | blues traveler | all in the groove            | pop    | 5.82    |     0     |
| line4216-FzyMtf7gBrBwk95EZaTfp      | blues traveler | hook                         | pop    | 5.82    |     0     |
| line14966-6cxYw5YmdMjwxkRcVXRwbh    | blues traveler |optimistic thought            | blues  | 5.82    |     1     |
| line15048-4sQJDDgVdDqtLvjkhZuPix    | blues traveler | whoops                       | blues  | 5.82    |     1     |
| line15059-77eEVDGDVYrQ4W73Q3a1sM    | blues traveler | love of my life              | blues  | 5.82    |     1     |
| line15096-qehxFsr1BoEmoog6qRDBi9    | blues traveler | trina magna                  | blues  | 5.82    |     1     |
| line15139-8E5N7qR7jmPx1jFNxXKUeG    | blues traveler | fallible                     | blues  | 5.82    |     1     |
| line15142-933UZhD2SVUazspJopj6yr    | blues traveler |the good, the bad and the ugly| blues  | 5.82    |     1     |
| line15147-eBDqzAdWA6htR6TAPGWW4p    | blues traveler | stand                        | blues  | 5.82    |     1     |


## Use Case 1: Search Result Evaluation

Request:
```json
GET as5664_info624_202202_music/_search
{
  "from": 0, "size": 3,
  "query": {
    "multi_match": {
      "query": "scent bone heart stick emptiness",
      "fields": ["artist_name", "track_name", "genre", "lyrics^3"]
    }
  }
}
```

Results (top 3):
| Doc ID                              | Artist             | Track_Name       | Genre  | Score   | Relevance |
|------------------------------------------------------------------------------------------------------------|
| line2125-xaiaAokVZ6wVhJcr1SsmCS     | blondie            | rifle range      | pop    | 55.74   |     1     |
| line27362-bMEsbfaVmJEMPetDXxz2dK    | grandson           | stick up         | rock   | 39.70   |     0     |
| line937-afmpchv54uazUPLgkgYRBS      | the zombies        | sticks and stones| pop    | 38.47   |     0     |


                   | Relevant  | Non-relevant  |
|------------------|-----------|---------------|
| Retrieved        |    1      |       2       |
| Not Retrieved    |    0      |       7       |

Precision = tp / (tp + fp) = 1 / (1 + 2) = 1 / 3 = 0.66667
Recall = tp / (tp + fn) = 1 / (1 + 0) = 1 / 1 = 1.0000
F1 Score = 2PR / (P + R) = 2(0.66667)(1) / (0.66667 + 1) = 1.33334 / 1.66667 = 0.8000
DCG = 


## Use Case 2: Search Result Evaluation

Request:
```json
GET as5664_info624_202202_music/_search
{
  "from": 0, "size": 3,
  "query": {
    "range": {
      "danceability": {
        "gt": 0.97
      }
    }
  },
  "sort": [
    {"danceability": {"order": "desc"}}
    ]
}
```

Results (top 3):
| Doc ID                              | Artist                | Track_Name       | Genre  | Danceability Score   | Relevance |
|----------------------------------------------------------------------------------------------------------------------------|
| line27614-f14pmqCLzU2ceJBr4H5tmj    | vanilla ice           | ice ice baby     | hip hop| 0.99350157           |     1     |
| line18885-6QZXNQ2MndhfVGCwfwuX7H    | jungle brothers       | black is black   | jazz   | 0.991335427          |     1     |
| line5621-jzfEBwvPuJy3QQuWJWnoz1     | timbaland             | give it to me    | pop    | 0.987003141          |     1     |


                   | Relevant  | Non-relevant  |
|------------------|-----------|---------------|
| Retrieved        |     3     |      0        |
| Not Retrieved    |     7     |      0        |

Precision = tp / (tp + fp) = 3 / (3 + 0) = 3 / 3 = 1.0000
Recall = tp / (tp + fn) = 3 / (3 + 7) = 3 / 10 = 0.3000
F1 Score = 2PR / (P + R) = 2(1)(0.30) / (1 + 0.30) = 0.60 / 1.30 = 0.4615
DCG = 


## Use Case 2: Search Result Evaluation

Request:
```json
GET as5664_info624_202202_music/_search
{
  "from": 0, "size": 3,
  "query": {
    "multi_match": {
      "query": "blues",
      "fields": ["artist_name", "track_name", "genre^3", "lyrics"]
    }
  }
}
```

Results (top 3):
| Doc ID                              | Artist         | Track_Name                   | Genre  | Score   | Relevance |
|--------------------------------------------------------------------------------------------------------------------|
| line18731-kUEMW5Z5phGENC4Xkbo7ii    | wynton marsalis| blues                        | jazz   | 6.63    |     0     |
| line3802-eh4fZpypQkWxgk8nbfTeLa     | blues traveler | all in the groove            | pop    | 5.82    |     0     |
| line4216-FzyMtf7gBrBwk95EZaTfp      | blues traveler | hook                         | pop    | 5.82    |     0     |


                   | Relevant  | Non-relevant  |
|------------------|-----------|---------------|
| Retrieved        |    0      |      3        |
| Not Retrieved    |    7      |      0        |

Precision = tp / (tp + fp) = 0 / (0 + 3) = 0 / 3 = 0
Recall = tp / (tp + fn) = 0 / (0 + 7) = 0 / 7 = 0
F1 Score = 2PR / (P + R) = 2(0)(0) / (0 + 0) = 0 / 0 = 0
DCG = 