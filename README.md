# Group-Anagrams-Daily-Leetcode-Challenge
<h2>Given an array of strings strs, group the anagrams together. You can return the answer in any order.  An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.</h2>

![1_OathM0PWiIfPfFuJ3wv87A](https://github.com/albrran/Valid-Anagram-Daily-Leetcode-Challenge/assets/120284166/4d831238-d99d-4762-93b5-6311438f469d)

<h2>Example 1:</h2>
    <pre>
Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
    </pre>
    <h2>Example 2:</h2>
    <pre>
Input: strs = [""]
Output: [[""]]
    </pre>
    <h2>Example 3:</h2>
    <pre>
Input: strs = ["a"]
Output: [["a"]]
    </pre>
    <h2>Constraints:</h2>
    <pre>
1 &lt;= strs.length &lt;= 104
0 &lt;= strs[i].length &lt;= 100
strs[i] consists of lowercase English letters.
    </pre>
<h1>Solution 1: Hashmap</h1>
<h1>Explanation of Anagram Grouping Code</h1>
    <pre>
        <code>
class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        Map<String, List<String>> map = new HashMap<>();
        for(String word: strs) {
            char[] chars = word.toCharArray();
            Arrays.sort(chars);
            String sortedword = new String(chars);
            if(!map.containsKey(sortedword)) {
                map.put(sortedword, new ArrayList<>());
            }
            map.get(sortedword).add(word);
        }
        return new ArrayList<>(map.values());
    }
}
        </code>
    </pre>
    <h2>How the Code Works:</h2>
    <ol>
        <li><strong>Initialization:</strong> The code starts by creating an empty <code>HashMap</code> called <code>map</code>.</li>
        <li><strong>Iteration through Input Strings:</strong> It then loops through each string in the input array <code>strs</code> using a for-each loop.</li>
        <li><strong>Sorting Characters:</strong> Inside the loop, it converts each word into a character array, sorts it alphabetically, and creates a sorted word.</li>
        <li><strong>Checking for Anagrams:</strong> The code checks if the sorted word is already a key in the <code>map</code>. If not, it adds a new entry with the sorted word as the key.</li>
        <li><strong>Adding Words to Anagram Lists:</strong> After ensuring there's an entry for the sorted word, the original word is added to the corresponding list.</li>
        <li><strong>Return Grouped Anagrams:</strong> Finally, after processing all words, the code constructs a new list containing all the values (lists of anagrams) from the <code>map</code> and returns it.</li>
    </ol>
