# JBIB
An alternative bibliographic format to MARC for libraries.

# The Argument for JBIB
I come from a web development background, which means my job for many years was to organize information and make it searchable. My primary focus for managing hundreds of web sites was the end user. When I stepped into the library industry I was shocked and disappointed at the outdated and difficult methods used to categorize and organize bibliographic information. Library systems were being written in PERL, and using data standards (MARC, AACR2) that were created in the 1960s (84 years old at this writing). These standards and methods were created when computers were in the dawn of their existence and were not regularly available. The term "search engine" wasn't even a thing yet. I was also disappointed by the approach to subject headings used in the library industry (5 volumes of subject headings... really?).

Cataloging books using these traditional methods takes a LONG time and has a steep learning curve. The end result of these efforts is a record which is difficult for computers to parse and search, and is difficult for humans to read. In effect: a waste of time and money. Most libraries (public and school libraries) do not need the complicated records that are the standard in the industry. I cannot even guess the number of hours wasted each year on cataloging when it could be done a simpler way. So, after learning and using these systems on a daily basis for almost two years, I decided it was time to do something about it.

JBIB is my answer to this problem. It is compact, easy to use, takes very little training, and is flexible enough that libraries can add to it as needed. JBIB is based on BIBSJSON, which took **huge** steps in the right direction for modern computing criteria. The reason for using JSON format to store information is simple. JSON is widely accpeted and can be parsed by all modern programming languages, JSON validators are plentiful and easy to use, and it is a storage format that is also easy for humans to read.

# JBIB Sample
Here is a sample record showing how the JBIB format should look:


    /* 
    JBIB specification 
    Created by Kendall Purser
    For Bonneville County Library District
    2024-04-20
    */
    
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
    "id": {
        "isbn": [9785555555555, 9785555555551],
        "loc": ["0-999-55555"],
        "doi": ["10.1644\/14-MAMM-A-004"],
        "call_num": "FOOD Easy",
        "dewey": 641.595
    },
	"subject": ["non-ficiton", "recipe", "china", "chinese", "food", "cooking"],
	"summary": "One hundred easy to make Chinese recipes for the hopeless housewife and budding chef. 
        Cook and Heere take you through each recipe step by step with easy to follow pictures and instructions."
    }

# Benefits of JBIB
1. JSON is a widely accepted storage format with interpreters in all major programing languages
2. JSON validation tools are widely available
3. Lists of data stored in arrays are much easier to itterate over than traditional MARC formatting, this gives the computer increased performance and searchability
4. Easy for catalogers to read the fields rather than memorizing MARC numbers, indicators, and subfields
5. Expandable beyond the base specificaiton if libraries want to add more fields
6. Comments can be left in the file without needing additional systems: // (end of line) and /* (multi-line) */
7. Uses "blog style" tags for easy subject searching, rather than complicated subject headings (Literally: "What would someone type in a search engine who is looking for this book?")
8. Much shorter and easier to use than the proposed BIBFRAME format that is currently in development

# Plan for Implementation
1. Create tools to transfer bibliographic records to and from JBIB and MARC
2. Create a simple ILMS that runs on JBIB that is Free Open Source Software (FOSS).
3. Create a large repository of JBIB records to pull from (z39.50 equivalent)
4. Promote the JBIB format to the powers that be (Other local libraries, Library of Congress, American Library Association, OCLC, etc...)


