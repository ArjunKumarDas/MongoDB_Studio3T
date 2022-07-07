# MongoDB_Studio3T
Common Command Line In MongoDB_Studio3T

#01 Insert One: 
db.employee.insertOne({})
db.employee.insertMany({})

#02 Select All Data:
db.employee.find({})
db.employee.aggregate([])

#03Row Count:
db.employee.find({}).count('total')
db.employee.aggregate([{$count:'total'}])

#04 Sorting: 
db.employee.find({}).sort({salary:1})
db.employee.find({}).sort({salary:-1})

#05 Limiting: 
db.employee.find({}).limit(2)
db.employee.aggregate([{$limit:2}])
#Limiting first and last:

#Limiting  Ascending Order: 
db.employee.find({}).sort({_id:1}).limit(2)
db.employee.aggregate(
[
{$sort:{_id:1}},
{$limit:5}
])

#Limiting  Descending Order: 
db.employee.find({}).sort({_id:-1}).limit(2)
db.employee.aggregate(
[
{$sort:{_id:-1}},
{$limit:5}
])

#06 Select By Match Condition: 
db.employee.aggregate([
{$match:{age:{$gt:29}}}
])
db.employee.find({age:{$gt:29}})

#10 Select By Match Condition AND OR:
db.employee.aggregate([
{$match:{Age:{$gt:29}}},
{$match:{City:"Singi"}}
])



