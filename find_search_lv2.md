## Level 2
#### Human
Find *fruit products* in *a basket*

Find *all iPhones and Android watches location* in *a building*

Find *all customers whose age from 25 to 34* from *a store members list*

#### Tricky human
Find *matching products* in *customer 1 and customer 2's baskets* 

#### Robot
Find **i** (items) which are existed in both **mess1** and **mess2**

#### Example

Input:
```
var groceryList = ["apple", "watermelon"]
var store = ["apple", "banana", "chicken", "icecream", "cucumber"]
```
Output:
```
["apple", "banana"]
```

#### Let's Analyze

Whenever finding multiple items, that means we have (sort of) two arrays:
- Items we look for
- Items from (some kind of) resources

For example, *buy some fruit products from a store*
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

We will never stop saying "what if" because we are human and we have our unique needs.

Now it is good to use robot to memorize all conditions and follow the steps we did. 
But it is not smart to tell them duplicate our inefficiency.

Our ultimate goal is reducing time and effort by combining technology and useful data.

*"Ok, so what will we do?."*

**Tell a robot/AI buy some fruit products from an online store**
- Scan the grocery list and open the store website (of course!)
- Click on Fruits section and sort products by name
- Read first item "apple"
- Page shows first product as "apple"
- Add to cart and checkmark
- Read second item "watermelon" and **think "watermelon" is not likely to be on page 2**
- Click on the second page from the last one
- Click on next or previous page of the current page to find "watermelon"

See a different?

*"How can a robot/AI know that "watermelon" is not likely to be on page 2?"*

Yub, that's why we use algorithm.

#### Method

(below code is in editing progress)
```
def printIntersection(arr1, arr2, m, n):
    i,j = 0,0
    while i < m and j < n:
        if arr1[i] < arr2[j]:
            i += 1
        elif arr2[j] < arr1[i]:
            j+= 1
        else:
            print(arr2[j])
            j += 1
            i += 1
 
# Driver program to test above function
arr1 = [1, 2, 4, 5, 6]
arr2 = [2, 3, 5, 7]
m = len(arr1)
n = len(arr2)
printIntersection(arr1, arr2, m, n)
```
