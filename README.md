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
3. The worst case is when there is no element such that `el === arr.length/2 -1`
4. The space-complexity is O(1), because we do not need to allocate any additional memory slots.
