##Audience and Reading Level Determination 

Within Aspen Discovery, you have the ability to choose where your audience data is being pulled from. You can either pull the audience from bibliographic record data, item collection, item shelving location, or you can specify a specific item subfield. If you choose to pull the audience data from item information, you will need to configure that option within ILS Integration -> ILS Indexing Information and choose from the dropdown under 'Determine Audience By'. If you choose to pull from a specific item subfield, you will need to specify that under 'Audience Subfield'. Additionally, if you are going to pull the audience data from item information, you will need to create a translation map for the values within ILS Integration. 

If you choose to have the audience pulled from the bibliographic data, the code will determine the audience based on the leader, the 008 and the 006. Aspen uses the following logic to determine the audience from the bibliographic data:

First, Aspen determines what the material type is of the record. In order to determine this, Aspen looks at the leader. If position 6 is 'A' or 'T' and position 7 is 'A' or 'C' or 'D' or 'M' then the material type is determined as 'Books'. If position 6 in the leader is 'M' then the material type is determined as 'Computer file'. If position 6 in the leader is 'C' or 'D' or 'I' or 'J' then material type is determined as 'Music'. If position 6 in the leader is 'G' or 'K' or 'O' or 'R' then it is a 'all' material type.

After determining material type, Aspen looks at the 006 and position 5. If that exists, we use the Library of Congress determination of audience based on that value and material type. 

https://www.loc.gov/marc/bibliographic/bd006.html

If we cannot determine audience based on the 006 position 5 or no value exists there, then the audience will be pulled from the 008 position 22. We then use the Library of Congress determination of audience based on that value and material type.

https://www.loc.gov/marc/bibliographic/bd008.html

If there is no 006 position 5 and no 008 position 22, then the audience is labled as 'unknown'. 
