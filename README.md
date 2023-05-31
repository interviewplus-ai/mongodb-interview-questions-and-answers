# MongoDB Interview Questions And Answers

Most targeted up-to-date MongoDB interview questions and answers list

## Table of Contents

1. [How do you create a collection in MongoDB?](#1-how-do-you-create-a-collection-in-mongodb)
2. [How do you insert a document into a collection in MongoDB?](#2-how-do-you-insert-a-document-into-a-collection-in-mongodb)
3. [How do you update a document in MongoDB?](#3-how-do-you-update-a-document-in-mongodb)
4. [How do you delete a document from a collection in MongoDB?](#4-how-do-you-delete-a-document-from-a-collection-in-mongodb)
5. [How do you retrieve all documents from a collection in MongoDB?](#5-how-do-you-retrieve-all-documents-from-a-collection-in-mongodb)
6. [How do you retrieve documents that match specific criteria in MongoDB?](#6-how-do-you-retrieve-documents-that-match-specific-criteria-in-mongodb)
7. [How do you retrieve documents with specific fields in MongoDB?](#7-how-do-you-retrieve-documents-with-specific-fields-in-mongodb)
8. [How do you sort documents in MongoDB?](#8-how-do-you-sort-documents-in-mongodb)
9. [How do you limit the number of documents returned in MongoDB?](#9-how-do-you-limit-the-number-of-documents-returned-in-mongodb)
10. [How do you perform aggregation in MongoDB?](#10-how-do-you-perform-aggregation-in-mongodb)
11. [How do you perform joins in MongoDB?](#11-how-do-you-perform-joins-in-mongodb)
12. [How do you perform text search in MongoDB?](#12-how-do-you-perform-text-search-in-mongodb)
13. [How do you create an index in MongoDB?](#13-how-do-you-create-an-index-in-mongodb)
- [Whats more?](#whats-more)
- [Contributing](#contributing)
- [License](#license)

## 1. How do you create a collection in MongoDB?

Answer:

```javascript
db.createCollection("users");
```

## 2. How do you insert a document into a collection in MongoDB?

Answer:

```javascript
db.users.insertOne({ name: "John Doe", email: "john@example.com" });
```

## 3. How do you update a document in MongoDB?

Answer:

```javascript
db.users.updateOne({ name: "John Doe" }, { $set: { email: "john.doe@example.com" } });
```

## 4. How do you delete a document from a collection in MongoDB?

Answer:

```javascript
db.users.deleteOne({ name: "John Doe" });
```

## 5. How do you retrieve all documents from a collection in MongoDB?

Answer:

```javascript
db.users.find();
```

## 6. How do you retrieve documents that match specific criteria in MongoDB?

Answer:

```javascript
db.users.find({ age: { $gt: 25 } });
```

## 7. How do you retrieve documents with specific fields in MongoDB?

Answer:

```javascript
db.users.find({}, { name: 1, email: 1 });
```

## 8. How do you sort documents in MongoDB?

Answer:

```javascript
db.users.find().sort({ age: 1 });
```

## 9. How do you limit the number of documents returned in MongoDB?

Answer:

```javascript
db.users.find().limit(10);
```

## 10. How do you perform aggregation in MongoDB?

Answer:

```javascript
db.users.aggregate([
    { $group: { _id: "$age", count: { $sum: 1 } } },
    { $sort: { count: -1 } }
]);
```

## 11. How do you perform joins in MongoDB?

Answer:

```javascript
db.users.aggregate([
    {
        $lookup: {
            from: "orders",
            localField: "_id",
            foreignField: "user_id",
            as: "orders"
        }
    }
]);
```

## 12. How do you perform text search in MongoDB?

Answer:

```javascript
db.users.createIndex({ name: "text", email: "text" });
db.users.find({ $text: { $search: "John" } });
```

## 13. How do you create an index in MongoDB?

Answer:

```javascript
db.users.createIndex({ email: 1 });
```

## What's more?
<a href="https://interviewplus.ai/database-administration/mongo-db/questions">A comprehensive list of questions and answers</a>

## Contributing
We welcome contributions from our users to help make this resource as comprehensive and useful as possible. If you have been recently interviewed and encountered a question that is not currently covered on our website, feel free to suggest it as a new question. Your contributions will be added to our platform, and we will make sure to credit you for your contributions. We appreciate your help in making our platform a valuable tool for all job seekers.

## License
MIT License
