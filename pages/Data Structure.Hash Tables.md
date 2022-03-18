title:: Data Structure/Hash Tables
alias:: 数据结构/哈希表

- **特征**
	- 直接通过 key 即可找到对应的 value
- **操作**
  一般复杂度为O(1)，最坏的情况为O(n)
	- search
	- insert
	- delete
- **解决哈希冲突**
  https://programmerah.com/hash-conflict-and-four-solutions-15712/
	- Separate Chaining(链地址)
	- Open Addressing(开放定址)
	- Re-hashing(再哈希)
	- Establish a public overflow area(建立公共溢出区)