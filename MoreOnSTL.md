# STL Algorithms and Methods

This section focuses on some useful algorithms dealing with containers in C++.  
*Note:* When "begin" is mentioned, it refers to container.begin() and similarly for "end".  
"Condition" refers to a function or functor that applies a specific condition used by the algorithm.  
For example:  
max_element(begin, end)  
If we have vector<int> v{1, 2, 3, 4, 5}, then it means max_element(v.begin(), v.end()), and the same applies to all other containers.

## Part 1: Algorithms and Methods

### Algorithms

1. **any_of(begin, end, condition)**
   - Returns true if any element in the range satisfies the condition.
  
2. **none_of(begin, end, condition)**
   - Returns true if none of the elements in the range satisfy the condition.
  
3. **all_of(begin, end, condition)**
   - Returns true if all elements in the range satisfy the condition.
  
4. **copy_n(begin, number_of_elements, destination(iterator))**
   - Copies the first number_of_elements elements from the range starting at begin to the destination iterator.
   - *Note:* The destination can be a back inserter using back_inserter(target). The target here is a container, and back_inserter() is a type of iterator that calls push_back on the target container.
  
5. **iota(begin, end, initial_val)**
   - Fills the range starting at begin with sequentially increasing values, starting from initial_val.
   - Example: If initial_val = 1, the range will be filled as 1, 2, 3, ... until end.
  
6. **equal(begin, end, corresponding_begin)**
   - Compares the range starting at begin with the range starting at corresponding_begin. If all elements are equal, returns true, otherwise returns false.

### Methods

1. **back_inserter(container)**
   - Creates an iterator that uses push_back to insert elements into the container.

## Part 2: Algorithms and Methods

### Algorithms

1. **max_element(begin, end)**
   - Returns an iterator pointing to the maximum element in the range.
  
2. **find(begin, end, value)**
   - Returns an iterator pointing to the first occurrence of value in the range. If value is not found, returns end.
  
3. **find_if(begin, end, condition)**
   - Returns an iterator pointing to the first element that satisfies the condition.
  
4. **find_if_not(begin, end, condition)**
   - Similar to find_if, but returns an iterator to the first element that does *not* satisfy the condition.
  
5. **replace(begin, end, value_to_be_replaced, value_that_will_replace)**
   - Replaces all occurrences of value_to_be_replaced with value_that_will_replace in the range.
  
6. **replace_if(begin, end, condition, value_that_will_replace)**
   - Replaces all elements that satisfy the condition with value_that_will_replace.
  
7. **search_n(begin, end, consecutive_value_repitition(n), value)**
   - Searches for a sequence of n consecutive occurrences of value in the range.
  
8. **search(begin, end, sub_begin, sub_end)**
   - Searches for the subsequence defined by [sub_begin, sub_end) in the main sequence [begin, end).

9. **for_each(begin, end, functor/function)**
   - Applies the given functor or function to each element in the range.  
   - *Key Differences Between Using a Functor and a Function:*
     - *Functor:* If you use a functor (a class or struct with an operator() method), std::for_each returns a copy of the functor after it has been applied to all elements. This can be useful if the functor maintains state (e.g., counting elements, accumulating a result, etc.) that you want to access after the operation.
     - *Function:* If you use a regular function, std::for_each returns a copy of the function (technically a function pointer), but since functions don't have state, the return value is usually ignored.

### Methods

1. **distance(iterator1, iterator2)**
   - Measures the distance between two iterators, returning the number of elements between them as an int.
