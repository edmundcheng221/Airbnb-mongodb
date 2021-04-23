# AirBnB MongoDB Analysis

A little assignment to practice importing and analyzing data within a MongoDB database.

# Part 1: Data Selection and Import

## Data Set Details
This data set was pulled from [inside airbnb](http://insideairbnb.com/get-the-data.html). The data is sourced from public information from the Airbnb site. This site provides data sets from many cities and countries around the world. The particular data set that I was interested in and used in my analysis is the dataset containing the listings in Amsterdam, Netherlands.

The data was in CSV format originally.

Here is what the raw data looks like:
There's a lot of data so I didn't put 20 rows because it takes up too much space. I think this is enough to get a clear idea of what the original data looks like.

|id|listing_url|scrape_id|last_scraped|name|description|neighborhood_overview|picture_url|host_id|host_url|host_name|host_since|host_location|host_about|host_response_time|host_response_rate|host_acceptance_rate|host_is_superhost|host_thumbnail_url|host_picture_url|host_neighbourhood|host_listings_count|host_total_listings_count|host_verifications|host_has_profile_pic|host_identity_verified|neighbourhood|neighbourhood_cleansed|neighbourhood_group_cleansed|latitude|longitude|property_type|room_type|accommodates|bathrooms|bathrooms_text|bedrooms|beds|amenities|price|minimum_nights|maximum_nights|minimum_minimum_nights|maximum_minimum_nights|minimum_maximum_nights|maximum_maximum_nights|minimum_nights_avg_ntm|maximum_nights_avg_ntm|calendar_updated|has_availability|availability_30|availability_60|availability_90|availability_365|calendar_last_scraped|number_of_reviews|number_of_reviews_ltm|number_of_reviews_l30d|first_review|last_review|review_scores_rating|review_scores_accuracy|review_scores_cleanliness|review_scores_checkin|review_scores_communication|review_scores_location|review_scores_value|license|instant_bookable|calculated_host_listings_count|calculated_host_listings_count_entire_homes|calculated_host_listings_count_private_rooms|calculated_host_listings_count_shared_rooms|reviews_per_month|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|2818	|https://www.airbnb.com/rooms/2818	|2.02102E+13|	2/11/21|	Quiet Garden View Room & Super Fast WiFi|	Quiet Garden View Room & Super Fast WiFi<br /><br /><b>The space</b><br />I'm renting a bedroom (room overlooking the garden) in my apartment in Amsterdam, <br /><br />The room is located to the east of the city centre in a quiet, typical Amsterdam neighbourhood the "Indische Buurt". Amsterdam‚Äôs historic centre is less than 15 minutes away by bike or tram.<br /><br /><br />The features of the room are:<br /><br />- Twin beds (80 x 200 cm, down quilts and pillows) <br />- 2 pure cotton towels for each guest <br />- reading lamps<br />- bedside table<br />- wardrobe<br />- table with chairs<br />- tea and coffee making facilities<br />- mini bar<br />- alarm clock<br />- Hi-Fi system with cd player, connection for mp3 player / phone<br />- map of Amsterdam and public transport<br />- Wi-Fi Internet connection <br /><br />Extra services:<br /><br />- Bike rental |Indische Buurt ("Indies Neighborhood") is a neighbourhood in the eastern portion of the city of Amsterdam, in the Dutch province of Noord-Holland. The name dates from the early 20th century and is derived from the fact that the neighbourhood's streets are named after islands and other geographical concepts in the former Dutch colony of the Dutch East Indies. The first street was named in 1902. In 2003, there were around 23,357 inhabitants. The neighbourhood is bounded on the west by the railroad Amsterdam - Hilversum (with the Muiderpoort Station), on the east side by Flevopark, on the north side by Zeeburgerdijk and on the south side by the Ringvaart Watergraafsmeer. Indische Buurt is the oldest part of the Zeeburg district and is very ethnically diverse, and a high percentage of the population is of immigrant origin (for Zeeburg this is already high at 55%, but higher in the Indische Buurt) and there are an estimated 100 languages spoken.|https://a0.muscache.com/pictures/10272854/8dcca016_original.jpg|3159|https://www.airbnb.com/users/show/3159|Daniel|9/24/08|Amsterdam, Noord-Holland, The Netherlands|"Upon arriving in Amsterdam, one can imagine asking oneself: Where is the fun nightlife? What are the local hot spots? How can I experience the real life in this city? I  offer you the opportunity to act, eat and sleep like-a-local!  I provide the traveler with the opportunity to connect with the local life in Amsterdam."|N/A|N/A|100%|t|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_small|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_x_medium|Indische Buurt|1|1|['email', 'phone', 'reviews', 'jumio', 'offline_government_id', 'selfie', 'government_id', 'identity_manual']|t|t|Amsterdam, North Holland, Netherlands|Oostelijk Havengebied - Indische Buurt| |52.36575|4.94142|Private room in apartment|Private room|2| |1.5 shared baths|1|2|["Hangers", "Coffee maker", "Paid parking on premises", "Long term stays allowed", "First aid kit", "Bed linens", "Lock on bedroom door", "Private entrance", "Carbon monoxide alarm", "Dedicated workspace", "Host greets you", "Single level home", "Extra pillows and blankets", "Hot water", "Paid parking off premises", "Heating", "Garden or backyard", "Hair dryer", "Essentials", "Smoke alarm", "Washer", "Refrigerator", "Iron", "Shampoo", "Ethernet connection", "Wifi", "Fire extinguisher"]|$59.00 |3|1125|3|3|1125|1125|3|1125| |t|29|46|60|139|2/11/21|278|1|0|3/30/09|2/14/20|98|10|10|1010|9|10| ||t|1|0|1|0|1.92|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|2818	|https://www.airbnb.com/rooms/2818	|2.02102E+13|	2/11/21|	Quiet Garden View Room & Super Fast WiFi|	Quiet Garden View Room & Super Fast WiFi<br /><br /><b>The space</b><br />I'm renting a bedroom (room overlooking the garden) in my apartment in Amsterdam, <br /><br />The room is located to the east of the city centre in a quiet, typical Amsterdam neighbourhood the "Indische Buurt". Amsterdam‚Äôs historic centre is less than 15 minutes away by bike or tram.<br /><br /><br />The features of the room are:<br /><br />- Twin beds (80 x 200 cm, down quilts and pillows) <br />- 2 pure cotton towels for each guest <br />- reading lamps<br />- bedside table<br />- wardrobe<br />- table with chairs<br />- tea and coffee making facilities<br />- mini bar<br />- alarm clock<br />- Hi-Fi system with cd player, connection for mp3 player / phone<br />- map of Amsterdam and public transport<br />- Wi-Fi Internet connection <br /><br />Extra services:<br /><br />- Bike rental |Indische Buurt ("Indies Neighborhood") is a neighbourhood in the eastern portion of the city of Amsterdam, in the Dutch province of Noord-Holland. The name dates from the early 20th century and is derived from the fact that the neighbourhood's streets are named after islands and other geographical concepts in the former Dutch colony of the Dutch East Indies. The first street was named in 1902. In 2003, there were around 23,357 inhabitants. The neighbourhood is bounded on the west by the railroad Amsterdam - Hilversum (with the Muiderpoort Station), on the east side by Flevopark, on the north side by Zeeburgerdijk and on the south side by the Ringvaart Watergraafsmeer. Indische Buurt is the oldest part of the Zeeburg district and is very ethnically diverse, and a high percentage of the population is of immigrant origin (for Zeeburg this is already high at 55%, but higher in the Indische Buurt) and there are an estimated 100 languages spoken.|https://a0.muscache.com/pictures/10272854/8dcca016_original.jpg|3159|https://www.airbnb.com/users/show/3159|Daniel|9/24/08|Amsterdam, Noord-Holland, The Netherlands|"Upon arriving in Amsterdam, one can imagine asking oneself: Where is the fun nightlife? What are the local hot spots? How can I experience the real life in this city? I  offer you the opportunity to act, eat and sleep like-a-local!  I provide the traveler with the opportunity to connect with the local life in Amsterdam."|N/A|N/A|100%|t|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_small|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_x_medium|Indische Buurt|1|1|['email', 'phone', 'reviews', 'jumio', 'offline_government_id', 'selfie', 'government_id', 'identity_manual']|t|t|Amsterdam, North Holland, Netherlands|Oostelijk Havengebied - Indische Buurt| |52.36575|4.94142|Private room in apartment|Private room|2| |1.5 shared baths|1|2|["Hangers", "Coffee maker", "Paid parking on premises", "Long term stays allowed", "First aid kit", "Bed linens", "Lock on bedroom door", "Private entrance", "Carbon monoxide alarm", "Dedicated workspace", "Host greets you", "Single level home", "Extra pillows and blankets", "Hot water", "Paid parking off premises", "Heating", "Garden or backyard", "Hair dryer", "Essentials", "Smoke alarm", "Washer", "Refrigerator", "Iron", "Shampoo", "Ethernet connection", "Wifi", "Fire extinguisher"]|$59.00 |3|1125|3|3|1125|1125|3|1125| |t|29|46|60|139|2/11/21|278|1|0|3/30/09|2/14/20|98|10|10|1010|9|10| ||t|1|0|1|0|1.92|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|2818	|https://www.airbnb.com/rooms/2818	|2.02102E+13|	2/11/21|	Quiet Garden View Room & Super Fast WiFi|	Quiet Garden View Room & Super Fast WiFi<br /><br /><b>The space</b><br />I'm renting a bedroom (room overlooking the garden) in my apartment in Amsterdam, <br /><br />The room is located to the east of the city centre in a quiet, typical Amsterdam neighbourhood the "Indische Buurt". Amsterdam‚Äôs historic centre is less than 15 minutes away by bike or tram.<br /><br /><br />The features of the room are:<br /><br />- Twin beds (80 x 200 cm, down quilts and pillows) <br />- 2 pure cotton towels for each guest <br />- reading lamps<br />- bedside table<br />- wardrobe<br />- table with chairs<br />- tea and coffee making facilities<br />- mini bar<br />- alarm clock<br />- Hi-Fi system with cd player, connection for mp3 player / phone<br />- map of Amsterdam and public transport<br />- Wi-Fi Internet connection <br /><br />Extra services:<br /><br />- Bike rental |Indische Buurt ("Indies Neighborhood") is a neighbourhood in the eastern portion of the city of Amsterdam, in the Dutch province of Noord-Holland. The name dates from the early 20th century and is derived from the fact that the neighbourhood's streets are named after islands and other geographical concepts in the former Dutch colony of the Dutch East Indies. The first street was named in 1902. In 2003, there were around 23,357 inhabitants. The neighbourhood is bounded on the west by the railroad Amsterdam - Hilversum (with the Muiderpoort Station), on the east side by Flevopark, on the north side by Zeeburgerdijk and on the south side by the Ringvaart Watergraafsmeer. Indische Buurt is the oldest part of the Zeeburg district and is very ethnically diverse, and a high percentage of the population is of immigrant origin (for Zeeburg this is already high at 55%, but higher in the Indische Buurt) and there are an estimated 100 languages spoken.|https://a0.muscache.com/pictures/10272854/8dcca016_original.jpg|3159|https://www.airbnb.com/users/show/3159|Daniel|9/24/08|Amsterdam, Noord-Holland, The Netherlands|"Upon arriving in Amsterdam, one can imagine asking oneself: Where is the fun nightlife? What are the local hot spots? How can I experience the real life in this city? I  offer you the opportunity to act, eat and sleep like-a-local!  I provide the traveler with the opportunity to connect with the local life in Amsterdam."|N/A|N/A|100%|t|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_small|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_x_medium|Indische Buurt|1|1|['email', 'phone', 'reviews', 'jumio', 'offline_government_id', 'selfie', 'government_id', 'identity_manual']|t|t|Amsterdam, North Holland, Netherlands|Oostelijk Havengebied - Indische Buurt| |52.36575|4.94142|Private room in apartment|Private room|2| |1.5 shared baths|1|2|["Hangers", "Coffee maker", "Paid parking on premises", "Long term stays allowed", "First aid kit", "Bed linens", "Lock on bedroom door", "Private entrance", "Carbon monoxide alarm", "Dedicated workspace", "Host greets you", "Single level home", "Extra pillows and blankets", "Hot water", "Paid parking off premises", "Heating", "Garden or backyard", "Hair dryer", "Essentials", "Smoke alarm", "Washer", "Refrigerator", "Iron", "Shampoo", "Ethernet connection", "Wifi", "Fire extinguisher"]|$59.00 |3|1125|3|3|1125|1125|3|1125| |t|29|46|60|139|2/11/21|278|1|0|3/30/09|2/14/20|98|10|10|1010|9|10| ||t|1|0|1|0|1.92|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|2818	|https://www.airbnb.com/rooms/2818	|2.02102E+13|	2/11/21|	Quiet Garden View Room & Super Fast WiFi|	Quiet Garden View Room & Super Fast WiFi<br /><br /><b>The space</b><br />I'm renting a bedroom (room overlooking the garden) in my apartment in Amsterdam, <br /><br />The room is located to the east of the city centre in a quiet, typical Amsterdam neighbourhood the "Indische Buurt". Amsterdam‚Äôs historic centre is less than 15 minutes away by bike or tram.<br /><br /><br />The features of the room are:<br /><br />- Twin beds (80 x 200 cm, down quilts and pillows) <br />- 2 pure cotton towels for each guest <br />- reading lamps<br />- bedside table<br />- wardrobe<br />- table with chairs<br />- tea and coffee making facilities<br />- mini bar<br />- alarm clock<br />- Hi-Fi system with cd player, connection for mp3 player / phone<br />- map of Amsterdam and public transport<br />- Wi-Fi Internet connection <br /><br />Extra services:<br /><br />- Bike rental |Indische Buurt ("Indies Neighborhood") is a neighbourhood in the eastern portion of the city of Amsterdam, in the Dutch province of Noord-Holland. The name dates from the early 20th century and is derived from the fact that the neighbourhood's streets are named after islands and other geographical concepts in the former Dutch colony of the Dutch East Indies. The first street was named in 1902. In 2003, there were around 23,357 inhabitants. The neighbourhood is bounded on the west by the railroad Amsterdam - Hilversum (with the Muiderpoort Station), on the east side by Flevopark, on the north side by Zeeburgerdijk and on the south side by the Ringvaart Watergraafsmeer. Indische Buurt is the oldest part of the Zeeburg district and is very ethnically diverse, and a high percentage of the population is of immigrant origin (for Zeeburg this is already high at 55%, but higher in the Indische Buurt) and there are an estimated 100 languages spoken.|https://a0.muscache.com/pictures/10272854/8dcca016_original.jpg|3159|https://www.airbnb.com/users/show/3159|Daniel|9/24/08|Amsterdam, Noord-Holland, The Netherlands|"Upon arriving in Amsterdam, one can imagine asking oneself: Where is the fun nightlife? What are the local hot spots? How can I experience the real life in this city? I  offer you the opportunity to act, eat and sleep like-a-local!  I provide the traveler with the opportunity to connect with the local life in Amsterdam."|N/A|N/A|100%|t|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_small|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_x_medium|Indische Buurt|1|1|['email', 'phone', 'reviews', 'jumio', 'offline_government_id', 'selfie', 'government_id', 'identity_manual']|t|t|Amsterdam, North Holland, Netherlands|Oostelijk Havengebied - Indische Buurt| |52.36575|4.94142|Private room in apartment|Private room|2| |1.5 shared baths|1|2|["Hangers", "Coffee maker", "Paid parking on premises", "Long term stays allowed", "First aid kit", "Bed linens", "Lock on bedroom door", "Private entrance", "Carbon monoxide alarm", "Dedicated workspace", "Host greets you", "Single level home", "Extra pillows and blankets", "Hot water", "Paid parking off premises", "Heating", "Garden or backyard", "Hair dryer", "Essentials", "Smoke alarm", "Washer", "Refrigerator", "Iron", "Shampoo", "Ethernet connection", "Wifi", "Fire extinguisher"]|$59.00 |3|1125|3|3|1125|1125|3|1125| |t|29|46|60|139|2/11/21|278|1|0|3/30/09|2/14/20|98|10|10|1010|9|10| ||t|1|0|1|0|1.92|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|2818	|https://www.airbnb.com/rooms/2818	|2.02102E+13|	2/11/21|	Quiet Garden View Room & Super Fast WiFi|	Quiet Garden View Room & Super Fast WiFi<br /><br /><b>The space</b><br />I'm renting a bedroom (room overlooking the garden) in my apartment in Amsterdam, <br /><br />The room is located to the east of the city centre in a quiet, typical Amsterdam neighbourhood the "Indische Buurt". Amsterdam‚Äôs historic centre is less than 15 minutes away by bike or tram.<br /><br /><br />The features of the room are:<br /><br />- Twin beds (80 x 200 cm, down quilts and pillows) <br />- 2 pure cotton towels for each guest <br />- reading lamps<br />- bedside table<br />- wardrobe<br />- table with chairs<br />- tea and coffee making facilities<br />- mini bar<br />- alarm clock<br />- Hi-Fi system with cd player, connection for mp3 player / phone<br />- map of Amsterdam and public transport<br />- Wi-Fi Internet connection <br /><br />Extra services:<br /><br />- Bike rental |Indische Buurt ("Indies Neighborhood") is a neighbourhood in the eastern portion of the city of Amsterdam, in the Dutch province of Noord-Holland. The name dates from the early 20th century and is derived from the fact that the neighbourhood's streets are named after islands and other geographical concepts in the former Dutch colony of the Dutch East Indies. The first street was named in 1902. In 2003, there were around 23,357 inhabitants. The neighbourhood is bounded on the west by the railroad Amsterdam - Hilversum (with the Muiderpoort Station), on the east side by Flevopark, on the north side by Zeeburgerdijk and on the south side by the Ringvaart Watergraafsmeer. Indische Buurt is the oldest part of the Zeeburg district and is very ethnically diverse, and a high percentage of the population is of immigrant origin (for Zeeburg this is already high at 55%, but higher in the Indische Buurt) and there are an estimated 100 languages spoken.|https://a0.muscache.com/pictures/10272854/8dcca016_original.jpg|3159|https://www.airbnb.com/users/show/3159|Daniel|9/24/08|Amsterdam, Noord-Holland, The Netherlands|"Upon arriving in Amsterdam, one can imagine asking oneself: Where is the fun nightlife? What are the local hot spots? How can I experience the real life in this city? I  offer you the opportunity to act, eat and sleep like-a-local!  I provide the traveler with the opportunity to connect with the local life in Amsterdam."|N/A|N/A|100%|t|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_small|https://a0.muscache.com/im/users/3159/profile_pic/1259095323/original.jpg?aki_policy=profile_x_medium|Indische Buurt|1|1|['email', 'phone', 'reviews', 'jumio', 'offline_government_id', 'selfie', 'government_id', 'identity_manual']|t|t|Amsterdam, North Holland, Netherlands|Oostelijk Havengebied - Indische Buurt| |52.36575|4.94142|Private room in apartment|Private room|2| |1.5 shared baths|1|2|["Hangers", "Coffee maker", "Paid parking on premises", "Long term stays allowed", "First aid kit", "Bed linens", "Lock on bedroom door", "Private entrance", "Carbon monoxide alarm", "Dedicated workspace", "Host greets you", "Single level home", "Extra pillows and blankets", "Hot water", "Paid parking off premises", "Heating", "Garden or backyard", "Hair dryer", "Essentials", "Smoke alarm", "Washer", "Refrigerator", "Iron", "Shampoo", "Ethernet connection", "Wifi", "Fire extinguisher"]|$59.00 |3|1125|3|3|1125|1125|3|1125| |t|29|46|60|139|2/11/21|278|1|0|3/30/09|2/14/20|98|10|10|1010|9|10| ||t|1|0|1|0|1.92|

### Problems with original data 

One problem with the original data downloaded was that there was a lot of irrelevant data that I did not need for my analysis. This made it hard to work with the data because the large amount of data made it confusing and hard to find only the relevant ones.

In order to clear out only the relevant data, I wrote a python code called munge.py to only filter out the necessary fields.

I used neighborhood_cleansed in lieu of neighborhood_group_cleansed and neighborhood since those fields had a lot of missing data and neighborhood_cleansed seemed to have more accurate data.

I also used host_neighborhood in lieu of city because the city field did not exist and host_neighborhood seemed to be the closest fit.
```
with open('./data/listings.csv', 'r') as f:
    reader = csv.DictReader(f)
    with open('./data/listings_clean.csv','w') as file:
        file.write('id,name,host_name,host_is_superhost,neighbourhood,neighbourhood_cleansed,neighbourhood_group_cleansed,beds,price,review_scores_rating\n')
    with open('./data/listings_clean.csv','a',newline='') as file:
        col = ['id','name','host_name','host_is_superhost','host_neighbourhood','neighbourhood_cleansed','neighbourhood_group_cleansed','beds','price','review_scores_rating']
        writer = csv.DictWriter(file, fieldnames=col)
...
```

### Scrubbed Data

Here are the first few data rows for the munged data. Again, I didn't put 20 rows because there's a lot of data.

|id	|name	|host_name|	host_is_superhost	|neighbourhood	|neighbourhood_cleansed	|neighbourhood_group_cleansed	|beds	|price|	review_scores_rating|
|---|---|---|---|---|---|---|---|---|---|
|2818	|Quiet Garden View Room & Super Fast WiFi	|Daniel	|t	|Indische Buurt	|Oostelijk Havengebied - Indische Buurt	| |	2	|$59.00| 	98|
|---|---|---|---|---|---|---|---|---|---|
|20168|	Studio with private bathroom in the centre 1|	Alexander|	f	|Grachtengordel	|Centrum-Oost| |		1|	$129.00 |	89|
|---|---|---|---|---|---|---|---|---|---|
|25428|	Lovely, spacious 1 bed apt in Center(with lift)	|Joan|	t	|Grachtengordel	|Centrum-West| |		1	|$125.00 |	100|
|---|---|---|---|---|---|---|---|---|---|
|27886	|Romantic, stylish B&B houseboat in canal district	|Flip	|t|	Westelijke Eilanden	|Centrum-West| |		1|	$125.00 |	99|

# Part 2: Data analysis in MongoDB

1. show exactly two documents from the listings collection in any order

find listings, limit 2 results.
```
> db.listings.find().limit(2)
{ "_id" : ObjectId("606b88dd7c6a86bb05935a14"), "id" : 2818, "name" : "Quiet Garden View Room & Super Fast WiFi", "host_name" : "Daniel", "host_is_superhost" : "t", "neighbourhood" : "Indische Buurt", "neighbourhood_cleansed" : "Oostelijk Havengebied - Indische Buurt", "neighbourhood_group_cleansed" : "", "beds" : 2, "price" : "$59.00", "review_scores_rating" : 98 }
{ "_id" : ObjectId("606b88dd7c6a86bb05935a15"), "id" : 20168, "name" : "Studio with private bathroom in the centre 1", "host_name" : "Alexander", "host_is_superhost" : "f", "neighbourhood" : "Grachtengordel", "neighbourhood_cleansed" : "Centrum-Oost", "neighbourhood_group_cleansed" : "", "beds" : 1, "price" : "$129.00", "review_scores_rating" : 89 }
```
2. show exactly 10 documents in any order, but print in easier to read format and noting the host names for further use, using the pretty() function.

Find listings limit 10. Using pretty function.

```
> db.listings.find().limit(10).pretty()
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a14"),
	"id" : 2818,
	"name" : "Quiet Garden View Room & Super Fast WiFi",
	"host_name" : "Daniel",
	"host_is_superhost" : "t",
	"neighbourhood" : "Indische Buurt",
	"neighbourhood_cleansed" : "Oostelijk Havengebied - Indische Buurt",
	"neighbourhood_group_cleansed" : "",
	"beds" : 2,
	"price" : "$59.00",
	"review_scores_rating" : 98
}
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a15"),
	"id" : 20168,
	"name" : "Studio with private bathroom in the centre 1",
	"host_name" : "Alexander",
	"host_is_superhost" : "f",
	"neighbourhood" : "Grachtengordel",
	"neighbourhood_cleansed" : "Centrum-Oost",
	"neighbourhood_group_cleansed" : "",
	"beds" : 1,
	"price" : "$129.00",
	"review_scores_rating" : 89
}
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a16"),
	"id" : 25428,
	"name" : "Lovely, spacious 1 bed apt in Center(with lift)",
	"host_name" : "Joan",
	"host_is_superhost" : "t",
	"neighbourhood" : "Grachtengordel",
	"neighbourhood_cleansed" : "Centrum-West",
	"neighbourhood_group_cleansed" : "",
	"beds" : 1,
	"price" : "$125.00",
	"review_scores_rating" : 100
}
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a17"),
	"id" : 27886,
	"name" : "Romantic, stylish B&B houseboat in canal district",
	"host_name" : "Flip",
	"host_is_superhost" : "t",
	"neighbourhood" : "Westelijke Eilanden",
	"neighbourhood_cleansed" : "Centrum-West",
	"neighbourhood_group_cleansed" : "",
	"beds" : 1,
	"price" : "$125.00",
	"review_scores_rating" : 99
}
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a18"),
	"id" : 28871,
	"name" : "Comfortable double room",
	"host_name" : "Edwin",
	"host_is_superhost" : "t",
	"neighbourhood" : "Amsterdam Centrum",
	"neighbourhood_cleansed" : "Centrum-Oost",
	"neighbourhood_group_cleansed" : "",
	"beds" : 1,
	"price" : "$75.00",
	"review_scores_rating" : 97
}
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a19"),
	"id" : 29051,
	"name" : "Comfortable single room",
	"host_name" : "Edwin",
	"host_is_superhost" : "t",
	"neighbourhood" : "Amsterdam Centrum",
	"neighbourhood_cleansed" : "Centrum-Oost",
	"neighbourhood_group_cleansed" : "",
	"beds" : 1,
	"price" : "$55.00",
	"review_scores_rating" : 95
}
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a1a"),
	"id" : 31080,
	"name" : "2-story apartment + rooftop terrace",
	"host_name" : "Nienke",
	"host_is_superhost" : "f",
	"neighbourhood" : "Hoofddorppleinbuurt",
	"neighbourhood_cleansed" : "Zuid",
	"neighbourhood_group_cleansed" : "",
	"beds" : 3,
	"price" : "$219.00",
	"review_scores_rating" : 95
}
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a1b"),
	"id" : 41125,
	"name" : "Amsterdam Center Entire Apartment",
	"host_name" : "Fatih",
	"host_is_superhost" : "t",
	"neighbourhood" : "Jordaan",
	"neighbourhood_cleansed" : "Centrum-West",
	"neighbourhood_group_cleansed" : "",
	"beds" : 1,
	"price" : "$160.00",
	"review_scores_rating" : 96
}
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a1c"),
	"id" : 43109,
	"name" : "Oasis in the middle of Amsterdam",
	"host_name" : "Aukje",
	"host_is_superhost" : "f",
	"neighbourhood" : "Grachtengordel",
	"neighbourhood_cleansed" : "Centrum-West",
	"neighbourhood_group_cleansed" : "",
	"beds" : 4,
	"price" : "$211.00",
	"review_scores_rating" : 98
}
{
	"_id" : ObjectId("606b88dd7c6a86bb05935a1d"),
	"id" : 44129,
	"name" : "Luxury design with canal view",
	"host_name" : "Tatiana",
	"host_is_superhost" : "f",
	"neighbourhood" : "Jordaan",
	"neighbourhood_cleansed" : "Centrum-West",
	"neighbourhood_group_cleansed" : "",
	"beds" : 1,
	"price" : "$115.00",
	"review_scores_rating" : 98
}
```
3. choose two host_names who are superhosts (available in the host_is_superhost field), and show all of the listings offered by either of the two hosts
    * only show the name, price, neighbourhood, host_name, and host_is_superhost for each result

Find listings based on host name. I added host_is_superhost criteria to avoid showing data for hosts with same names.
```
let host1 = {$and: [{"host_name":"Fatih"},{"host_is_superhost":"t"}]};
let host2 = {$and: [{"host_name":"Edwin"},{"host_is_superhost":"t"}]};
let criteria = {"_id":0, "name":1,"price":1,"neighborhood_cleansed":1,"host_name":1,"host_is_superhost":1};
db.listings.find(host1,criteria);
db.listings.find(host2,criteria);

{ "name" : "Amsterdam Center Entire Apartment", "host_name" : "Fatih", "host_is_superhost" : "t", "price" : "$160.00" }
{ "name" : "Comfortable double room", "host_name" : "Edwin", "host_is_superhost" : "t", "price" : "$75.00" }
{ "name" : "Comfortable single room", "host_name" : "Edwin", "host_is_superhost" : "t", "price" : "$55.00" }
{ "name" : "BedBikeBoat", "host_name" : "Edwin", "host_is_superhost" : "t", "price" : "$250.00" }
```
4. find all the unique host_name values


distinct function finds distinct hosts.

```
db.listings.distinct("host_name")
[
    ...
	"Aad",
	"Aafje",
	"Aafke",
	"Aafke Monique",
	"Aaike",
	"Aalje",
	"Aaron",
	"Aart",
    ...
]
```
5. find all of the places that have more than 2 beds in a neighborhood of your choice (referred to as neighbourhood_group_cleansed in the data file), ordered by review_scores_rating descending
    * only show the name, beds, city, review_scores_rating, and price
    * if you run out of memory for this query, try filtering review_scores_rating that aren't empty ($ne); and lastly, if there's still an issue, you can set the beds to match exactly 2

Let neighborhood be the city. I had enough memory so I didn't add the $ne criteria.

```
let query = {"beds":{$gt:2}, "neighbourhood_cleansed":"Zuid"};
let filtering = {"_id":0,"name":1,"beds":1,"neighborhood":1,"review_scores_rating":1,"price":1};
db.listings.find(query,filtering).sort("review_scores_rating":-1)

{ "name" : "Spacious 170 m2 house with garden", "beds" : 4, "price" : "$275.00", "review_scores_rating" : "" }
{ "name" : "Spacious & bright apartment with roof terrace", "beds" : 4, "price" : "$300.00", "review_scores_rating" : "" }
{ "name" : "Nice family house near Vondelpark.", "beds" : 6, "price" : "$175.00", "review_scores_rating" : "" }
{ "name" : "SPACIOUS, LUXURY LOFT APARTMENT", "beds" : 3, "price" : "$113.00", "review_scores_rating" : "" }
{ "name" : "Family friendly spacious house with lovely cat", "beds" : 7, "price" : "$299.00", "review_scores_rating" : "" }
{ "name" : "Spacious, charming family home", "beds" : 4, "price" : "$270.00", "review_scores_rating" : "" }
{ "name" : "Nice 2floor familyhouse with garden", "beds" : 5, "price" : "$130.00", "review_scores_rating" : "" }
{ "name" : "Watervilla met vrij uitzicht rondom", "beds" : 5, "price" : "$150.00", "review_scores_rating" : "" }
{ "name" : "Huge 3 bedroom apartment | Vondelpark, Museum, RAI", "beds" : 3, "price" : "$200.00", "review_scores_rating" : "" }
{ "name" : "Stylish apartment located in Museum District", "beds" : 3, "price" : "$220.00", "review_scores_rating" : "" }
{ "name" : "Beautiful Family Apartment", "beds" : 5, "price" : "$325.00", "review_scores_rating" : "" }
{ "name" : "Beautiful Family House Amsterdam", "beds" : 4, "price" : "$200.00", "review_scores_rating" : "" }
{ "name" : "Amazing 2 story apartment near Vondelpark", "beds" : 4, "price" : "$350.00", "review_scores_rating" : "" }
{ "name" : "Perfect located new apartment in Amsterdam.", "beds" : 3, "price" : "$140.00", "review_scores_rating" : "" }
{ "name" : "New and romantic house near Vondelpark and center", "beds" : 4, "price" : "$200.00", "review_scores_rating" : "" }
{ "name" : "Beautiful large apartment next to Vondelpark", "beds" : 4, "price" : "$105.00", "review_scores_rating" : "" }
{ "name" : "Superb townhouse in Amsterdam South at Vondelpark", "beds" : 12, "price" : "$450.00", "review_scores_rating" : "" }
{ "name" : "Typical Dutch family house in Amsterdam", "beds" : 4, "price" : "$210.00", "review_scores_rating" : "" }
{ "name" : "Old-South near the Vondelpark and musea!", "beds" : 6, "price" : "$400.00", "review_scores_rating" : "" }
{ "name" : "A family home with a big terrace", "beds" : 3, "price" : "$205.00", "review_scores_rating" : "" }
Type "it" for more
...
```
6. show the number of listings per host
```

$sum to find number of listings per host.

db.listings.aggregate([{$group: {_id: "$host_name",listingCount: {$sum: 1}}}])

{ "_id" : "Aparthotel Adagio Amsterdam City", "listingCount" : 3 }
{ "_id" : "Casta", "listingCount" : 1 }
{ "_id" : "Danila", "listingCount" : 2 }
{ "_id" : "Isaona", "listingCount" : 1 }
{ "_id" : "Sergei", "listingCount" : 1 }
{ "_id" : "Sircle", "listingCount" : 2 }
{ "_id" : "Solomon", "listingCount" : 1 }
{ "_id" : "F E", "listingCount" : 1 }
{ "_id" : "Apartment", "listingCount" : 1 }
{ "_id" : "Gurjot", "listingCount" : 1 }
{ "_id" : "Madee", "listingCount" : 1 }
{ "_id" : "Emo", "listingCount" : 1 }
{ "_id" : "Cocomama", "listingCount" : 7 }
{ "_id" : "Conscious Hotel Vondelpark", "listingCount" : 3 }
{ "_id" : "Evie", "listingCount" : 1 }
{ "_id" : "Kukur", "listingCount" : 1 }
{ "_id" : "Liezl", "listingCount" : 1 }
{ "_id" : "Alaya", "listingCount" : 1 }
{ "_id" : "Flor", "listingCount" : 1 }
{ "_id" : "Niels And Lena", "listingCount" : 2 }
Type "it" for more
```
7. in a particular neighborhood_group_cleansed of your choosing again, find the average review_scores_rating per neighborhood, and only show the ones above a 95, sorted in descending order of rating 

average stores the average rating scores
match 95 finds ratings greater than 95
aggregate combines both variables

```
let average = {$group: {_id: "$neighbourhood_cleansed",average_rating:{$avg:"$review_scores_rating"}}};
let match95 = {$match: {"average_rating":{$gt: 95}}};
db.listings.aggregate([average,match95])

{ "_id" : "De Aker - Nieuw Sloten", "average_rating" : 95.1734693877551 }
{ "_id" : "IJburg - Zeeburgereiland", "average_rating" : 96.06590257879657 }
{ "_id" : "Watergraafsmeer", "average_rating" : 95.18139534883721 }
{ "_id" : "Westerpark", "average_rating" : 95.62418300653594 }
{ "_id" : "De Baarsjes - Oud-West", "average_rating" : 95.6065451840833 }
{ "_id" : "De Pijp - Rivierenbuurt", "average_rating" : 95.25245732022762 }
{ "_id" : "Bos en Lommer", "average_rating" : 95.56906077348066 }
{ "_id" : "Oud-Oost", "average_rating" : 95.66698935140367 }
{ "_id" : "Zuid", "average_rating" : 95.45108695652173 }
{ "_id" : "Noord-West", "average_rating" : 95.60200668896321 }

```

### Extra Credit

Please see below for my code for this section. Note that I left my password out (don't want to share my password)

```
python3 -m venv .venv
source .venv/bin/activate
pip3 install pymongo

import pymongo
connection = pymongo.MongoClient("class-mongodb.cims.nyu.edu", 27017,
                                username="ec3219",
                                password="your_db_password",
                                authSource="ec3219")
collection = connection["ec3219"]["listings"]

# the collection variable will be a reference to your collection
docs = collection.find()

for ele in docs:
    if ele.get("beds") != "":
        if (ele.get("neighbourhood_cleansed") == "Zuid" and float(ele.get("beds"))>float(numBeds)):
            print(str(ele.get("name")) + "," + str(ele.get("beds")) + "," + str(ele.get("neighbourhood_cleansed")) + "," + str(ele.get("review_scores_rating")) + "," + str(ele.get("price")))
```

## Extra-credit

This assignment deserves extra credit because I did part 3 and posted my code in the appropriate section. Note that I left my password out (don't want to share my password). Otherwise everything else works fine.