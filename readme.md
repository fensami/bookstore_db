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

✔️মাল্টি-টেন্যান্সি অ্যাপ্লিকেশনে উপকারী (একটা ডেটাবেসে ভিন্ন ভিন্ন ক্লায়েন্টের জন্য আলাদা schema)।

```
