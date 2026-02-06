# MongoDB Checkpoint

## 📌 Project Overview
This project demonstrates basic MongoDB operations including:
- Creating a collection (`contactlist`)
- Inserting multiple documents
- Querying documents with filters
- Updating fields
- Deleting documents
- Displaying results

It serves as a checkpoint to validate understanding of CRUD operations in MongoDB.

---

## 🗂️ Collection: `contactlist`
### Sample Documents Inserted
```json
[
    { "lastName": "Ben", "firstName": "Moris", "email": "ben@gmail.com", "age": 26 },
  { "lastName": "Kefi", "firstName": "Anis", "email": "kefi@gmail.com", "age": 15 },
  { "lastName": "Emilie", "firstName": "brouge", "email": "emilie.b@gmail.com", "age": 40 },
  { "lastName": "Alex", "firstName": "brown", "age": 4 },
  { "lastName": "Denzel", "firstName": "Washington", "age": 3 }
]
### Additional Document Inserted
To better illustrate the **fourth instruction** (filtering contacts by age > 18 and name containing "ah"),  
I added the following document to the `contactlist` collection:

```json
{
  "_id": ObjectId("6986547be7b42d1a14628ca6"),
  "lastName": "James",
  "firstName": "Cahli",
  "age": 19
}

🔍 Queries Demonstrated
Insert documents

js
db.contactlist.insertMany([...])
Find all contacts

js
db.contactlist.find().pretty()
Find by ID

js
db.contactlist.findOne({ _id: ObjectId("PUT_THE_ID_HERE") })
Filter by age

js
db.contactlist.find({ age: { $gt: 18 } })
Filter by age and name containing "ah"

js
db.contactlist.find({
  age: { $gt: 18 },
  $or: [{ firstName: /ah/i }, { lastName: /ah/i }]
})
Update a contact’s first name

js
db.contactlist.updateOne(
  { lastName: "Kefi", firstName: "Seif" },
  { $set: { firstName: "Anis" } }
)
Delete contacts under age 5

js
db.contactlist.deleteMany({ age: { $lt: 5 } })
✅ Key Learnings
How to insert, query, update, and delete documents in MongoDB.

Using operators like $gt, $lt, $or, and regex for filtering.

Understanding how _id works for uniquely identifying documents.

Practicing schema flexibility (some documents may not have all fields).
