## KMP ##

Pattern matching. Given text t[0...m-1] and pattern p[0...n-1], m >= n. Find the occurence of p in t.

### Definition of Proper Prefix String and Proper Suffix String ###

**Proper pefix string**: prefix string of s[0...n-1] is ps[0...j] where j < n - 1

**Proper suffix string**: suffix string of s[0...n-1] is ss[j...n-1] where j > 0


### Preprocessing ###

Use auxilary space to create match table lps.

lps[i] stores the longest proper prefix string which is also a proper suffix string of t[0..i]. 

E.g. 
proper prefix of "a" : null   
proper suffix of "a" : null 

|String|a|b|a|b|a|b|c|a|
|-|-|-|-|-|-|-|-|-|
|lps|0||||||||

proper prefix of "ab" : "a"   
proper suffix of "ab" : "b"

|String|a|b|a|b|a|b|c|a|
|-|-|-|-|-|-|-|-|-|
|lps|0|0|||||||

proper prefix of "aba": **"a"**, "ab"    
proper suffix of "aba": **"a"**, "ba"

|String|a|b|a|b|a|b|c|a|
|-|-|-|-|-|-|-|-|-|
|lps|0|0|1||||||

proper prefix of "abab": "a", **"ab"**, "aba"    
proper suffix of "abab": "a", **"ab"**, "bab"

|String|a|b|a|b|a|b|c|a|
|-|-|-|-|-|-|-|-|-|
|lps|0|0|1|2|||||

proper prefix of "ababa": "a", "ab", **"aba"**, "abab"    
proper suffix of "ababa": "a", "ba", **"aba"**, "baba"

|String|a|b|a|b|a|b|c|a|
|-|-|-|-|-|-|-|-|-|
|lps|0|0|1|2|3||||

proper prefix of "ababab": "a", "ab", "aba", **"abab"**, "ababa"      
proper suffix of "ababab": "b", "ab", "bab", **"abab"**, "babab"

|String|a|b|a|b|a|b|c|a|
|-|-|-|-|-|-|-|-|-|
|lps|0|0|1|2|3|4|||

proper prefix of "abababc": "a", "ab", "aba", "abab", "ababa", "ababab"        
proper suffix of "abababc": "c", "bc", "abc,  "babc", "ababc", "bababc"

|String|a|b|a|b|a|b|c|a|
|-|-|-|-|-|-|-|-|-|
|lps|0|0|1|2|3|4|0||

proper prefix of "abababca": **"a"**, "ab", "aba", "abab", "ababa", "ababab", "abababc"      
proper suffix of "abababca": **"a"**, "ca", "bca", "abca", "babca", "ababca", "bababca"

|String|a|b|a|b|a|b|c|a|
|-|-|-|-|-|-|-|-|-|
|lps|0|0|1|2|3|4|0|1|



