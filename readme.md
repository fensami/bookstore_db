# 1. What is PostgreSQL?

## PostgreSQL (পোস্টগ্রেসকিউএল) একটি open-source relational database management system (RDBMS), অর্থাৎ এটি একটি মুক্ত উৎস সম্পর্কিত ডেটাবেস পরিচালনা ব্যবস্থা।

### Key Features (মূল বৈশিষ্ট্যসমূহ):

```
✅ SQL-compliant (এসকিউএল সমর্থিত): এটি Standard SQL ব্যবহার করে ডেটা পরিচালনা করে।

✅ ACID-compliant: এটি Atomicity, Consistency, Isolation, Durability নিশ্চিত করে — যা ডেটার নিরাপত্তা ও নির্ভরযোগ্যতা বজায় রাখে।

✅ Advanced data types: JSON, XML, Array, Key-Value Pair (hstore) এর মত জটিল ডেটা টাইপ সাপোর্ট করে।

✅ Extensible (বর্ধনযোগ্য): আপনি নিজের function, data type এবং programming language ব্যবহার করে এক্সটেনশন তৈরি করতে পারেন।

```

# 2. What is the purpose of a database schema in PostgreSQL?

## PostgreSQL-এ schema হলো ডেটাবেসের ভেতরে একটি "namespace" বা জায়গা, যেখানে আপনি table, view, function, index ইত্যাদি রাখতে পারেন। আপনি এটিকে ডেটাবেসের ভেতরে একটি আলাদা folder হিসেবে ভাবতে পারেন।

### উদ্দেশ্য:

```
✔️ ডেটা গুছিয়ে রাখার জন্য।

✔️ একাধিক ইউজার বা অ্যাপ্লিকেশন যাতে একসাথে একই ডেটাবেস ব্যবহার করতে পারে, কিন্তু একে অপরের ডেটায় হস্তক্ষেপ না করে।

✔️ সিকিউরিটি ও পারমিশন আলাদাভাবে ম্যানেজ করা সহজ হয়।

✔️ মাল্টি-টেন্যান্সি অ্যাপ্লিকেশনে উপকারী (একটা ডেটাবেসে ভিন্ন ভিন্ন ক্লায়েন্টের জন্য আলাদা schema)।

```

# 3. Explain the Primary Key and Foreign Key concepts in PostgreSQL.

## Primary Key

```

Primary Key হলো একটি কলাম বা একাধিক কলামের সমষ্টি যা প্রতিটি রো (row) কে অন্যরকম বা ইউনিক করে চিহ্নিত করে।

এটি নিশ্চিত করে:

✔️ কোনো ডুপ্লিকেট ভ্যালু থাকবে না

✔️ ভ্যালু null হতে পারবে না

✔️ প্রতিটি টেবিলে মাত্র একটি Primary Key থাকতে পারে।

```

## Foreign Key

```
Foreign Key হলো এমন একটি কলাম যা অন্য টেবিলের Primary Key কে রেফার করে।
এটি দুইটি টেবিলের মধ্যে সম্পর্ক (relationship) তৈরি করে।

এটি referential integrity নিশ্চিত করে — অর্থাৎ, foreign key-এর ভ্যালু অবশ্যই ঐ টেবিলে থাকতে হবে যেটিকে এটি রেফার করছে।

```

# 4. What is the difference between the VARCHAR and CHAR data types?

```
CHAR(n) → ফিক্সড লেন্থ (স্থির দৈর্ঘ্য)

যদি আপনি ৫ অক্ষরের জন্য CHAR(5) দেন এবং 'abc' ইনপুট দেন, তাহলে এটি 'abc ' হিসেবে সেভ হবে (২টা স্পেস যোগ করবে)।

VARCHAR(n) → ভ্যারিয়েবল লেন্থ (পরিবর্তনশীল দৈর্ঘ্য)

যদি VARCHAR(5) দেন এবং 'abc' দেন, তাহলে কেবল 'abc' ই সেভ হবে, কোনো স্পেস যোগ হবে না।

সংক্ষেপে:

CHAR → স্থির দৈর্ঘ্য, স্পেস দিয়ে পূরণ হয়

VARCHAR → পরিবর্তনশীল দৈর্ঘ্য, যতটুকু দরকার ততটুকুই

```

# 5. Explain the purpose of the WHERE clause in a SELECT statement.

```
SELECT স্টেটমেন্টে WHERE ক্লজ ব্যবহার করা হয় ডাটাবেস থেকে নির্দিষ্ট শর্ত অনুযায়ী ডেটা বের করতে। এটি আপনাকে নির্ধারণ করতে দেয় কোন কোন সারি (row) আপনি দেখতে চান।

যদি WHERE ক্লজ ব্যবহার না করা হয়, তাহলে পুরো টেবিলের সব ডেটা চলে আসবে।

```

# 6. What are the LIMIT and OFFSET clauses used for?

```
✅ LIMIT:
LIMIT ক্লজ ব্যবহার করা হয় কতটি রেকর্ড রিটার্ন করতে হবে তা নির্ধারণ করতে। যেমন ধরুন, আপনি শুধু প্রথম ৫টা ডেটা দেখতে চান — তখন LIMIT 5 ব্যবহার করবেন।

✅ OFFSET:
OFFSET ক্লজ ব্যবহার করা হয় শুরুতে কতটি রেকর্ড বাদ দিতে চান তা জানানোর জন্য। উদাহরণস্বরূপ, OFFSET 5 মানে প্রথম ৫টা রেকর্ড বাদ দিয়ে এরপরেরগুলো দেখাবে।

```

# 7. How can you modify data using UPDATE statements?

```
UPDATE স্টেটমেন্ট ব্যবহার করা হয় টেবিলের আগের ডেটা পরিবর্তন করতে।
যখন আপনি কোনো রেকর্ডের এক বা একাধিক কলামের ভ্যালু চেঞ্জ করতে চান, তখন এটি ব্যবহার করা হয়।
```
