#MongoDB assignment

## Part 1: Data Selection and Import

### Data Selection

The [dataset](data/listings.csv) chosen for analysis comprises [Airbnb](https://insideairbnb.com/get-the-data/) listings specifically from Quebec City, Quebec, Canada, encompassing data up until December 13, 2023. This dataset is a valuable resource for gaining insights into the dynamics of the Airbnb market within this vibrant Canadian city. It provides a comprehensive overview of various aspects such as property types, rental prices, location preferences, and availability trends.


### Raw Data
First few rows and columns as an example:

| ID | Listing URL | Scrape ID | Last Scraped | Source | Name | Description | Neighborhood Overview | Picture URL | Host ID | Host URL | Host Name | Host Since | Host Location |
|----|-------------|-----------|--------------|--------|------|-------------|-----------------------|-------------|---------|----------|-----------|------------|---------------|
| 138381 | [https://www.airbnb.com/rooms/138381](https://www.airbnb.com/rooms/138381) | 20231213181237 | 2023-12-13 | city scrape | Bed and breakfast in Quebec · ★4.91 · 1 bedroom · 2 beds · 1 private bath | | Situé sur le chemin Saint-Louis, près du site patrimonial de Sillery, le gîte est à distance de marche de l'animée avenue Maguire, de l'université Laval et des centres d'achats. À quelques minutes se trouve aussi la promenade Champlain et une piste cyclable au bord du Saint-Laurent. | ![Mary](https://a0.muscache.com/pictures/e9224551-d416-4495-9d71-69448ea10185.jpg) | 675584 | [Mary's Profile](https://www.airbnb.com/users/show/675584) | Mary | 2011-06-07 | |
| 198548 | [https://www.airbnb.com/rooms/198548](https://www.airbnb.com/rooms/198548) | 20231213181237 | 2023-12-13 | city scrape | Rental unit in Quebec · ★4.76 · 1 bedroom · 2 beds · 1 bath | | Saint-Jean-Baptiste definitely is your best choice :  all major touristic points of interest and all services are walking distance. <br /><br />Université Laval is a 30 min bus ride - 20 min bike ride. | ![Marianne](https://a0.muscache.com/pictures/e46bb202-f284-4cf1-bfcf-cf80f2c25f32.jpg) | 960772 | [Marianne's Profile](https://www.airbnb.com/users/show/960772) | Marianne | 2011-08-12 | Quebec, Canada |
| 214967 | [https://www.airbnb.com/rooms/214967](https://www.airbnb.com/rooms/214967) | 20231213181237 | 2023-12-13 | city scrape | Townhouse in Quebec · ★4.95 · 1 bedroom · 1 bed · 1 shared bath | | La nature, le fleuve et la tranquillité du secteur. C'est la campagne en ville ! | ![Julie](https://a0.muscache.com/pictures/f672f818-a78c-4fc5-a7e2-5638e18dc817.jpg) | 1110010 | [Julie's Profile](https://www.airbnb.com/users/show/1110010) | Julie | 2011-09-04 | Quebec, Canada |
| 517628 | [https://www.airbnb.com/rooms/517628](https://www.airbnb.com/rooms/517628) | 20231213181237 | 2023-12-13 | city scrape | Townhouse in Quebec · ★4.89 · 5 bedrooms · 5 beds · 2.5 baths | | This is our primary residence, and we take great pride in our home and our neighborhood. We have THE BEST neighbors ever, so don't be afraid to say bonjour! From our home you are only a ten minute stroll to Petit Champlain, just across the street from the public pool and the stunning, new nordic spa; Strom. We are also a two minute walk from les escaliers du Cap Blanc (the Cap Blanc stairs), which bring you right up to the Citadel and the Plains of Abraham. | ![Jennifer](https://a0.muscache.com/pictures/f617ef26-8920-4ccb-8d70-30101924eb1a.jpg) | 2216595 | [Jennifer's Profile](https://www.airbnb.com/users/show/2216595) | Jennifer | 2012-04-24 | Quebec, Canada |
| 588889 | [https://www.airbnb.com/rooms/588889](https://www.airbnb.com/rooms/588889) | 20231213181237 | 2023-12-13 | previous scrape | Home in Ville de Québec · ★4.75 · 4 bedrooms · 5 beds · 1.5 baths | | | ![Mariane](https://a0.muscache.com/pictures/0d69bf89-62f2-4c19-8ed5-5605602ded7d.jpg) | 2904660 | [Mariane's Profile](https://www.airbnb.com/users/show/2904660) | Mariane | 2012-07-11 | Quebec, Canada |
| 661569 | [https://www.airbnb.com/rooms/661569](https://www.airbnb.com/rooms/661569) | 20231213181237 | 2023-12-13 | city scrape | Bed and breakfast in Quebec · ★4.98 · 1 bedroom · 1 bed · 1 bath | | In the heart of a beautiful and calm neighbourhood. We are located only a few feet away from a Grocery Store, Pharmacy, and many more amenities. <br />Furthermore, the B&B is located on the axes of all public transport, making it easy to get to the Old City. <br />The Champlain Promenade allows guests to walk along the St-Laurence river. <br />McGuire street is a local hub of restaurants with over 20, located only 15 minutes away by foot. | ![Mary](https://a0.muscache.com/pictures/8e839142-384e-4c1f-8fe5-e7c6a02cf437.jpg) | 675584 | [Mary's Profile](https://www.airbnb.com/users/show/675584) | Mary | 2011-06-07 | |
| 878309 | [https://www.airbnb.com/rooms/878309](https://www.airbnb.com/rooms/878309) | 20231213181237 | 2023-12-13 | city scrape | Rental unit in Quebec · ★4.60 · 2 bedrooms · 2 beds · 1 bath | | Our neighbourhood is also dog friendly, just a few minutes’ walk to several parks that your dog will love. City requirements are that dogs must be held with a leash, and to clean up after them.<br /><br />The neighbourhood is very safe and peaceful, very green, with trees in the street. Everything you need is at walking distance: outdoor swimming pool (public and free and, more important, heated) , parks, drugstores, grocery stores, fresh fruit and vegetables store, library, restaurants, cafes and bistros, parks. | ![Ag












### Data Scrubbing

[Data Scrubbing File](data/scrubbing_data.py)

[Cleaned Data File](data/cleaned_data.csv)

In the process of scrubbing the Airbnb dataset from Quebec City, several columns were identified for removal due to either containing no meaningful values or having no data at all. These included the "calculated_host_listings_count_shared_rooms," "bathrooms," "bedrooms," "calendar_updated," and "neighbourhood_group_cleansed" columns. Additionally, the "description" column was removed since it contained no valuable information for analysis.

To further enhance the dataset, a thorough cleansing procedure was undertaken to ensure consistency and clarity in the data. One crucial step involved standardizing the representation of boolean values present in certain cells, denoted as "t" or "f." To make this data more interpretable and user-friendly, all occurrences of "t" were replaced with "YES," signifying a positive affirmation, while "f" was substituted with "NO," indicating a negative response.



## Part 2: Data analysis in MongoDB
### 1. show exactly two documents from the listings collection in any order
```
db.listings.find().limit(2)
```
```
[    _id: ObjectId('660e4b11b6515eb2057e1308'),
    id: 138381,
    listing_url: 'https://www.airbnb.com/rooms/138381',
    scrape_id: Long('20231213181237'),
    last_scraped: '2023-12-13',
    source: 'city scrape',
    name: 'Bed and breakfast in Quebec · ★4.91 · 1 bedroom · 2 beds · 1 private bath',
    neighborhood_overview: "Situé sur le chemin Saint-Louis, près du site patrimonial de Sillery, le gîte est à distance de marche de l'animée avenue Maguire, de l'université Laval et des centres d'achats. À quelques minutes se trouve aussi la promenade Champlain et une piste cyclable au bord du Saint-Laurent.",
    picture_url: 'https://a0.muscache.com/pictures/e9224551-d416-4495-9d71-69448ea10185.jpg',
    host_id: 675584,
    host_url: 'https://www.airbnb.com/users/show/675584',
    host_name: 'Mary',
    host_since: '2011-06-07',
    host_location: '',
    host_about: 'Owner of a Small B&B in Quebec city. I try to make it feel like a home away from home. Every morning I pick up fresh pasteries for our local baker, Olivier. I love when the Bed and Breakfast is full of life and different people get to meet. I look forward to meeting you, if you come to my little place in Quebec city!',
    host_response_time: 'within a day',
    host_response_rate: '100%',
    host_acceptance_rate: '100%',
    host_is_superhost: 'YES',
    host_thumbnail_url: 'https://a0.muscache.com/im/pictures/user/5371a91d-eb88-44db-9850-74f8d9150a98.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/pictures/user/5371a91d-eb88-44db-9850-74f8d9150a98.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: '',
    host_listings_count: 3,
    host_total_listings_count: 6,
    host_verifications: "['phone']",
    host_has_profile_pic: 'YES',
    host_identity_verified: 'YES',
    neighbourhood: 'Quebec, Canada',
    neighbourhood_cleansed: 'Sillery',
    latitude: 46.76851,
    longitude: -71.26804,
    property_type: 'Private room in bed and breakfast',
    room_type: 'Private room',
    accommodates: 3,
    bathrooms_text: '1 private bath',
    beds: 2,
    amenities: '[]',
    price: '$185.00',
    minimum_nights: 31,
    maximum_nights: 365,
    minimum_minimum_nights: 31,
    maximum_minimum_nights: 31,
    minimum_maximum_nights: 365,
    maximum_maximum_nights: 365,
    minimum_nights_avg_ntm: 31,
    maximum_nights_avg_ntm: 365,
    has_availability: 'YES',
    availability_30: 6,
    availability_60: 6,
    availability_90: 6,
    availability_365: 222,
    calendar_last_scraped: '2023-12-13',
    number_of_reviews: 176,
    number_of_reviews_ltm: 3,
    number_of_reviews_l30d: 0,
    first_review: '2011-06-13',
    last_review: '2023-08-21',
    review_scores_rating: 4.91,
    review_scores_accuracy: 4.94,
    review_scores_cleanliness: 4.95,
    review_scores_checkin: 4.94,
    review_scores_communication: 4.96,
    review_scores_location: 4.82,
    review_scores_value: 4.92,
    license: '',
    instant_bookable: 'NO',
    calculated_host_listings_count: 3,
    calculated_host_listings_count_entire_homes: 0,
    calculated_host_listings_count_private_rooms: 2,
    reviews_per_month: 1.16
  },




  {
    _id: ObjectId('660e4b11b6515eb2057e1309'),
    id: 198548,
    listing_url: 'https://www.airbnb.com/rooms/198548',
    scrape_id: Long('20231213181237'),
    last_scraped: '2023-12-13',
    source: 'city scrape',
    name: 'Rental unit in Quebec · ★4.76 · 1 bedroom · 2 beds · 1 bath',
    neighborhood_overview: 'Saint-Jean-Baptiste definitely is your best choice :  all major touristic points of interest and all services are walking distance. <br /><br />Université Laval is a 30 min bus ride - 20 min bike ride.',
    picture_url: 'https://a0.muscache.com/pictures/e46bb202-f284-4cf1-bfcf-cf80f2c25f32.jpg',
    host_id: 960772,
    host_url: 'https://www.airbnb.com/users/show/960772',
    host_name: 'Marianne',
    host_since: '2011-08-12',
    host_location: 'Quebec, Canada',
    host_about: 'Polyglotte globetrotter, swing dancer, curieuse avertie, toujours prête!\n' +
      '\n' +
      'I love to travel, both for work and leisure. \n' +
      'Visiting friends wherever they might be on this planet or welcoming them at my place is always a pleasure.\n' +
      '\n' +
      'I have rented my fully furnished condo in beautiful Quebec city to monthly tenants while I was living abroad. Now back home, I rent on a monthly basis the condo I own just above!',
    host_response_time: 'within a few hours',
    host_response_rate: '100%',
    host_acceptance_rate: '88%',
    host_is_superhost: 'YES',
    host_thumbnail_url: 'https://a0.muscache.com/im/pictures/user/690d1ba0-2f4b-4103-abcb-870571243864.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/pictures/user/690d1ba0-2f4b-4103-abcb-870571243864.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: '',
    host_listings_count: 1,
    host_total_listings_count: 1,
    host_verifications: "['email', 'phone', 'work_email']",
    host_has_profile_pic: 'YES',
    host_identity_verified: 'YES',
    neighbourhood: 'Quebec, Canada',
    neighbourhood_cleansed: 'Saint-Roch',
    latitude: 46.81169,
    longitude: -71.22522,
    property_type: 'Entire rental unit',
    room_type: 'Entire home/apt',
    accommodates: 4,
    bathrooms_text: '1 bath',
    beds: 2,
    amenities: '[]',
    price: '$164.00',
    minimum_nights: 31,
    maximum_nights: 1125,
    minimum_minimum_nights: 31,
    maximum_minimum_nights: 31,
    minimum_maximum_nights: 1125,
    maximum_maximum_nights: 1125,
    minimum_nights_avg_ntm: 31,
    maximum_nights_avg_ntm: 1125,
    has_availability: 'YES',
    availability_30: 4,
    availability_60: 4,
    availability_90: 20,
    availability_365: 170,
    calendar_last_scraped: '2023-12-13',
    number_of_reviews: 58,
    number_of_reviews_ltm: 5,
    number_of_reviews_l30d: 1,
    first_review: '2011-10-03',
    last_review: '2023-11-27',
    review_scores_rating: 4.76,
    review_scores_accuracy: 4.88,
    review_scores_cleanliness: 4.63,
    review_scores_checkin: 4.93,
    review_scores_communication: 4.96,
    review_scores_location: 4.93,
    review_scores_value: 4.75,
    license: '',
    instant_bookable: 'NO',
    calculated_host_listings_count: 1,
    calculated_host_listings_count_entire_homes: 1,
    calculated_host_listings_count_private_rooms: 0,
    reviews_per_month: 0.39
  }
]

```





### 2. Show exactly 10 documents in any order, but "prettyprint" in easier to read format, using the pretty() function.
(Listed 3 of them below for easier read)
```
db.listings.find().limit(10).pretty()
```

```
  {
    _id: ObjectId('660e4b11b6515eb2057e1308'),
    id: 138381,
    listing_url: 'https://www.airbnb.com/rooms/138381',
    scrape_id: Long('20231213181237'),
    last_scraped: '2023-12-13',
    source: 'city scrape',
    name: 'Bed and breakfast in Quebec · ★4.91 · 1 bedroom · 2 beds · 1 private bath',
    neighborhood_overview: "Situé sur le chemin Saint-Louis, près du site patrimonial de Sillery, le gîte est à distance de marche de l'animée avenue Maguire, de l'université Laval et des centres d'achats. À quelques minutes se trouve aussi la promenade Champlain et une piste cyclable au bord du Saint-Laurent.",
    picture_url: 'https://a0.muscache.com/pictures/e9224551-d416-4495-9d71-69448ea10185.jpg',
    host_id: 675584,
    host_url: 'https://www.airbnb.com/users/show/675584',
    host_name: 'Mary',
    host_since: '2011-06-07',
    host_location: '',
    host_about: 'Owner of a Small B&B in Quebec city. I try to make it feel like a home away from home. Every morning I pick up fresh pasteries for our local baker, Olivier. I love when the Bed and Breakfast is full of life and different people get to meet. I look forward to meeting you, if you come to my little place in Quebec city!',
    host_response_time: 'within a day',
    host_response_rate: '100%',
    host_acceptance_rate: '100%',
    host_is_superhost: 'YES',
    host_thumbnail_url: 'https://a0.muscache.com/im/pictures/user/5371a91d-eb88-44db-9850-74f8d9150a98.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/pictures/user/5371a91d-eb88-44db-9850-74f8d9150a98.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: '',
    host_listings_count: 3,
    host_total_listings_count: 6,
    host_verifications: "['phone']",
    host_has_profile_pic: 'YES',
    host_identity_verified: 'YES',
    neighbourhood: 'Quebec, Canada',
    neighbourhood_cleansed: 'Sillery',
    latitude: 46.76851,
    longitude: -71.26804,
    property_type: 'Private room in bed and breakfast',
    room_type: 'Private room',
    accommodates: 3,
    bathrooms_text: '1 private bath',
    beds: 2,
    amenities: '[]',
    price: '$185.00',
    minimum_nights: 31,
    maximum_nights: 365,
    minimum_minimum_nights: 31,
    maximum_minimum_nights: 31,
    minimum_maximum_nights: 365,
    maximum_maximum_nights: 365,
    minimum_nights_avg_ntm: 31,
    maximum_nights_avg_ntm: 365,
    has_availability: 'YES',
    availability_30: 6,
    availability_60: 6,
    availability_90: 6,
    availability_365: 222,
    calendar_last_scraped: '2023-12-13',
    number_of_reviews: 176,
    number_of_reviews_ltm: 3,
    number_of_reviews_l30d: 0,
    first_review: '2011-06-13',
    last_review: '2023-08-21',
    review_scores_rating: 4.91,
    review_scores_accuracy: 4.94,
    review_scores_cleanliness: 4.95,
    review_scores_checkin: 4.94,
    review_scores_communication: 4.96,
    review_scores_location: 4.82,
    review_scores_value: 4.92,
    license: '',
    instant_bookable: 'NO',
    calculated_host_listings_count: 3,
    calculated_host_listings_count_entire_homes: 0,
    calculated_host_listings_count_private_rooms: 2,
    reviews_per_month: 1.16
  },




  {
    _id: ObjectId('660e4b11b6515eb2057e1309'),
    id: 198548,
    listing_url: 'https://www.airbnb.com/rooms/198548',
    scrape_id: Long('20231213181237'),
    last_scraped: '2023-12-13',
    source: 'city scrape',
    name: 'Rental unit in Quebec · ★4.76 · 1 bedroom · 2 beds · 1 bath',
    neighborhood_overview: 'Saint-Jean-Baptiste definitely is your best choice :  all major touristic points of interest and all services are walking distance. <br /><br />Université Laval is a 30 min bus ride - 20 min bike ride.',
    picture_url: 'https://a0.muscache.com/pictures/e46bb202-f284-4cf1-bfcf-cf80f2c25f32.jpg',
    host_id: 960772,
    host_url: 'https://www.airbnb.com/users/show/960772',
    host_name: 'Marianne',
    host_since: '2011-08-12',
    host_location: 'Quebec, Canada',
    host_about: 'Polyglotte globetrotter, swing dancer, curieuse avertie, toujours prête!\n' +
      '\n' +
      'I love to travel, both for work and leisure. \n' +
      'Visiting friends wherever they might be on this planet or welcoming them at my place is always a pleasure.\n' +
      '\n' +
      'I have rented my fully furnished condo in beautiful Quebec city to monthly tenants while I was living abroad. Now back home, I rent on a monthly basis the condo I own just above!',
    host_response_time: 'within a few hours',
    host_response_rate: '100%',
    host_acceptance_rate: '88%',
    host_is_superhost: 'YES',
    host_thumbnail_url: 'https://a0.muscache.com/im/pictures/user/690d1ba0-2f4b-4103-abcb-870571243864.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/pictures/user/690d1ba0-2f4b-4103-abcb-870571243864.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: '',
    host_listings_count: 1,
    host_total_listings_count: 1,
    host_verifications: "['email', 'phone', 'work_email']",
    host_has_profile_pic: 'YES',
    host_identity_verified: 'YES',
    neighbourhood: 'Quebec, Canada',
    neighbourhood_cleansed: 'Saint-Roch',
    latitude: 46.81169,
    longitude: -71.22522,
    property_type: 'Entire rental unit',
    room_type: 'Entire home/apt',
    accommodates: 4,
    bathrooms_text: '1 bath',
    beds: 2,
    amenities: '[]',
    price: '$164.00',
    minimum_nights: 31,
    maximum_nights: 1125,
    minimum_minimum_nights: 31,
    maximum_minimum_nights: 31,
    minimum_maximum_nights: 1125,
    maximum_maximum_nights: 1125,
    minimum_nights_avg_ntm: 31,
    maximum_nights_avg_ntm: 1125,
    has_availability: 'YES',
    availability_30: 4,
    availability_60: 4,
    availability_90: 20,
    availability_365: 170,
    calendar_last_scraped: '2023-12-13',
    number_of_reviews: 58,
    number_of_reviews_ltm: 5,
    number_of_reviews_l30d: 1,
    first_review: '2011-10-03',
    last_review: '2023-11-27',
    review_scores_rating: 4.76,
    review_scores_accuracy: 4.88,
    review_scores_cleanliness: 4.63,
    review_scores_checkin: 4.93,
    review_scores_communication: 4.96,
    review_scores_location: 4.93,
    review_scores_value: 4.75,
    license: '',
    instant_bookable: 'NO',
    calculated_host_listings_count: 1,
    calculated_host_listings_count_entire_homes: 1,
    calculated_host_listings_count_private_rooms: 0,
    reviews_per_month: 0.39
  },




  {
    _id: ObjectId('660e4b11b6515eb2057e130a'),
    id: 214967,
    listing_url: 'https://www.airbnb.com/rooms/214967',
    scrape_id: Long('20231213181237'),
    last_scraped: '2023-12-13',
    source: 'city scrape',
    name: 'Townhouse in Quebec · ★4.95 · 1 bedroom · 1 bed · 1 shared bath',
    neighborhood_overview: "La nature, le fleuve et la tranquillité du secteur. C'est la campagne en ville !",
    picture_url: 'https://a0.muscache.com/pictures/f672f818-a78c-4fc5-a7e2-5638e18dc817.jpg',
    host_id: 1110010,
    host_url: 'https://www.airbnb.com/users/show/1110010',
    host_name: 'Julie',
    host_since: '2011-09-04',
    host_location: 'Quebec, Canada',
    host_about: "Sur Airbnb depuis 12 ans avec le même plaisir renouvelé d’accueillir des voyageurs qui veulent vivre un séjour inoubliable ! Travelling myself a lot, I like to host guests sharing the same passion ! Grande voyageuse moi-même, j'aime accueillir chez moi des gens qui partagent cette passion de la découverte !",
    host_response_time: 'within an hour',
    host_response_rate: '100%',
    host_acceptance_rate: '95%',
    host_is_superhost: 'YES',
    host_thumbnail_url: 'https://a0.muscache.com/im/pictures/user/d8660426-75a5-4122-93a2-3fc07c98f37a.jpg?aki_policy=profile_small',
    host_picture_url: 'https://a0.muscache.com/im/pictures/user/d8660426-75a5-4122-93a2-3fc07c98f37a.jpg?aki_policy=profile_x_medium',
    host_neighbourhood: '',
    host_listings_count: 2,
    host_total_listings_count: 2,
    host_verifications: "['email', 'phone']",
    host_has_profile_pic: 'YES',
    host_identity_verified: 'YES',
    neighbourhood: 'Quebec, Canada',
    neighbourhood_cleansed: 'Vieux-Québec/Cap-Blanc/Colline parlementaire',
    latitude: 46.80233,
    longitude: -71.21214,
    property_type: 'Private room in townhouse',
    room_type: 'Private room',
    accommodates: 2,
    bathrooms_text: '1 shared bath',
    beds: 1,
    amenities: '[]',
    price: '$61.00',
    minimum_nights: 32,
    maximum_nights: 1125,
    minimum_minimum_nights: 32,
    maximum_minimum_nights: 32,
    minimum_maximum_nights: 1125,
    maximum_maximum_nights: 1125,
    minimum_nights_avg_ntm: 32,
    maximum_nights_avg_ntm: 1125,
    has_availability: 'YES',
    availability_30: 11,
    availability_60: 12,
    availability_90: 25,
    availability_365: 223,
    calendar_last_scraped: '2023-12-13',
    number_of_reviews: 198,
    number_of_reviews_ltm: 7,
    number_of_reviews_l30d: 0,
    first_review: '2012-08-20',
    last_review: '2023-09-30',
    review_scores_rating: 4.95,
    review_scores_accuracy: 4.95,
    review_scores_cleanliness: 4.99,
    review_scores_checkin: 4.98,
    review_scores_communication: 4.97,
    review_scores_location: 4.89,
    review_scores_value: 4.87,
    license: '',
    instant_bookable: 'NO',
    calculated_host_listings_count: 1,
    calculated_host_listings_count_entire_homes: 0,
    calculated_host_listings_count_private_rooms: 1,
    reviews_per_month: 1.44
  }
```



### 3. choose two hosts (by reffering to their host_id values) who are superhosts (available in the host_is_superhost field), and show all of the listings offered by both of the two hosts
```
db.listings.find(
  {
    host_is_superhost: "YES",
    host_id: { $in: [1110010, 2216595] }
  },
  {
    _id: 0,
    name: 1,
    price: 1,
    neighbourhood: 1,
    host_name: 1,
    host_is_superhost: 1
  }
)
```
```
[
  {
    name: 'Townhouse in Quebec · ★4.95 · 1 bedroom · 1 bed · 1 shared bath',
    host_name: 'Julie',
    host_is_superhost: 'YES',
    neighbourhood: 'Quebec, Canada',
    price: '$61.00'
  },
  {
    name: 'Townhouse in Quebec · ★4.89 · 5 bedrooms · 5 beds · 2.5 baths',
    host_name: 'Jennifer',
    host_is_superhost: 'YES',
    neighbourhood: 'Quebec, Canada',
    price: '$504.00'
  }
]
```







### 4. find all the unique host_name values 
```
db.listings.distinct("host_name")
```
```
['77 St-Vallier',
  'Abner',
  'Adam',
  'Adele',
  'Adolphe',
  'Adriana',
  'Aesthesia',
  'Agnes',
  'AlChalet',
  'Alain',
  'Albert',
  'Alek',
  'Alex',
  'Alex Et Sophia',
  'Alexander',
  'Alexandra',
  'Alexandre',
  'Alexe',
  'Alexi Et Caroline',
  'Alexis',
  'Alfred',
  'Alice',
  'Allison',
  'Alys',
  'Alyson',
  'Amanda',
  'Amandine',
  'Amelie',
  'Amine',
  'Amélie',
  'Ana Maria',
  'Andre',
  'Andrew',
  'André',
  'Angéline',
  'Anicet',
  'Anna',
  'Annabelle',
  'Anne',
  'Anne-Gael',
  'Anne-Isabelle',
  'Anne-Marie Et Julien',
  'Anne-Sophie',
  'Annick',
  'Annie',
  'Anny & Eric',
  'Anthonie',
  'Anthony',
  'Anthony & Angélique',
  'Antoine',
  'Antoine ET Stéphane',
  'Antoinette',
  'Antonin',
  'Antonio',
  'Arturo',
  'Aude',
  'Audree',
  'Audrey',
  'Aurélie',
  'Axel',
  'Azelie',
  'Aziel',
  'Azure',
  'Bacall',
  'Barricade',
  'Bastien',
  'Beatrix',
  'Ben',
  'Benoit',
  'Benoit F.',
  'Bernadette',
  'Bernard',
  'Berri',
  'Bertrand',
  'Blaise',
  'Brice',
  'Brigitte',
  'Brigitte / Ghislain',
  'Bruno',
  'Bryde Elizabeth',
  'Buade',
  'Béatrice',
  'Camille',
  'Camilo',
  'Camping',
  'Carl',
  'Carol',
  'Carole-Ann',
  'Caroline',
  'Caroline Et Jean-Raphael',
  'Cassiopée',
  'Catherine',
  'Cathy',
  'Caïman',
  'Chalets',
  'Chalets Et Cie',
  'Chantal',
  'Chantale & Alain',
  'Chantale Et Robert',
  'Charles',
  ... 534 more items]

```




### 5. Find all of the places that have more than 2 beds in a neighborhood of your choice (referred to as either the neighborhood or neighbourhood_group_cleansed fields in the data file), ordered by review_scores_rating descending.

```
db.listings.find(
  {
    beds: { $gt: 2 },
    neighbourhood_cleansed: "Saint-Jean-Baptiste"
  },
  {
    _id: 0,
    name: 1,
    beds: 1,
    review_scores_rating: 1,
    price: 1
  }
).sort({ review_scores_rating: -1 })

```

```
  [{name: 'Rental unit in Québec · 5 bedrooms · 6 beds · 2 baths',
    beds: 6,
    price: '$120.00',
    review_scores_rating: ''
  },
  {
    name: 'Condo in Québec · 3 bedrooms · 3 beds · 1 bath',
    beds: 3,
    price: '$100.00',
    review_scores_rating: ''
  },
  {
    name: 'Rental unit in Québec · 4 bedrooms · 5 beds · 2 baths',
    beds: 5,
    price: '$305.00',
    review_scores_rating: ''
  },
  {
    name: 'Home in Québec · ★New · 2 bedrooms · 3 beds · 2 baths',
    beds: 3,
    price: '$445.00',
    review_scores_rating: ''
  },
  {
    name: 'Rental unit in Québec · ★New · 4 bedrooms · 5 beds · 2 baths',
    beds: 5,
    price: '$291.00',
    review_scores_rating: ''
  },
  {
    name: 'Cottage in Québec · ★New · 2 bedrooms · 4 beds · 1.5 baths',
    beds: 4,
    price: '$500.00',
    review_scores_rating: ''
  },
  {
    name: 'Rental unit in Québec · ★5.0 · 2 bedrooms · 3 beds · 1 bath',
    beds: 3,
    price: '$130.00',
    review_scores_rating: 5
  },
  {
    name: 'Home in Québec · ★5.0 · 4 bedrooms · 4 beds · 1.5 baths',
    beds: 4,
    price: '$688.00',
    review_scores_rating: 5
  },
  {
    name: 'Townhouse in Québec · ★5.0 · 2 bedrooms · 4 beds · 1.5 baths',
    beds: 4,
    price: '$429.00',
    review_scores_rating: 5
  },
  {
    name: 'Rental unit in Québec · ★5.0 · 2 bedrooms · 4 beds · 1 bath',
    beds: 4,
    price: '$60.00',
    review_scores_rating: 5
  },
  {
    name: 'Townhouse in Québec · ★5.0 · 2 bedrooms · 3 beds · 1.5 baths',
    beds: 3,
    price: '$140.00',
    review_scores_rating: 5
  },
  {
    name: 'Rental unit in Québec · ★5.0 · 2 bedrooms · 3 beds · 1 bath',
    beds: 3,
    price: '$69.00',
    review_scores_rating: 5
  },
  {
    name: 'Rental unit in Québec · 2 bedrooms · 3 beds · 1 bath',
    beds: 3,
    price: '$150.00',
    review_scores_rating: 5
  },
  {
    name: 'Rental unit in Québec · ★5.0 · 2 bedrooms · 3 beds · 1 bath',
    beds: 3,
    price: '$193.00',
    review_scores_rating: 5
  },
  {
    name: 'Rental unit in Québec · ★5.0 · 2 bedrooms · 3 beds · 2 baths',
    beds: 3,
    price: '$458.00',
    review_scores_rating: 5
  },
  {
    name: 'Rental unit in Québec · ★4.96 · 2 bedrooms · 3 beds · 1 bath',
    beds: 3,
    price: '$159.00',
    review_scores_rating: 4.96
  },
  {
    name: 'Townhouse in Québec · ★4.96 · 2 bedrooms · 5 beds · 1.5 baths',
    beds: 5,
    price: '$298.00',
    review_scores_rating: 4.96
  },
  {
    name: 'Rental unit in Ville de Québec · ★4.92 · 2 bedrooms · 4 beds · 1 bath',
    beds: 4,
    price: '$190.00',
    review_scores_rating: 4.92
  },
  {
    name: 'Rental unit in Québec City · ★4.91 · 2 bedrooms · 4 beds · 1 bath',
    beds: 4,
    price: '$134.00',
    review_scores_rating: 4.91
  },
  {
    name: 'Rental unit in Québec · ★4.90 · 3 bedrooms · 3 beds · 1 bath',
    beds: 3,
    price: '$134.00',
    review_scores_rating: 4.9
  }
]
```



### 6. Show the number of listings per host
```
db.listings.aggregate([
  { $group: { _id: "$host_id", listingsCount: { $sum: 1 } } }
])
```
```
[
  { _id: 547679923, listingsCount: 1 },
  { _id: 268467584, listingsCount: 2 },
  { _id: 30546462, listingsCount: 1 },
  { _id: 547263941, listingsCount: 1 },
  { _id: 78914482, listingsCount: 4 },
  { _id: 59232131, listingsCount: 1 },
  { _id: 486999897, listingsCount: 1 },
  { _id: 321339788, listingsCount: 1 },
  { _id: 6251077, listingsCount: 1 },
  { _id: 488378198, listingsCount: 1 },
  { _id: 448441979, listingsCount: 1 },
  { _id: 544397488, listingsCount: 1 },
  { _id: 544312053, listingsCount: 1 },
  { _id: 500125, listingsCount: 1 },
  { _id: 232981615, listingsCount: 1 },
  { _id: 544114079, listingsCount: 1 },
  { _id: 392438892, listingsCount: 1 },
  { _id: 16878679, listingsCount: 2 },
  { _id: 543164512, listingsCount: 1 },
  { _id: 39928826, listingsCount: 1 }
]
```



### 7. Find the average review_scores_rating per neighborhood, and only show those that are 4 or above, sorted in descending order of rating (see the docs).

```
db.listings.aggregate([
  { $group: { _id: "$neighbourhood_cleansed", averageRating: { $avg: "$review_scores_rating" } } },
  { $match: { averageRating: { $gte: 4 } } },
  { $sort: { averageRating: -1 } }
])
```

```
[
  { _id: 'Plateau', averageRating: 4.98 },
  { _id: 'Cap-Rouge', averageRating: 4.967777777777778 },
  { _id: 'Quartier 5-2', averageRating: 4.89375 },
  { _id: 'Quartier 4-2', averageRating: 4.88875 },
  { _id: 'Lac-Saint-Charles', averageRating: 4.886666666666667 },
  { _id: 'Saint-Sacrement', averageRating: 4.867083333333333 },
  { _id: 'Loretteville', averageRating: 4.865 },
  { _id: 'Chutes-Montmorency', averageRating: 4.8629411764705885 },
  { _id: 'Pointe-de-Sainte-Foy', averageRating: 4.859999999999999 },
  { _id: 'Notre-Dame-des-Laurentides', averageRating: 4.858125 },
  { _id: 'Sillery', averageRating: 4.851136363636364 },
  { _id: 'Lairet', averageRating: 4.840243902439024 },
  { _id: 'Quartier 4-5', averageRating: 4.838181818181818 },
  {
    _id: 'Neufchâtel-Est/Lebourgneuf',
    averageRating: 4.837777777777778
  },
  { _id: 'Quartier 4-3', averageRating: 4.8325000000000005 },
  { _id: 'Val-Bélair', averageRating: 4.826153846153846 },
  { _id: 'Montcalm', averageRating: 4.818181818181818 },
  { _id: 'Quartier 4-6', averageRating: 4.805555555555555 },
  { _id: 'Saint-Sauveur', averageRating: 4.774034090909091 },
  {
    _id: 'Vieux-Québec/Cap-Blanc/Colline parlementaire',
    averageRating: 4.764656084656084
  }
]
```