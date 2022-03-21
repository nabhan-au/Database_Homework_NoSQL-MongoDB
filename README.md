# Database_Homework_NoSQL-MongoDB
• Find the total marks for each student across all subjects. 
db.user.aggregate([{$group:{_id:"$name",total:{$sum:"$marks"}}}])

• Find the maximum marks scored in each subject.
db.user.aggregate([{$group:{_id:"$subject",max:{$max:"$marks"}}}]) 

• Find the minimum marks scored by each student. 
db.user.aggregate([{$group:{_id:"$name",min:{$min:"$marks"}}}])

• Find the top two subjects based on average marks.
db.user.aggregate([{$group:{_id:"$subject",avg:{$avg:"$marks"}}},{$sort:{"avg":-1}},{$limit:2}])
