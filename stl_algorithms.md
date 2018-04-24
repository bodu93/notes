##input-iterator | output-iterator > forward-iterator > bidirectional-iterator > random-access-iterator

####NonModifying Algorithms \<algorithm>

```c++
difference_type count(InputIterator beg, InputIterator end, const T& value)
difference_type count_if(InputIterator beg, InputIterator end, UnaryPredicate op)

ForwardIterator min_element(ForwardIterator beg, ForwardIterator end)
ForwardIterator min_element(ForwardIterator beg, ForwardIterator end, CompFunc op)

ForwardIterator max_element(ForwardIterator beg, ForwardIterator end)
ForwardIterator max_element(ForwardIterator beg, ForwardIterator end, CompFunc op)

std::pair<ForwardIterator, ForwardIterator> minmax_element(ForwardIterator beg, ForwardIterator end)
std::pair<ForwardIterator, ForwardIterator> minmax_element(ForwardIterator beg, ForwardIterator end, CompFunc op)
  
InputIterator find(InputIterator beg, InputIterator end, const T& value)
InputIterator find_if(InputIterator beg, InputIterator end, UnaryPredicate op)
InputIterator find_if_not(InputIterator beg, InputIterator end, UnaryPredicate op)

ForwardIterator search_n(ForwardIterator beg, ForwardIterator end, Size count, const T& value)
ForwardIterator search_n(ForwardIterator beg, ForwardIterator end, Size count, const T& value, BinaryPredicate op)

ForwardIterator1 search(ForwardIterator1 beg, ForwardIterator1 end, ForwardIterator2 searchBeg, ForwardIterator2 searchEnd)
ForwardIterator1 search(ForwardIterator1 beg, ForwardIterator1 end, ForwardIterator2 searchBeg, ForwardIterator2 searchEnd, BinaryPredicate op)

ForwardIterator1 find_end(ForwardIterator1 beg, ForwardIterator1 end, ForwardIterator2 searchBeg, ForwardIterator2 searchEnd)
ForwardIterator1 find_end(ForwardIterator1 beg, ForwardIterator1 end, ForwardIterator2 searchBeg, ForwardIterator2 searchEnd, BinaryPredicate op)

InputIterator find_first_of(InputIterator beg, InputIterator end, ForwardIterator searchBeg, ForwardIterator searchEnd)
InputIterator find_first_of(InputIterator beg, InputIterator end, ForwardIterator searchBeg, ForwardIterator searchEnd, BinaryPredicate op)

ForwardIterator adjacent_find(ForwardIterator beg, ForwardIterator end)
ForwardIterator adjacent_find(ForwardIterator beg, ForwardIterator end, BinaryPredicate op)

bool equal(InputIterator1 beg, InputIterator1 end, InputIterator2 cmpBeg)
bool equal(InputIterator1 beg, InputIterator1 end, InputIterator2 cmpBeg, BinaryPredicate op)

bool is_permutation(ForwardIterator1 beg1, ForwardIterator1 end1, ForwardIterator2 beg2)
bool is_permutation(ForwardIterator1 beg1, ForwardIterator1 end1, ForwardIterator2 beg2, CompFunc op)

std::pair<InputIterator1, InputIterator2> mismatch(InputIterator1 beg, InputIterator1 end, InputIterator2 cmpBeg)
std::pair<InputIterator1, InputIterator2> mismatch(InputIterator1 beg, InputIterator1 end, InputIterator2 cmpBeg, BinaryPredicate op)

bool lexicographical_compare(InputIterator1 beg1, InputIterator1 end1, InputIterator2 beg2, InputIterator2 end2)
bool lexicographical_compare(InputIterator1 beg1, InputIterator1 end1, InputIterator2 beg2, InputIterator2 end2, CompFunc op)

bool is_sorted(ForwardIterator beg, ForwardIterator end)
bool is_sorted(ForwardIterator beg, ForwardIterator end, BinaryPredicate op)

ForwardIterator is_sorted_util(ForwardIterator beg, ForwardIterator end)
ForwardIterator is_sorted_util(ForwardIterator beg, ForwardIterator end, BinaryPredicate op)

bool is_partitioned(InputIterator beg, InputIterator end, UnaryPredicate op)

ForwardIterator partition_point(InputIterator beg, InputIterator end, BinaryPredicate op)

bool is_heap(RandomAccessIterator beg, RandomAccessIterator end)
bool is_heap(RandomAccessIterator beg, RandomAccessIterator end, BinaryPredicate op)

RandomAccessIterator is_heap_util(RandomAccessIterator beg, RandomAccessIterator end)
RandomAccessIterator is_heap_util(RandomAccessIterator beg, RandomAccessIterator end, BinaryPredicate op)
  
bool all_of(InputIterator beg, InputIterator end, UnaryPredicate op)
bool any_of(InputIterator beg, InputIterator end, UnaryPredicate op)
bool none_of(InputIterator beg, InputIterator end, UnaryPredicate op)
```



