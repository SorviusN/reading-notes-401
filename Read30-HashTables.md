# Reading Notes 30 - Hash Tables

## What is a hashtable?
Hash - restulf of an algorithm taking incoming string and converting it to a val that can be used for something.

Buckets - A bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.

Collisions - A collision is what happens when more than one key gets hashed to the same location of the hashtable. No bueno.

## Why use them?
- Hold unique values
- Dictionary
- Library

## What are they?
A data structure that utilizes key value pairs. Every Node or Bucket has key and value.  
The benefits include O(1) time analysis.

## Structure
### Hashing
A Hash code turns a key into an integer. It should be noted that hash codes should never have randomness to them.

### Creation of a hash table
A hashtable is traditionally created from an array, commonly the size of 1024. This matters because of index placement (where the key references within the array).  
Additionally, we want to perform logic that turns that hask key into an actual integer. One way would be as such:
``` cs
Key = "Cat"
Val = "Josie"

// Proceed to add every ascii value together to form a number.
67 + 97 + 116 = 280;

280 * 599 = 69648

69648 % 1024 = 16

Val.Place(16) // Place the value into the 16th index of our hash array.
```

## Collisions

Collisions occur when more than one key hashes to the same index in an array. A perfect "hash" will never have any collisions.  
<b>The workaround for solving collisions comes with changing each array value to be a linked list rather than just null. </b>  

Now, if two keys resolve to the same index in arr then their key/val pair can be stored as a node in the linked list. Each index in the arr is called a bucket because it can store multiple key value pairs now.

Since different keys lead to same bucket, you must store both the key and the val inside of the bucket.
Example: 
``` cs
hashMap.Add("Pioneer Square", 98104);
hashMap.Add("Alki Beach", 98116);

// LinkedList representation of the index.
Bucket 92: [{Pioneer Square: 98104} --> {Alki Beach: 98116}]
```

great resource: https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html
