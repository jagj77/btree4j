btree4j: Disk-based Prefix B+-tree written in Pure Java
======================================================= 
[![License](http://img.shields.io/:license-Apache_v2-blue.svg)](https://github.com/myui/btree4j/blob/master/LICENSE)

This software is originally developed for [XBird](https://github.com/myui/xbird/) based on [Apache Xindice](https://xml.apache.org/xindice/). 

# Features and Strength

Applied many improvements over the original Xindice's implements as follows:

* Implementes [Prefix B+-tree](https://dl.acm.org/citation.cfm?id=320530) in which prefixes are selected carefully to minimize their length.

> _Rudolf Bayer and Karl Unterauer. "Prefix B-trees", Proc. ACM Trans. Database Syst. 2, 1, pp.11-26), March 1977._ [[DOI](https://doi.org/10.1145/320521.320530 )]

* Pointers are [compressed](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/utils/codec/VariableByteCodec.java) using [Variable Byte Codes](https://en.wikipedia.org/wiki/Variable-length_code) so that more keys/values are fit in memory.

* Support both unique and non-unique indexing. Storing duplicate keys is allowed for non-unique indexing.

* [Index file](https://en.wikipedia.org/wiki/Indexed_file) based on B+-tree is [supported](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/BIndexFile.java). [Multiple values per a key](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/BIndexMultiValueFile.java) is also supported.

* Support variable-length [key](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/Key.java)/[value](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/Value.java)

* [Prefix and range search](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/indexer/BasicIndexQuery.java) is supported in addition to exact match using a [flexible callback handler](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/BTreeCallback.java). Support [LIKE match](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/indexer/LikeIndexQuery.java) using wildcards.

* Paging (virtual memory) support using [LRU cache replacement policy](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/BTree.java) and [Freespace management](https://github.com/myui/btree4j/blob/master/src/main/java/btree4j/FreeList.java).

* Minimum dependencies to external libraries
