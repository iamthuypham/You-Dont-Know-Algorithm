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
- Sort this list by alphabet (Sorting will be discussed later)
- Find the item at the middle of the list
- Compare the item with the item we want

There are two ways to implement this menthod

1. Recursive Binary Search
```
var L = [ a, d, h, y, z ]
var itemIWant = y
var left = 0
var right = len(L)-1

function find(L, l, r, itemIWant) {
	if (r < l) {
		return -1
	}
	
	// Find middle element
	m = l + Math.ceil((r - l)/2)

	// If element is present at the middle itself
	if (L[m] == x) {
		return m
	    
	// If element is smaller than mid, then it can only
	// be present in half left of the list
	} else if (L[m] > itemIWant) {
		return find(L, l, m-1, itemIWant)

	// Else the element can only be present in right subarray
	} else {
		return find(L, m+1, r, itemIWant)
	}
}

find(L, left, right, itemIWant )

// Complexity:
// Space: O(logn)
// Speed: O(n/2)
```

2. Iterative Binary Search
```
var L = [ a, d, h, y, z ]
var itemIWant = y
var left = 0
var right = len(L)-1

def find(L, l, r, itemIWant):
	while (l <= r) {
		m = l + Math.ceil((r - l)/2)

      // Check if itemIWant is present at mid
      if (L[m] == itemIWant) {
      	return mid

      // If itemIWant is greater, ignore left half
      } else if (L[m] < itemIWant) {
      	l = m + 1

      // If x is smaller, ignore right half
      } else {
      	r = m - 1
      }
    }
    
    // If we reach here, then the element was not present
    return -1
}

find(L, left, right, itemIWant )

// Complexity:
// Space: O(1)
// Speed: O(n/2)
```
---
[Next: Find & Search Level 2](https://github.com/iamthuypham/You-Dont-Know-Algorithm/blob/master/find_search_lv2.md)
