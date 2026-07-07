Generic
- `List<T>`
	- ⇐ `vector<T>`
- `Map<K, V>`  
	- ⇐ `map<K,V>`
- `Set<T>`
	- ⇐ `set<T>`

특징
- Type Erasure
	- 런타임에 타입 정보가 존재하지 않음
	- `T t = new T();` // ❌ 런타임에 T가 뭔지 모름
	- [[Reflection]]
- primitive 불가
	- 대응되는 wrapper가 항상 존재: AutoBoxing



---
