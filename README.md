# Projects
Farm-2-Plate Solution:
=======================
This is a supply chain management Solution where any customer will be able to invest or order in any farm produce
The customers will be able to track the lifecycle of food they are consuming
Farmers will get benifits directly by consumer's investments
App will manage the agreements between farmers and Investors

Basic Rules :
Investors are the consumers
An investment can be before 1 second before the delivery or 1 year before the delivery
The cost of the produce is declared in the Contract :
Contract date,
Investor's Name,
Farmer's name,
obligation{produce,Quantity,Price},
Date of Investment,
Date of Delivery,
Contract Duration,
Insurance id,








Villege secury system :
=============================

Identify the entry points (Gates) of the villege.
Using cameras, log the user activity (post)

User Signup (adds new row in identity table [userID,key1,key2,key3])

Users should be able to access their data(get), after completing Identity before one of the cameras

user should be able to update data, after login. (put)

Live data is available via h2 database(get), for the past 24 hours.

H2 data will be automatically removed after 24 hours.


Mongo DB tables :
gate - gate_ID, location, key
activity_<gate_ID from gates table> - activity_ID,parameters[int referance_model(),int referance_model()]
referance_<gate_ID from gates table> - referance_ID, 
user - Distributed Database for all gates. -  identity.json user_ID index



Camera MS : no security
1. post(activity_f1.json) to h2 DB

Identity MS : 
interfaces : Camera MS - identifies each activity and updates identity table (validate with available gatekeys table in mongo) - gate keys are added from backend.
3. post(identity.json) - to mongo DB. user_ID,key1,key2,key3,identity[]

Login MS : This will create a new instance of selfSupport MS :
4. post(login.json)  - Validations before selfSupport MS is created - [bool haskeys,bool validatekeys[key1,key2,key3]] issuer validates keys from mongo DB - open mongoDB access to view "activity data".



SelfSupport MS : 
get(activity_<user_ID>)

Issuer MS : 
APIs of MS 4 : selfSupport MS(identity)  
5. put(profile) - returns activity.json
6. get(activities)
7. get(activity_details)
8. delete(activity)







