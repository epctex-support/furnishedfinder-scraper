# Actor - Furnished Finder Scraper

## Furnished Finder scraper

Since Furnished Finder doesn't provide a good and free API, this actor should help you to retrieve data from it.

The Furnished Finder data scraper supports the following features:

-		Get Property Information - Retrieve comprehensive details about any property listed on Furnished Finder, including its location, size, amenities, and more.

-		Search with Custom Filters - Easily find properties by applying specific filters such as location, price range, accommodation type, and more, ensuring precise search results.

-		Property Images and Details - Access a gallery of high-quality images for each property, along with detailed descriptions, helping users visualize their potential accommodations.

-		Accommodation Details - Obtain in-depth information about each property's accommodations, such as the number of bedrooms, bathrooms, and any special features like a pool or gym.

-		Fee Information - Retrieve data on all associated fees related to a property, including rent, utilities, security deposits, and any additional charges.

-		Property Features - View a comprehensive list of property features, from basic amenities like Wi-Fi and parking to more specific offerings like pet-friendly environments or furnished options.

-		Reviews and Ratings - Access all available reviews and ratings for any property, helping users make informed decisions based on the experiences of previous tenants.

## Bugs, fixes, updates and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/furnishedfinder-scraper/issues).


## Input Parameters

The input of this scraper should be JSON containing the list of pages on Furnished Finder that should be visited. Required fields are:

- `startUrls`: (Optional) (Array) List of Furnished Finder URLs. You should only provide list, search or detail URLs.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `extendOutputFunction`: (Optional) (String) Function that takes a JQuery handle ($) as argument and returns object with data.

- `customMapFunction`: (Optional) (String) Function that takes each objects handle as argument and returns object with executing the function.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Compute Unit Consumption

The actor optimized to run blazing fast and scrape as many items as possible. Therefore, it forefronts all the detail requests. If actor doesn't block very often it'll scrape 100 listings in 1 minute with ~0.03-0.05 compute units.

### Furnished Finder Scraper Input example

```json
{
  "startUrls":[
    "https://www.furnishedfinder.com/housing/Atlanta/Texas/Budget3200/MoveIndate20231213/Avail",
		"https://www.furnishedfinder.com/housing/San-Diego/California",
		"https://www.furnishedfinder.com/property/299655_1"
  ],
  "proxy":{
    "useApifyProxy":false
  },
  "endPage": 5,
  "maxItems": 100
}
```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with failure state and output an explanation of what is wrong.

## Furnished Finder Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any languague (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Furnished Finder actor.

## Scraped Furnished Finder Properties

The structure of each item in Furnished Finder looks like this:

### Item Detail

