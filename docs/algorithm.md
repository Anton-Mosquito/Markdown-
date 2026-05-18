# Linear Search Algorithm

Linear Search is a simple searching algorithm used to find a target element in an array or list. The algorithm checks each element sequentially until the required value is found or the end of the collection is reached.

The main idea of Linear Search is straightforward: compare the target value $x$ with every element of the array one by one. If a match is found, the algorithm returns the index of the element. Otherwise, it returns $-1$.

For an array of size $n$, the algorithm may need to perform up to $n$ comparisons in the worst case.

## Algorithm Steps

1. Start from the first element of the array.
2. Compare the current element with the target value.
3. If the element matches, return its index.
4. Otherwise, move to the next element.
5. Repeat the process until the element is found or the array ends.

## Mathematical Representation

The search operation can be represented as:

$$
f(x) =
\begin{cases}
i, & \text{if } arr[i] = x \\
-1, & \text{if the element is not found}
\end{cases}
$$

The average number of comparisons can be estimated using the formula:

$$
\frac{\sum_{i=1}^{n} i}{n}
$$

In some cases, the performance analysis may also involve expressions such as $\sqrt{n}$ when comparing algorithmic efficiency with more advanced methods.

## Time Complexity

- Best Case: $O(1)$ — when the target element is at the beginning.
- Worst Case: $O(n)$ — when the element is at the end or absent.
- Average Case: $O(n)$.

## Advantages

- Easy to understand and implement.
- Works with both sorted and unsorted data.
- Requires no extra memory.

## Disadvantages

- Inefficient for large datasets.
- Slower compared to Binary Search for sorted arrays.

## Example

Given the array:

```text
[10, 20, 30, 40, 50]
If we search for the value 30, the algorithm checks:

10 != 30
20 != 30
30 == 30

Therefore, the element is found at index 2.

Conclusion

Linear Search is one of the simplest searching algorithms and is suitable for small or unsorted datasets. Although it is not optimal for large collections, it remains an important foundational algorithm in computer science.
```
