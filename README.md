# jbib
An alternative bibliographic format to MARC for libraries.

I come from a web development background rather than a library background, so my approach to storing information is quite different from the traditional approach. For a storage format to be accepatble on the web it needs to fit the following criteria:

1- Easy for humans to read (catalogers)
2- Easy for computers to read (search engines)
3- Have a small data footprint (less than 1 kilobyte in size if possible)

After a hard look around for an alternative format for MARC and finding none that met these criteria, I decided to create my own. The closest format that had most of these qualities was BIBSJSON, so I decided to take that as a starting point and improve on it. The format I arrived at I am calling JBIB (or JSON Bibliography). This protocol is stored in JSON format, and should be validated as such.

Here is a sample record showing how the format should look:

// JBIB specification
// Created by Kendall Purser
// For Bonneville County Library District
// 2024-04-20

{
	"rec_type": "JBIB", //JavaScript Bibliography
	"title": "Easy Chinese Food for the Hungry",
	"author": ["I. M. Cook", "Ben Heere"],
	"publisher": "Ben Heere Publishing",
	"year": 2014,
	"item_type": "book",
	"pages": 200,
	"height_cm": 19,
	"series": ["International Foods or Die", 2], // Series title, book in series
	"identifier": {
		"isbn": [9785555555555, 9785555555551],
		"loc": ["0-999-55555"],
		"doi": ["10.1644\/14-MAMM-A-004"],
		"call_num": "FOOD Easy",
	},
	"subject": ["non-ficiton", "recipe", "china", "chinese", "food", "cooking"],
	"summary": "One hundred easy to make Chinese recipes for the hopeless housewife and budding chef. Cook and Heere take you through each recipe step by step with easy to follow pictures and instructions."
}

#Plan for Implementation
1- Create a simple ILMS that runs on JBIB that is Free Open Source Software (FOSS).
2- Create a large repository of JBIB records to pull from (z39.50 equivalent)
3- Promote the format to the powers that be (Other local libraries, Library of Congress, American Library Association, OCLC, etc...)
