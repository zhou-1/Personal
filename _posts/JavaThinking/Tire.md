# Tire     
Trie (we pronounce "try") or prefix tree is a tree data structure (rooted tree), which is used for retrieval of a key in a dataset of strings. There are various applications of this very efficient data structure such as: Autocomplete on search engine online; Spell checker; IP routing (Longest prefix matching), T9(text on 9 keys) predictive text, solving word games.       

There are several other data structures, like balanced trees and hash tables, which give us the possibility to search for a word in a dataset of strings. Then why do we need trie? Although hash table has O(1) time complexity for looking for a key, it is not efficient in the following operations: Finding all keys with a common prefix. Enumerating a dataset of strings in lexicographical order.     
Another reason why trie outperforms hash table, is that as hash table increases in size, there are lots of hash collisions and the search time complexity could deteriorate to O(n), where nn is the number of keys inserted. Trie could use less space compared to Hash Table when storing many keys with the same prefix. In this case using trie has only O(m) time complexity, where mm is the key length. Searching for a key in a balanced tree costs O(mlogn) time complexity.         






