
- GitHub: https://github.com/mirnovov/obsidian-homepage.git



### Git: [[../Git/커밋 탐색|커밋 탐색]]
전체 보기
```sh
git log --oneline --reverse
```

해당 커밋 상세 보기
```sh
git show <commit-hash>
```

해당 커밋으로 이동
명령어
```sh
git checkout <commit-hash>
```

-  결과(접기)
  ```sh
	Note: switching to 'd933'.
	
	You are in 'detached HEAD' state. You can look around, make experimental
	changes and commit them, and you can discard any commits you make in this
	state without impacting any branches by switching back to a branch.
	
	If you want to create a new branch to retain commits you create, you may
	do so (now or later) by using -c with the switch command. Example:
	
	  git switch -c <new-branch-name>
	
	Or undo this operation with:
	
	  git switch -
	
	Turn off this advice by setting config variable advice.detachedHead to false
	
	HEAD is now at d933c6d Initial commit
	```

