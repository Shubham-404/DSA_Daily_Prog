## Q. All the elements of a sorted array appear twice, except one element that appears only once. Find that element in O(logn).
- Use the fact that all elements appear twice, except once. This indicates that the length of the array must be odd.
- Now choose whether to eliminate left part or the right part based on this fact, at each iteration.
- if mid is not the answer, ans must be either on the right of the left part.
- if mid is odd, each side must be odd in numbers, even if otherwise.
- now, based on above info, if the mid matches an element in either left or right, we have to cases.
- - mid is odd:
  - - mid matches its left element, ans is on right, left otherwise.
  - mid is even:
  - - mid matches its left element, ans is on left, right otherwise. 