####Modifying Algorithms \<algorithm>

```c++
OutputIterator copy(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg)
OutputIterator copy_if(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg, UnaryPredicate op)
BidirectionalIterator2 copy_backward(BidirectionalIteartor1 sourceBeg, BidirectionalIteartor1 sourceEnd, BidirectionalIterator2 destEnd)

OutputIterator move(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg)
BidirectionalIterator2 move_backward(BidirectionalIterator1 sourceBeg, BidirectionalIterator1 sourceEnd, BidirectionalIterator2 destEnd)

OutputIterator transform(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg, UnaryFunc op)
OutputIterator transform(InputIterator1 source1Beg, InputIterator1 source1End, InputIterator2 source2Beg, OutputIterator destBeg, BinaryFunc op)

ForwardIterator2 swap_ranges(ForwardIterator1 beg1, ForwardIterator1 end1, ForwardIterator2 beg2)

void fill(ForwardIterator beg, ForwardIterator end, const T& newValue)
void fill_n(OutputIterator beg, Size num, const T& newValue)

void generate(ForwardIterator beg, ForwardIterator end, Func op)
void generate_n(OutputIterator beg, Size num, Func op)

void iota(ForwardIterator beg, ForwardIterator end, T startValue)

void replace(ForwardIterator beg, ForwardIterator end, const T& oldValue, const T& newValue)
void replace_if(ForwardIterator beg, ForwardIterator end, UnaryPredicate op, const T& newValue)

OutputIterator replace_copy(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg, const T& oldValue, const T& newValue)
OutputIterator replace_copy_if(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg, UnaryPredicate op, const T& newValue)
```



####Removing Algorithms \<algorithm>

```c++
ForwardIterator remove(ForwardIterator beg, ForwardIterator end, const T& value)
ForwardIterator remove_if(ForwardIterator beg, ForwardIterator end, UnaryPredicate op)
OutputIterator remove_copy(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg, const T& value)
OutputIterator remove_copy_if(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg, UnaryPredicate op)

ForwardIterator unique(ForwardIterator beg, ForwardIterator end)
ForwardIterator unique(ForwardIterator beg, ForwardIterator end, BinaryPredicate op)

OutputIterator unique_copy(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg)
OutputIterator unique_copy(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg, BinaryPredicate op)
```



####Mutaing Algorithms \<algorithm>

```cpp
void reverse(BidirectionalIterator beg, BidirectionalIterator end)
OutputIterator reverse_copy(BidirectionalIterator sourceBeg, BidirectionalIterator sourceEnd, OutputIterator destBeg)

ForwardIterator rotate(ForwardIterator beg, ForwardIterator newBeg, ForwardIterator end)
OutputIterator rotate_copy(ForwardIterator sourceBeg, ForwardIterator newBeg, ForwardIterator sourceEnd, OutputIterator destBeg)
  
bool next_permutation(BidirectionalIterator beg, BidirectionalIterator end)
bool next_permutation(BidirectionalIterator beg, BidirectionalIterator end, BinaryPredication op)

bool prev_premutation(BidirectionalIterator beg, BidirectionalIterator end)
bool prev_premutation(BidirectionalIterator beg, BidirectionalIterator end, BinaryPredication op)

void shuffle(RandomAccessIterator beg, RandomAccessIterator end, UniformRandomNumberGenerator&&
eng)
void random_shuffle(RandomAccessIterator beg, RandomAccessIterator end)
void random_shuffle(RandomAccessIterator beg, RandomAccessIterator end, RandomFunc&& op)

ForwardIterator partition(ForwardIterator beg, ForwardIterator end, UnaryPredicate op)
BidirectionalIterator stable_partition(BidirectionalIterator beg, BidirectionalIterator end, UnaryPredicate op)

std::pair<OutputIterator1, OutputIterator2> partional_copy(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator1 destTrueBeg, OutputIterator2 destFalseBeg, UnaryPredicate op)
```



####Sorting Algorithms \<algorithm>

