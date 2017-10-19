# Find/Search 

## Level 1
#### Human
Find *an apple* in *a basket*

Find *my lost phone* around *the house*

Find *a customer name* from *a store members list*

#### Robot
Find **i** (item) in a **mess** (unknown data structure)

#### Method 1
- Let's organize this **mess** by putting them in a **List** data structure. 
- Iterate each item in the list 
- Detect if each item is the item we want

```
var itemIWant = z
var L = [x, y, z]

for (var i = 0; i < L.length; i++) {
	if (L[i] === itemIWant) {
    	return i
    }
}

// Complexity: 
// Speed: O(n)
```

#### Method 2
- Let's organize this mess by putting them in a **List**
- Sort this list by alphabet
- Find the item at the middle of the list
- Compare the item with the item we want


## Level 2
#### Human
Find *fruit products* in *a basket*

Find *all iPhones and Android watches location* in *a building*

Find *all customers whose age from 25 to 34* from *a store members list*

#### Tricky human
Find *matching products* in *customer 1 and customer 2's baskets* 

#### Robot
Find **i** (items) which are existed in both **mess1** and **mess2**

#### Method


#### Example:
Input:
```
var groceryList = ["apple", "banana", "kiwi"]
var basket = ["apple", "banana", "chicken", "icecream", "cucumber"]
```
Expected output:
```
["apple", "banana"]
```


