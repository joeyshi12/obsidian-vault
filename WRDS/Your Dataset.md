# Your Dataset
- Should be raw data for YOU to conduct analysis
- At least 30 data points / rows
- Statistics for provinces / territories will be problematic since there are less than <30 provinces, but for each state in US, data for each country ...

## Yugioh card infos
```
{
	"id": 34541863,
	"name": "\"A\" Cell Breeding Device",
	"type": "Spell Card",
	"desc": "During each of your Standby Phases, put 1 A-Counter on 1 face-up monster your opponent controls.",
	"race": "Continuous",
	"archetype": "Alien",
	"card_sets": [
		{
			"set_name": "Force of the Breaker",
			"set_code": "FOTB-EN043",
			"set_rarity": "Common",
			"set_rarity_code": "(C)",
			"set_price": "1.58"
		}
	],
	"card_images": [
		{
			"id": 34541863,
			"image_url": "https://storage.googleapis.com/ygoprodeck.com/pics/34541863.jpg",
			"image_url_small": "https://storage.googleapis.com/ygoprodeck.com/pics_small/34541863.jpg"
		}
	],
	"card_prices": [
		{
		"cardmarket_price": "0.14",
		"tcgplayer_price": "0.23",
		"ebay_price": "4.99",
		"amazon_price": "3.94",
		"coolstuffinc_price": "0.25"
		}
	]
}
```
- Where did the data come from?
	- API: https://db.ygoprodeck.com/api/v7/cardinfo.php 
	- API guide website: https://db.ygoprodeck.com/api-guide/
	- Organization: https://ygoprodeck.com/
- Card information dataset + https://db.ygoprodeck.com/api/v7/cardinfo.php
- What knowledge can be produced?
	- Correlate card rarity with set price
	- Most popular monster types
		- Average set prices over each card type for all cards
	- Which store sells cheaper cards?
		- Average card prices over each store for all cards
- Relevant variables / Nature of variables
	- set_rarity = Qualitative
	- set_price = Quantitative
	- cardmarket_price = Quantitative
	- tcgplayer_price = Quantitative
	- ebay_price = Quantitative
	- amazon_price = Quantitative
	- coolstuffinc_price = Quantitative