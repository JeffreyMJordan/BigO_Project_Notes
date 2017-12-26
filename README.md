# BigO_Project_Notes

# Arrays
## Problem 1
```(ruby)
def add(a, b)
  if a > b
    return a + b
  end

  a - b
end
```
1. This algorithm's number of operations doesn't depend on any of its inputs.
2. The time-complexity is O(1).
3. There are no worst cases because the time complexity is O(1).
4. The space-complexity is O(1) also.

## Problem 2
```(ruby)
def print_arr_1(arr)
  arr.each do |el|
    puts el
  end
end
```
1. The number of operations needed scales linearly with the length of the array (arr.length == n)
2. The time-complexity is O(n).
3. There are no worst cases because no matter what, we must always iterate through every item in the array.
4. The space-complexity is O(1), because we do not need to allocate any additional memory slots.

## Problem 3
```(ruby)
def print_arr_2(arr)
  arr.each_with_index do |el, idx|
    break if idx == arr.length/2 - 1
    puts el
  end
end
```
1. The number of operations needed scales linearly with the length of the array (arr.length == n)
2. The time-complexity is O(n/2).
3. There is no worst case, because we must always iterate through half of the given array.
4. The space-complexity is O(1), because we do not need to allocate any additional memory slots.

## Problem 4
```(ruby)
def print_arr_3(arr)
  arr.each do |el|
    break if el == arr.length/2 - 1
    puts el
  end
end
```
1. The number of operations needed scales linearly with the length of the array (arr.length == n)
2. The time-complexity is O(n).
3. The worst case is when there is no element such that `el == arr.length/2 -1`
4. The space-complexity is O(1), because we do not need to allocate any additional memory slots.

## Problem 5
```(ruby)
def print_arr_4(arr)
  arr.each do |el|
    break if el == arr.length/2 - 1
    puts el
  end

  arr.each_with_index do |el, idx|
    puts el if idx % 3 == 0
  end

  puts arr.last
end
```
1. The number of operations needed scales linearly with the length of the array (arr.length == n)
2. The time-complexity is O(n).
3. The worst case is when there is no elements such that `el == arr.length/2 -1`.
4. The space-complexity is O(1), because we do not need to allocate any additional memory slots.

## Problem 6
```(ruby)
def search(arr, target)
  arr.each_with_index do |el, idx|
    return idx if el == target
  end
end
```
1. The number of operations needed scales linearly with the length of the array (arr.length == n)
2. The time-complexity is O(n).
3. The worst case is when the element we're searching for is at the very end of the array.
4. The space-complexity is O(1), because we do not need to allocate any additional memory slots.


## Problem 7
```(ruby)
def searchity_search(arr, target)
  results = []
  arr.each do |el|
    results << search(arr, target + el)
  end

  results  
end
```
1. The number of operations needed scales quadratically with the length of the array (arr.length == n)
2. The time-complexity is O(n^2).
3. The worst case is when the value of each `target + el` is always at the end of `arr`. (For example, we could have `target = 0` and `arr = [0,0,0,0,0,0]`, requiring us to iterate through all of `arr` each time we call `search`).
4. The space-complexity is O(n), because we need to define a new memory slot in `results` for each item in `arr`.

## Problem 8
```(ruby)
def searchity_search_2(arr, target)
  results = []
  arr.each do |el|
    results << search(arr, el)
  end

  results  
end
```
1. The number of operations needed scales quadratically with the length of the array (arr.length == n)
2. The time-complexity is O(n^2).
3. The worst case is when we're given an array with all unique elements, requiring us to iterate through all the preceding elements before `search` returns our target.
4. The space-complexity is O(n), because we need to define a new memory slot in `results` for each item in `arr`.

# Iterations 
## Problem 1
```(javascript)
let iterative_1 = (n, m) => {
  let notes = ["do", "rei", "mi", "fa", "so", "la", "ti", "do"];

  for (var i = 0; i < n; i++) {
    for (var j = 0; j < m; j++) {
      let position = (i+j) % 8;
      console.log(notes[position]);
    }
  }
}
```
1. The number of operations scales linearly with the size of n and m.
2. The time-complexity is O(nm).
3. There is no worst case because we must always perform nm operations.
4. The space-complexity is O(1), because we do not need to allocate any additional slots in memory.

## Problem 2
```(javascript)
let iterative_2 = (n) => {
  let notes = ["do", "rei", "mi", "fa", "so", "la", "ti", "do"];

  for (var i = 0; i < n; i++) {
    for (var j = i; j >= 0; j--) {
      let position = (i+j) % 8;
      console.log(notes[position]);
    }
  }
}
```
1. The number of operations needed scales quadratically with n.
2. The time-complexity is O(n^2).
3. There is no worst case scenario, because we our longest loop will always be O(n^2). 
4. The space-complexity is O(1), because we do not need to allocate any additional slots in memory.

## Problem 3
```(javascript)
let iterative_3 = (n, m) => {
  let notes = ["do", "rei", "mi", "fa", "so", "la", "ti", "do"];

  let bigger = n > m ? n : m;
  let smaller = n <= m ? n : m;

  for (var i = 0; i < smaller; i++) {
    for (var j = i; j < bigger; j++) {
      let position = (i+j) % 8;
      console.log(notes[position]);
    }
  }
}
```
1. The number of operations needed scales linearly with n and m.
2. The time-complexity is O(nm).
3. There is no worst case because we must always perform nm operations.
4. The space-complexity is O(1), because we do not need to allocate any additional slots in memory.

# Recursion
## Problem 1 
```(ruby)
def rec_mystery(n)
  return n if n < 5

  rec_mystery(n - 5)
end
```
1. The number of operations scales linearly with n. 
2. The time-complexity is O(n/5).
3. There is no worst case scenario because we will always need O(n/5) operations.
4. The space-complexity is O(n/5), because we need to create that many stack frames for a given n. 

## Problem 2
```(ruby)
def rec_mystery_2(n)
  return 0 if n == 0

  rec_mystery_2(n/5) + 1
end
```
1. The number of operations scales linearly with n. 
2. The time-complexity is O(n/5).
3. There is no worst case scenario because we will always need O(n/5) operations.
4. The space-complexity is O(n/5), because we need to create that many stack frames for a given n. 

## Problem 3
```(java)
void rec_mystery_3(int n, int m, int o)
{
  if (n <= 0)
  {
    printf("%d, %d\n", m, o);
  }
  else
  {
    rec_mystery_3(n-1, m+1, o);
    rec_mystery_3(n-1, m, o+1);
  }
}
```
1. The number of operations scales linearly with n. 
2. The time-complexity is O(n).
3. There is no worst case scenario because we will always need O(n) operations.
4. The space-complexity is O(n), because we need to create that many stack frames for a given n.

## Problem 4 
```(ruby)
class Array
  def grab_bag
    return [[]] if empty?
    bag = take(count - 1).grab_bag
    bag.concat(bag.map { |handful| handful + [last] })
  end
end
```
1. The number of operations scales factorially with count (count == n).
2. The time complexity is O(n!)
3. There is no worst case scenario because we will always need O(n!) operations.
4. The space-complexity is O(n!) because we need n! stack frames for each count == n.