```json
{
	"url": "https://www.furnishedfinder.com/property/299655_1",
	"id": "299655_1",
	"name": "Billiard House 1 Bed, Private",
	"isFurnished": true,
	"isOwnerVerified": false,
	"propertyDescription": "Newly remodeled spacious 1 Bed - 1 bath. Fully furnished, secluded and private. All interiors are modernized and brand new. Cook and wash your dishes while watching on a large TV. Includes wireless high-speed internet. Private deck in back of the bedroom with a view of a large land lot of canary palms. It feels like you are in the jungle and the country with privacy and space around you, but you have the convenience of freeways and groceries less than a mile away. Located in a \"country feel\" neighborhood\", but 3/4 miles from freeway 78. This is a converted garage into a Jr ADU. It feels like a cozy house with 700 square feet. One bedroom 10x17 includes a King bed and large TV. The billiard room 22x22 includes a billiard table and or ping pong table, an oversize chair, and one queen sofa couch and table with 4 stools. Enjoy the great room with a billiard table and or ping pong. Private patio off the bedroom with lounge couch and table & chairs and a great view of large land space. It has a microwave and an air fryer/oven. There is no regular stove or dishwasher.The bathroom has a tiled stone shower only with a toilet and sink and a linen storage closet. Top-quality linens, towels, tableware, and luxury housewares. Comfortable ambiance, relaxed lighting, great artwork. You will feel very relaxed and cozy in this atmosphere. Dessert landscaping as water restrictions in San Diego. Located in a quiet pocket neighborhood surrounded by growing nurseries and large land lots. Located in north county San Diego. Off & close to Freeway 78, between 5 and 15 freeways. Thirty miles N of SD, 44 min from Sea World 39.3 miles to San Diego Zoo, 17.5 miles to Wild Animal Park, 11 miles to beaches, 8 miles to Legoland. 24 miles to Del Mar Race Track. CA State University San Marcos 5.5 miles, and 6 miles to Palomar College.QUIET TENANTS ONLYThe Billiard room is typically rented with the large house. Because the Billiard Room is so close to the large house, the noise level must be low so as to not disturb guests in the large house.The garage door must remain closed at all times during the guest's stay in the large house.You can open a couple of feet at the bottom to allow additional airflow if needed. This building gets great airflow when all windows and french doors are open. Please do not wander in their area. Do not park in their designated spaces in the driveway or on the right side of the driveway. Please do not give any reason that the guests complain about you.ELECTRIC USE ISSUELimited electricity is a disadvantage in this building. YOu have a limited number of AMPS you can use at one time. You will trip the breaker if you overload, and the breaker will have to be reset when this happens. . An electric hot water heater heats the water and travels from the large house. It takes 6 minutes to heat hot water. The pressure for hot water is on the low side. You can only use one high-energy device at a time. For Example, You cannot have the fireplace and shower on simultaneously. You cannot use the microwave and the air fry oven simultaneously. You may not use two high-energy devices at the same time. If you do, you will trip the breaker. You need to agree that you are aware of the issue.Billiard TablePlease refrain from putting anything on the billiard table except the billiard supplies. Drinks spilled or rings will require new felt. Be careful about scratching the billiard table when you put the ping pong table on the billiard table.",
	"hotelOverview": {
		"Laundry": "In Complex W/D",
		"Utilities Included?": "Yes!",
		"Bathrooms": "1 Bathroom",
		"Bedrooms": "1 Bedroom",
		"Minimum Term": "30 Day Min Stay",
		"Type": "House",
		"Unit": "Billiard - 1 Bed/Bath"
	},
	"pricePanel": {
		"price": "$2,600/Month",
		"remarks": []
	},
	"feesPanel": [
		{
			"type": "Property Fees",
			"fees": [
				{
					"name": "Deposit (Refundable)",
					"amount": "$2600.00"
				},
				{
					"name": "Cleaning Fee",
					"amount": "$175.00"
				},
				{
					"name": "Electric usage only",
					"amount": "$50.00"
				}
			]
		}
	],
	"hospitals": [
		{
			"name": "Tri-City Medical Center",
			"distance": "2.94 miles away"
		},
		{
			"name": "Oceanside Clinic",
			"distance": "4.01 miles away"
		},
		{
			"name": "San Marcos Vet Center",
			"distance": "6.26 miles away"
		},
		{
			"name": "Naval Hospital Camp Pendleton",
			"distance": "8.59 miles away"
		},
		{
			"name": "Camp Pendleton Wounded Warrior Tc",
			"distance": "9.31 miles away"
		}
	],
	"propertyOverview": [
		{
			"label": "Property #",
			"value": "299655"
		},
		{
			"label": "Location",
			"value": "Vista California 92081"
		},
		{
			"label": "Price",
			"value": "$2,600/Month Available On October 31"
		},
		{
			"label": "Minimum Term",
			"value": "30 Day Min Stay"
		},
		{
			"label": "Pet Friendly?",
			"value": "No"
		},
		{
			"label": "Unit Type",
			"value": "Separate Unit"
		}
	],
	"accommodations": [
		"Essentials (Kitchenware Bathware Linens)",
		"Air Conditioning",
		"Heating",
		"Quiet Environment",
		"Full-size ironing board",
		"Non-Smoking",
		"You can park next to the garage in the carport.",
		"Internet",
		"WiFi",
		"Stovetop",
		"Full-size fridge",
		"Security",
		"Alarm",
		"Smoke Detector",
		"Carbon Monoxide Detector",
		"Fire Extinguisher",
		"Free Parking on Premises"
	],
	"features": [
		"Utilities Included",
		"Furniture Included",
		"In Complex W/D"
	],
	"managerProfile": "https://www.furnishedfinder.com/members/profile?u=Patricia.OBanion",
	"reviews": [
		{
			"title": "Perfect home away from home!",
			"date": "Submitted: 1/29/2022 12:00:00 AM",
			"description": "Rented this property for a nursing contract. Would have stayed longer but got transferred further south. Property was as beautiful in person as the pictures show. Amazing outdoor space. Close proximity to freeway, shopping, restaurants and gym. All the comforts of home. P was great to deal with and addressed any questions in a timely manner. Would 100% rent this place again if I got assignment in this area!",
			"rating": "5"
		}
	],
	"coordinates": {
		"latitude": 33.1781106,
		"longitude": -117.244601
	},
	"images": [
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44397997-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398007-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398005-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398004-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398010-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44397998-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398000-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44397999-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398003-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398008-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398001-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398002-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398006-full.jpg",
		"https://staticproperties.furnishedfinder.com/299655/1/299655_1_44398009-full.jpg"
	]
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that is available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
