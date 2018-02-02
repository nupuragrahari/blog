---
title: Data Normalization
catalog: true
date: 2017-09-01 22:01:47
subtitle:
header-img:
tags:
- dataNormalization
---
When I first heard of data normalization, the concept seemed rather confusing to me. However, in some time I came across a rather simple explanation that I'd like to share.

Data Normalization is the process of analyzing a relation to ensure it is free from three anomalies.These anomalies if present will restrict the data from having referential integrity.
The three anomalies are :
1. Updation anomalies
2. Deletion anomalies
3. Insertion anomalies

Now, the relation is in first normal form if it is free from any multivalued attributes. So, if there are any multivalued attributes present in the table we need to remove them to get it in first normal form.
In other words every attribute is atomic. Also, to note if a relation is not in it's first normal form, it isn't a relation.
For a relation to be in second normal form, the requirements of first normal form must be fulfilled plus every attribute that is not a key should be fully functionally dependent on the entire primary key and not just a part of it.
This means no partial dependencies. Partial dependency implies when some of the non-key attributes depend on only a part of the primary key and not the entire primary key.
There is also something called a transitive dependency, which means that the primary key determines an attribute which in turn determines another third attribute.
The transitive dependency needs to be removed for a relation to be in the third normal form.

Well, there is also a fourth normal form and then a fifth and so on, but for data designing for business concepts third normal form has been proven to be more than sufficient.
I hope this read has helped you with the concept.