```c++
void sort(RandomAccessIterator beg, RandomIterator end)
void sort(RandomAccessIterator beg, RandomIterator end, BinaryPredicate op)

void stable_sort(RandomAccessIterator beg, RandomAccessIterator end)
void stable_sort(RandomAccessIterator beg, RandomAccessIterator end, BinaryPredicate op)

void partial_sort(RandomAccessIterator beg, RandomAccessIterator sortEnd, RandomAccessIterator end)
void partial_sort(RandomAccessIterator beg, RandomAccessIterator sortEnd, RandomAccessIterator end, BinaryPredicate op)

RandomAccessIterator partial_sort_copy(InputIterator sourceBeg, InputIterator sourceEnd, RandomAccessIterator destBeg, RandomAccessIterator destEnd)
RandomAccessIterator partial_sort_copy(InputIterator sourceBeg, InputIterator sourceEnd, RandomAccessIterator destBeg, RandomAccessIterator destEnd, BinaryPredicate op)

void nth_element(RandomAccessIterator beg, RandomAccessIterator nth, RandomAccessIterator end)
void nth_element(RandomAccessIterator beg, RandomAccessIterator nth, RandomAccessIterator end, BinaryPredicate op)

void make_heap(RandomAccessIterator beg, RandomAccessIterator end)
void make_heap(RandomAccessIterator beg, RandomAccessIterator end, BinaryPredicate op)

void push_heap(RandomAccessIterator beg, RandomAccessIterator end)
void push_heap(RandomAccessIterator beg, RandomAccessIterator end, BinaryPredicate op)

void pop_heap(RandomAccessIterator beg, RandomAccessIterator end)
void pop_heap(RandomAccessIterator beg, RandomAccessIterator end, BinaryPredicate op)

```



####Sorted-Range Algorithms \<algorithm>

```c++
bool binary_search(ForwardIterator beg, ForwardIterator end, const T& value)
bool binary_search(ForwardIterator beg, ForwardIterator end, const T& value, BinaryPredicate op)

bool includes(InputIterator1 beg, InputIterator1 end, InputIterator2 searchBeg, InputIterator2 searchEnd)
bool includes(InputIterator1 beg, InputIterator1 end, InputIterator2 searchBeg, InputIterator2 searchEnd, BinaryPredicate op)

ForwardIterator lower_bound(ForwardIterator beg, ForwardIterator end, const T& value)
ForwardIterator lower_bound(ForwardIterator beg, ForwardIterator end, const T& value, BinaryPredicate op)

ForwardIterator upper_bound(ForwardIterator beg, ForwardIterator end, const T& value)
ForwardIterator upper_bound(ForwardIterator beg, ForwardIterator end, const T& value, BinaryPredicate op)

std::pair<ForwardIterator, ForwardIterator> equal_range(ForwardIterator beg, ForwardIterator end, const T& value)
std::pair<ForwardIterator, ForwardIterator> equal_range(ForwardIterator beg, ForwardIterator end, const T& value, BinaryPredicate op)

OutputIterator merge(InputIterator source1Beg, InputIterator source1End, InputIterator source2Beg, InputIterator source2End, OutputIterator destBeg)
OutputIterator merge(InputIterator source1Beg, InputIterator source1End, InputIterator source2Beg, InputIterator source2End, OutputIterator destBeg, BinaryPredicate op)

OutputIterator set_union(InputIterator source1Beg, InputIterator source1End, InputIterator source2Beg, InputIterator source2End, OutputIterator destBeg)
OutputIterator set_union(InputIterator source1Beg, InputIterator source1End, InputIterator source2Beg, InputIterator source2End, OutputIterator destBeg, BinaryPredicate op)

OutputIterator set_difference(InputIterator source1Beg, InputIterator source1End, InputIterator source2Beg, InputIterator source2End, OutputIterator destBeg)
OutputIterator set_difference(InputIterator source1Beg, InputIterator source1End, InputIterator source2Beg, InputIterator source2End, OutputIterator destBeg, BinaryPredicate op)

OutputIterator set_symmetric_difference(InputIterator source1Beg, InputIterator source1End, InputIterator source2Beg, InputIterator source2End, OutputIterator destBeg)
OutputIterator set_symmetric_difference(InputIterator source1Beg, InputIterator source1End, InputIterator source2Beg, InputIterator source2End, OutputIterator destBeg, BinaryPredicate op)

void inplace_merge(BidirectionalIterator beg1, BidirectionalIterator end1beg2, BidirectionalIterator end2)
void inplace_merge(BidirectionalIterator beg1, BidirectionalIterator end1beg2, BidirectionalIterator end2, BinaryPredication op)
```



####Numeric Algorithms \<numeric>

```c++
T accumulate(InputIterator beg, InputIterator end, T initValue);
T accumulate(InputIterator beg, InputIterator end, T initValue, BinaryFunc op);

T inner_product(InputIterator1 beg1, InputIterator1 end1, InputIterator2 beg2, InputIterator2 end2, T initValue);
T inner_product(InputIterator1 beg1, InputIterator1 end1, InputIterator2 beg2, InputIterator2 end2, T initValue, BinaryFunc op1, BinaryFunc op2);

OutputIterator partial_sum(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg);
OutputIterator partial_sum(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg, BinaryFunc op);

OutputIterator adjacent_difference(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg);
OutputIterator adjacent_difference(InputIterator sourceBeg, InputIterator sourceEnd, OutputIterator destBeg, BinaryFunc op);
```

