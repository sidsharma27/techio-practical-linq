[//]: # (GENERATED FILE -- DO NOT EDIT)
# Methods: Calculating a single value

### SequenceEqual() method
The `SequenceEqual()` method takes a "second" `IEnumerable<T>` sequence as a parameter, and performs a comparison, element-by-element, with the target (first) sequence. If the two sequences contain the same number of elements, and each element in the first sequence is equal to the corresponding element in the second sequence (using the default equality comparer) then `SequenceEqual()` returns `true`.  Otherwise, `false` is returned.

It is interesting to note that this can be used to compare *any* two sequences! So, for example, a list and an array can be compared using this method. It can be quite handy sometimes. The only stipulation is that the datatype of the two sequences, `<T>`, must be the same.

```csharp
// returns true
bool isEqual1 = new[] { 1, 2, 3 }.SequenceEqual(new List<int> { 1, 2, 3 });
// returns false
bool isEqual2 = new List<int> { 1, 2, 3, 4 }.SequenceEqual(new[] { 1, 2, 3 });
// returns true
bool isEqual3 = new List<int> { 1, 2, 3, 4 }.Take(3).SequenceEqual(new[] { 1, 2, 3 });
// returns false
bool isEqual4 = new[] { 2, 1, 2 }.SequenceEqual(new[] { 1, 1, 2 });
// returns true
bool isEqual5 = new[] { 2, 1, 2 }.Skip(1).SequenceEqual(new[] { 1, 1, 2 }.Skip(1));
```

> **NOTE:** There is also another form of `SequenceEqual()` that takes an `IEqualityComparer<T>` comparer parameter to use instead of the default equality comparer.

### SequenceEqual() quiz
Based on this, which of the following would **both** compile correctly and return `true`?

?[Which statements would compile and return true?]
 - [ ] new[]{2}.SequenceEqual(2)
 - [x] new SortedSet&lt;int&gt;{1,2,4}.SequenceEqual(new[]{1,2,4})
 - [ ] new[]{2,5,2}.SequenceEqual(new[]{2,5,2,2})
 - [ ] new[]{1,1,1}.SequenceEqual(new[]{1,1})
 - [ ] new[]{"1","2","3"}.SequenceEqual(new[]{1,2,3})
 - [x] new List&lt;string&gt;{"a","b","abc"}.SequenceEqual(new[]{"a","b","abc"})
 - [ ] new[]{1,2}.SequenceEqual(new[]{1.0,2.0})