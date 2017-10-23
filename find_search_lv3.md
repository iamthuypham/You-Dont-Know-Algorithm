# Level 3
We finished ordering. At a store, a worker will pick freshest items and put in a box before delivering it to us on the same day. In near future, robot will help us to detect freshness and nutrition by image processing and laser measurement. Let's see how we implement that.

#### Human
Find *fruit products*, which *not* expired in 7 days, from *the store*

#### Robot
Find **i** (items) which are existed in a **mess** filtered by a **condition**

## Let's Analyze
There are at least 2 ways for robot to approach this scenarios:
#### **One-by-one:** 
One-by-one is the method which human already have done. The worker picks each product randomly, check apple's expiration day is not next 7 days, put in deliver box. Using this method if customer orders a small number of products.

Steps: 
1. Iterate each **i**
2. Apply condition on each **i**

#### **Priority**
Priority is the method which requires extra step. Apples are prioritized by its expiration day. The worker picks products from top to bottom. Using this method if customer orders a large number of products.

Steps:
1. Prioritize the **mess** by **condition**
2. Pick **i**

## Method 1: One-by-one
To use this method, array data structure is enough to do the work.

Input:
```
var store = [{"watermelon": 10}, {watermelon: 2}, {"apple": 8}, {"apple": 1}, {"banana":4}, {"banana": 10}]
var order = ["apple", "watermelon"]
```
Output:
```
[{"apple":8}, {"watermelon":10}]
```
Code:

1. Iterate each product in store and return if its expiration date is not within 7 days
```
var fresh = store.filter(function (product) {
  return product.exd > 7
})
// fresh = [{ name: 'watermelon', exd: 10 }, { name: 'apple', exd: 8 }, { name: 'banana', exd: 10 } ]
```
2. Now in the fresh products, there is "banana" what we don't want. 
```
order = ["apple", "watermelon"]
fresh = [{ name: 'watermelon', exd: 10 }, { name: 'apple', exd: 8 }, { name: 'banana', exd: 10 } ]
```
We want to find products which are existed in both **order** and **fresh** arrays.

From here, this is [Level 2 problem: **Find i (items) which are existed in both list (small) and mess (large, infinitive)**](https://github.com/iamthuypham/You-Dont-Know-Algorithm/blob/master/find_search_lv2.md) 
You can find a solution on that page.

```
// Complexity:
// Speed: O(n + (m + n)) or O(n + min(min(mLogn, nLogm)))
```
