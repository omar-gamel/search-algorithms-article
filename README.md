# Why Searching Algorithms important?

The searching algorithm is an algorithm that is designed to check and find an element that is stored in the data structure like an array or string.

- Sometimes an application needs to find some data. For Example, A Bank needs to find a customer’s account in their database or find an email to login into an application.

- Bigger algorithms may use a searching algorithm to search some data and then manipulate that data according to their use

- Some Search algorithms can be employed in games, like chess, the computer may try to find the best position on board to move its chess piece.

- When you type a file name in a computer or even on a search engine, they use different searching algorithms to find and present the file or data you are looking for.

# Types of Searching Algorithms

According to different data structure and type of search operations, search algorithms is divided into basically two different categories,

<h3>Sequential Search</h3>

In Sequential search, every element present in the list of array or group of data is traversed sequentially, checked, and compared. For example, Linear Search.

<h3>Interval Search</h3>

In Interval search, algorithms are specifically designed to work on the ordered lists. An ordered list is said to a group of data or a list of an array that is already sorted in either an ascending or descending order. Interval Search algorithms are much more efficient than Sequential Search algorithms as they don’t check every element in an array, rather than divide the length of an array in half, cutting down the search space. For Example, Binary Search.

# Linear Search

Linear Search is one of the simplest search algorithms to find and check any element if it is present in the given array list or not. One of the biggest advantage of using linear search is that it can be used to perform a search operation on any type of array list, no matter the array list is sorted in order or not.

<b>Steps</b>

- Start traversing from starting index or left side of the given array and compare each element of the array with the number we have to find

- If any first element matches, then return the index where that element is present in the array

- If it does not matches to any element present in the array, the return -1

<b>Code Snippet</b>

<p>

``` javascript

function linearSearch(num,x){
    // loop through every element
    for(let i = 0; i < num.length; i++){
      if(num[i] === x){ // check and compare every element
        return i // if found then returning index
    }
  }
  
  return -1 // if not found then returning -1
}
let arr = [64, 25, 12, 22, 11];
// sending element 12 to find in the array list
let result = linearSearch(arr,12);
console.log(result)
// 2, as 12 is present at the index 2
// sending element 42 to find in the array list
let result1 = linearSearch(arr, 42)
console.log(result1)
// -1, as there is no element inside the array list

```
</p>

<b>Best Time Complexity</b> – O(1) <br>
<b>Worst Time Complexity</b> – O(n) <br>
<br>
Though linear search algorithms are rarely used in practical applications because algorithms like the binary search approach have better performance and provide much faster solutions than linear search.

# Binary Search

The binary search algorithm is one of the most efficient searching algorithms based on the divide and conquers approach, in which the array given is sorted and according to the order of given sorted array, the middle element is compared to the number we have to find, if it is equal to that number then it returns the index.
<br>
<br>
But if the given number is greater than the middle element then the array is broken again in half and we have to search only in the half section of the array, which is the left side of the array is changed to mid-index + 1 and if the number is lesser than middle element then again array is broken into half and our search space also becomes half, and right side of the array is changed to mid-index – 1.
<br>
<br>
For example, Looking for any word in a dictionary, as all the words are sorted in alphabetical order, and according to that we divide the search area and ignore the half of dictionary data.

<b>Steps(Ascending Order)</b>

- first initialize the left and right side of the array, ex: left side = 0 and right side = array’s length – 1.
- Then take out the mid-index element of the array, and compare it with the given number, if true then return the index.
- If the given number is <b>smaller</b> than the mid-index element, then change the <b>right bound</b> of the array to <b>mid-index – 1.</b>
- Or, if the given number is <b>greater</b> than the mid-index element, then change the <b>left bound</b> of the array to <b>mid-index + 1.</b>
- But if the desired number is not present in the given array then return -1.

<b>Code Snippet</b>

<p>

``` javascript

function binarySearch(nums,x){
  // left side of the array
    let left = 0
  
  // right side of the array
  let right = nums.length - 1 
  
  while(left <= right){
  
       // finding the mid point of array
      let mid = Math.floor(left + (right - left) / 2);
      
      // if mid is equal to number the return index
      if(nums[mid] == x){
         return mid
         
        // if number is smaller than mid element
      }else if(nums[mid] > x){ 
      
          // decrease the right side to mid -1
        right = mid - 1 
        
        // if number is greater than mid element
      } else if(nums[mid] < x){
       
       // increse the left side to mid + 1
        left = mid + 1 
      }
    }
    
  // if the given number is not present in array then return -1
    return -1
}
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
// sending element 12 to find in the array list
let result = binarySearch(arr,4);
console.log(result)
// 2, as 12 is present at the index 2
// sending element 42 to find in the array list
let result1 = binarySearch(arr, 42)
console.log(result1)
// -1, as there is no element inside the array list

```
</p>

<b>Steps (Descending Order)</b>

- first initialize the left and right side of the array, ex – left side = 0 and right side = array’s length – 1.
- Then take out the mid-index element of the array, and compare it with the given number, if true then return the index.
- If the given number is <b>smaller</b> than the mid-index element, then change the <b>left bound</b> of the array to <b>mid-index + 1.</b>
- Or, if the given number is <b>greater</b> than the mid-index element, then change the <b>right bound</b> of the array to <b>mid-index – 1.</b>
- But if the desired number is not present in the given array then return -1.

<b>Code Snippet</b>

<p>



``` javascript

function binarySearch(nums,x){
  // left side of the array
    let left = 0
  
  // right side of the array
  let right = nums.length - 1 
  
  while(left <= right){
  
       // finding the mid point of array
      let mid = Math.floor(left + (right - left) / 2);
      
      // if mid is equal to number the return index
      if(nums[mid] == x){
         return mid
         
        // if number is smaller than mid element
      }else if(nums[mid] > x){ 
      
          // search only mid + 1 area
        left = mid + 1 
        
        // if number is greater than mid element
      } else if(nums[mid] < x){
       
       // search only mid - 1 area 
        right = mid - 1 
      }
    }
    
  // if the given number is not present in array then return -1
    return -1
}
const arr = [9, 8, 7, 6, 5, 4, 3, 2, 1];
// sending element 12 to find in the array list
let result = binarySearch(arr,3)
console.log(result)
// 6, as 3 is present at the index 2
// sending element 42 to find in the array list
let result1 = binarySearch(arr, 42)
console.log(result1)
// -1, as there is no element inside the array list

```
</p>

<b>Best Time Complexity</b> – O(1)<br>
<b>Worst Time Complexity</b> – O(log n)<br>
<br>

<b>Note –</b> You may notice in the code snippet we are using mid-index = left + (right - left) / 2 instead of mid-index = (left + right) / 2 , this is because using (left + right) / 2 to find the mid-index is not 100% correct as it may contain bugs because if we get very large values of left and right side then it may fall outside the maximum positive int value(231 – 1), that’s why it is better to use mid-index = left + (right - left) / 2 method.
<br>
<br>
One of the biggest disadvantages of the binary search is that it can only work on a sorted array, as it compares the number we have to find to mid-index and according to then it changes the search area that’s why if an unsorted array is given it will not able to provide the desired result.

# 

Link: https://www.devcript.com/searching-algorithms-with-javascript/
