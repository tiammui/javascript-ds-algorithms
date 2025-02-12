## What is Merge Sort ?

* It's a combination of two things - merging and sorting!
* Exploits the fact that arrays of 0 or 1 element are always sorted
* Works by decomposing an array into smaller arrays of 0 or 1 elements, then building up a newly sorted array

## How does it work?

```javascript

[ 8, 3, 5, 4, 7, 6, 1, 2 ]

[ 8, 3, 5, 4 ] [ 7, 6, 1, 2 ]

[ 8, 3 ] [ 5, 4 ] [ 7, 6 ] [ 1, 2 ]

[ 8 ] [ 3 ] [ 5 ] [ 4 ] [ 7 ] [ 6 ] [ 1 ] [ 2 ]

[ 3, 8 ] [ 4, 5 ] [ 6, 7 ] [ 1, 2 ]

[ 3, 4, 5, 8 ] [ 1, 2, 6, 7 ]

[ 1, 2, 3, 4, 5, 6, 7, 8 ]

```

## Merging Arrays

* In order to implement merge sort, it's useful to first implement a function responsible for merging two sorted arrays
* Given two arrays which are sorted, this helper function should create a new array which is also sorted, and consists of all of the elements in the two input arrays
* This function should run in O(n + m) time and O(n + m) space and should not modify the parameters passed to it.

## Merging Arrays Pseudocode

* Create an empty array, take a look at the smallest values in each input array
* While there are still values we haven't looked at.
    * If the value in the first array is smaller than the value in the second array, push the value in the first array into our results and move on to the next value in the first array
    * If the value in the first array is larger than the value in the second array, push the value in the second array into our results and move on to the next value in the second array
    * Once we exhaust one array, push in all remaining values from the other array

## Merge Sort Pseudocode

* Break up the array into halves until you have arrays that are empty or have one element
* Once you have smaller sorted arrays, merge those arrays with other sorted arrays until you are back at the full length of the array
* Once the array has been merged back together, return the merged (and sorted!) array

## How it Works?

<p align="center">
<b>[10,24,73,76]</b><br />
<b>mergeSort([10,24,76,73])</b><br />
<b>[10,24] merge [73,76]</b><br />
<b>mergeSort([10,24]) mergeSort([76,73])</b><br />
<b>[10] merge [24]     [76] merge [73]</b><br />
<b>mergeSort([10])  mergeSort([24])     mergeSort([76])  mergeSort([73])</b>
</p>

## Time Complexity of Merge Sort

| Time Complexity (Best)   | Time Complexity (Average)	| Time Complexity (Worst) | Space Complexity |
|          :---:           |          :---:             |         :---:           |       :---:      |
|     **O(n log n)**       |      **O(n log n)**        |      **O(n log n)**     |      **O(n)**    |
