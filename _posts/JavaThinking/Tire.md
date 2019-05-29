# Tire     
Trie (we pronounce "try") or prefix tree is a tree data structure (rooted tree), which is used for retrieval of a key in a dataset of strings. There are various applications of this very efficient data structure such as: Autocomplete on search engine online; Spell checker; IP routing (Longest prefix matching), T9(text on 9 keys) predictive text, solving word games.       

There are several other data structures, like balanced trees and hash tables, which give us the possibility to search for a word in a dataset of strings. Then why do we need trie? Although hash table has O(1) time complexity for looking for a key, it is not efficient in the following operations: Finding all keys with a common prefix. Enumerating a dataset of strings in lexicographical order.     
Another reason why trie outperforms hash table, is that as hash table increases in size, there are lots of hash collisions and the search time complexity could deteriorate to O(n), where nn is the number of keys inserted. Trie could use less space compared to Hash Table when storing many keys with the same prefix. In this case using trie has only O(m) time complexity, where mm is the key length. Searching for a key in a balanced tree costs O(mlogn) time complexity.         

## Insertion of a key to a trie     
We insert a key by searching into the trie. We start from the root and search a link, which corresponds to the first key character. There are two cases:     
A link exists. Then we move down the tree following the link to the next child level. The algorithm continues with searching for the next key character.       
A link does not exist. Then we create a new node and link it with the parent's link matching the current key character. We repeat this step until we encounter the last character of the key, then we mark the current node as an end node and the algorithm finishes.      

字典树（Trie）可以保存一些字符串->值的对应关系。基本上，它跟 Java 的 HashMap 功能相同，都是 key-value 映射，只不过 Trie 的 key 只能是字符串。     

    class Trie {
     private TrieNode root;

     public Trie() {
        root = new TrieNode();
     }

     // Inserts a word into the trie.
     public void insert(String word) {
        TrieNode node = root;
        for (int i = 0; i < word.length(); i++) {
            char currentChar = word.charAt(i);
            if (!node.containsKey(currentChar)) {
                node.put(currentChar, new TrieNode());
            }
            node = node.get(currentChar);
        }
        node.setEnd();
     }
    }

Time complexity : O(m), where m is the key length.         
Space complexity : O(m).       

## Search for a key in a trie     
Each key is represented in the trie as a path from the root to the internal node or leaf. We start from the root with the first key character. We examine the current node for a link corresponding to the key character. There are two cases:     
A link exist. We move to the next node in the path following this link, and proceed searching for the next key character.      
A link does not exist. If there are no available key characters and current node is marked as isEnd we return true. Otherwise there are possible two cases in each of them we return false:      
There are key characters left, but it is impossible to follow the key path in the trie, and the key is missing;     
No key characters left, but current node is not marked as isEnd. Therefore the search key is only a prefix of another key in the trie.       















