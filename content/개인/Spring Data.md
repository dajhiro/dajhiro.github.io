## Core Philosophy: The Repository Abstraction
The superpopwer of Spring Data
Instead of writing complex DAOs(Data Access Objects), you simply define an interface.

```java
public interface UserRepository extends CrudRepository<User, Long> {
	List<User> findByLastName(String lastName);
}
```


- Boilerplate Reduction
	- Standard CRUD operations
- Pagination and Sorting
- Transparent Auditing