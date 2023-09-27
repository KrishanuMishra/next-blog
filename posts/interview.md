---
title: "Interview Prepration"
subtitle: "Here is a qurated list of quetions for interview prepration."
date: "2023-09-27"
---

- [Javascript Questions:](#javascript-questions)
- [DSA Questions:](#dsa-questions)

# Javascript Questions:

**Q.1 What are all possible ways to create objects in Javascript?**

```js
var object = new Object(); // 1

var object = new Object.create(null); // 2

var object = {} // 3

function Person(name){
    var object = {};
    object.name = name;
    object.age = 21;
    return object;
}
var object = new Person("Krishanu"); // 4

class Person{
    constructor(name){
        this.name = name;
    }
}
var object = new Person("Krishanu"); // 5

```

**Q.2 What is a prototype chaining?**

It is a way to make new object types based on already made objects. It is like inhertence;

```js
class Person{
    constructor(name){
        this.name = name;
    }
}

Person.prototype.greet = function(){
    return `Hello, I am ${this.name}.`;
}
const john = new Person("John");
console.log(john.greet()); // Output: Hello, I am John.
```

# DSA Questions:

**1. Reverse an array:**

Input:[1,2,3,4]  Output:[4,3,2,1]
```c
void reverse_array(int arr[],int n){
    for(int i =0;i<n/2;i++){
        swap(arr[i],arr[n-i]);
    }
}
```

**2. Find maximum element:**

Input: [3, 7, 1, 9, 5], Output: 9
```c
int find_max(int arr[],int n){
    int max = INT_MIN;
    for(int i =0;i<n;i++){
        if(arr[i]>max) max = arr[i];
    }
    return max;
}
```

**3. Find a peak element which is not smaller than its neighbors.**

Input: [5, 10, 20, 15] Output: 20

```c
int peak_element(int arr[],int n){
    int val;
    for(int i =1;i<n;i++){
        if(arr[i]>arr[i-1] && arr[i]>arr[i+1]){
            val = arr[i];
        }
    }
    return val;
}
```

**4. Find the occurrence of an integer in the array.**

```c
int find_k_count(int arr[],int n,int k){
    int count = 0;
    for(int i =0;i<n;i++){
        if(arr[i]==k) count++;
    }
    return count;
}
```

```c
// Using Map:
int find_k_count(int arr[],int n,int k){
    unordered_map<int,int> mp;
    for(int i =0;i<n;i++){
        mp[arr[i]]++;
    }
    auto it = mp.find(k);
    return it->second;
}
```