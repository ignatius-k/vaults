- there are entities without wallets, ie 
	- those push money to the system 
	- those pull money out of the system


~~on transactions,~~ 
~~there are some filtering fields used ie source, destination,~~
~~which might not be known by the person~~
- ~~for the source and destination, we are to search for the entity~~
- ~~but even then, I dotn expect users to cram these~~
- ~~there is sth usually used in field, wher we can display a searchabl e dropdown~~
- ~~[- **Trigger:** The user clicks the select box.~~
- ~~**Display:** A small list panel (modal) appears directly below.~~
- ~~**Search:** The user types a few letters.~~
- ~~**Filter:** The component hides choices that do not match what is being type] something like this, remember the options are very many, so we are to use things like lazy loading,  and pagination on the back like just 10 elements sth like that~~
- ~~but also this is not needed on only the source and destination here, but even in some other places,~~ 
~~still on transactions, I hope the data is paginated, and the searc/filtering of data is happening at the back~~

~~then, on entities,~~
- ~~hope the search by name or id, triggers a new call to the back and not jsut filtering the data that has been fetched~~
- ~~there are some changes needed here, its ok for the type badge to be colored, but the box with the frst character of the entity id is not required, just indexing is enough here without the coloring ie from 1, 2 ...~~
- ~~the bar, is fine, ie agents , bank caccounts, ..., but an extra one is required or needed ,~~ 
- ~~so, the aggregating suggestion for entites, instead of bar for selecting the type, and a input for selecting the name or id, lets use a search bar as is in transactions, to filetr these ie filetr by entity type, entity name/id, exposure range, transactiosn range,~~ 
  
~~network,~~
- ~~as indicated in transactions, the searchable dropdown is to be used here, ie search query needs to be dynamic, person can try to search by the entity id, entity name, or walllet id~~
  
  ~~and the results are to be brought back say if entity [ENTITY_TYPE] - [ENTITY_NAME], if wallet for now we show the wallet id, in future names will be able to bring them~~
~~also, the inboud and outboud directions are not that intuitive, why ways can we make it more intoutive on both the entity page, even the network~~

~~for the network ie the side component used to show the transactions selected, it needs some adbvancement~~
~~on each transaction we can have an arrow, say a green pointing down or red pointing up indicating money going out, rememvber the entity we are interested in si the subject no the selected, ie here inbound should mean the transaction increased the amount of the subject from the selected entity, recommendatiosn are welcomed~~

~~in the same side component after trnasactions, we show sth like summary, like number of transactions, total inbound, total outbound~~
~~the date ranfge is from  to~~

~~in network when user clicks on new node we follow the node, we need to track the previous node ie if its visible in the new query, we add on it like a tag~~
~~rember it spossible for it not to be visible ie if the user changes some params eg the form and to, yet the transctions with the previos node are not in that range~~

~~user & roles~~
- ~~when user is tapped on or clicked, if its the current user they should not be able to lock their account or edit role, and also they should be able to edit their full name, and for this a drawer, is preferred, same with creating a user~~
  

during ingestion, the phone number needs to be standardised, some are having the country code, and others dont have, the standardization should be lets remove the code since all numbers are for same country code

so numbers are appearing as different entites ie 256700111222 should be the same as 700111222 which is the same as 0700111222

when showing transactions, let page be 15

and also when showing transactions, current yl if source or destination is entity we display ENTITY 700111222 this should be [entity_type] [entity_name or id] ie PHONE NUMBER 700111222

Currently in the entity column, we show the entity_name then below the entity id
for billers its showing fine because they have a name, but now for others like agents, phone numbers with only id, they display hte name as dash then id down, which should be the like coalesce(name, id) ie if not name diplay id, and if id is displayed in the name space then its not showed down

also in the source/destination searchable dropdown, 
say I search and there is an entity Biller- Schoolpay I see it and click, the issue is after selecting the entity, what is displayed to the user is now the underlying id which could confuse the user