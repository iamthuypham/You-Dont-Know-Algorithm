## Level 2
#### Human
Find *some fruit products* from *a store*

Find *all iPhones and Android watches location* in *a building*

Find *all customers whose age from 25 to 34* from *a store members list*

#### Robot
Find **i** (items) which are existed in both **mess1** and **mess2**

#### Example
Input:
```
var groceryList = ["apple", "watermelon"]
var store = ["apple", "banana", "chicken", "cucumber", "icecream",..., "water", "watermelon"]
```
Output:
```
["apple", "watermelon"]
```

#### Let's Analyze
Whenever finding multiple items, that means we have (sort of) two arrays:
- Items we look for
- Items from (some kind of) resources

For the example *buy some fruit products from a store*
- Items we look for: any fruit product
- Items from resources: all products in our basket

**How do we buy some fruit products from a store?**
- Bring our grocery list to the store (of course!)
- Read first item "apple"
- Look for "Apple" sign
- Checkmark the item "apple" in the list
- Read second item 
...

If we want a robot to do above steps, we have write a program with **nested for loop**. Nested for loop should be avoided because of time cosuming. 

*"Why time consuming? I thought we all did this way for long time"*

Yes, we do this for decades, but we don't have to tell robot do the same way. Do you remember the last time you walk to one end of a store for one product, walk to another end for another, and again?

*"Well, that's reason why we should sort items in the grocery list by their locations inside a store"*

Yes, what if there is none apple in the store and our robot still goes to the Fruit section and scan for "apple" sign or detect each object if it is an apple ?

*"Alright, so we sort items in the grocery list by their locations and check whether each item is sold out with a store employee. Skip the item if it is sold out"*

#### Conclusion
1. "What if" question helps us to explore rare cases or new areas of a problem. Answering "what if" question by adding more conditions to the solution is not an effective approach. **We need a dynamic solution**

2.  It is good to use robot to memorize all conditions and follow the steps we did. But it is not smart to tell them duplicate our inefficiency. Our ultimate goal is **reducing time and effort for robot**, *not* **by robot**

*How do we accomplish that?*

#### Method 1: **Tell a robot go shopping online**
- Scan the grocery list and open the store website (of course!)
- Click on Fruits section and sort products by name
- Read first item "apple"
- Scan each item 's name until reach "apple"
- Add to cart and checkmark
- Read second item "watermelon"
- Scan next items 's name until reach "watermelon"
- Add to cart and checkmark

**Why this method?**
We don't have to worry about items' location or whether they are sold out or others "what if". It is a dynamic solution.

```
var m = groceryList.length
var n = store.length
function find(groceryList, store, m, n) {
    var i = 0
    var j = 0
    while (i < m and j < n) {
        if groceryList[i] < store[j] {
            i += 1
        } else if (store[j] < groceryList[i]) {
            j+= 1
        } else {
            print(store[j])
            j += 1
            i += 1
        }
    }
}
// Complexity
// Speed: O(m+n)
```

**A robot can do better!**
In this method, our robot scans each item 's name. When we, as a  human, we know "watermelon" **is not likely** next to "apple" and we usually skip to end of the page. How can our robot know **"watermelon" is not likely next to "apple"** ?

#### Method 2: **Tell a robot to think**
...
- Read second item "watermelon"
- Find a product which is right at middle of the page. Let's say "milk"
- Think "watermelon" is after "milk"
- Find a product which is right at middle between "milk" and end of the page. Let's say "raisin"
- Think "watermelon" is after "raisin"
...



