```
salvo@darkside:~/Work/Ross$ git log
```
<pre>
commit df5164033b12477cd4a63781ea5610629b0326f1 (HEAD -> master)
Author: salvo <salvo.cuccurullo@gmailcom>
Date:   Sun Jul 8 21:55:40 2018 +0200

    Commit 4

commit 671945c986a8a9f3db1da04d7b259cf5dccb1d5c
Author: salvo <salvo.cuccurullo@gmailcom>
Date:   Sun Jul 8 21:55:20 2018 +0200

    Commit 3

commit f2f853f273ca6199482d91b6fca39fa380623a62
Author: salvo <salvo.cuccurullo@gmailcom>
Date:   Sun Jul 8 21:54:50 2018 +0200

    Commit 2

commit d9864b05506ea048dc6d7e48004fa5ca338243e8
Author: salvo <salvo.cuccurullo@gmailcom>
Date:   Sun Jul 8 21:54:15 2018 +0200

    Commit 1
</pre>

```
salvo@darkside:~/Work/Ross$ git revert --no-commit HEAD~2..HEAD
```
Reverting using the range option: from HEAD to HEAD-2 (in this case also HEAD-2 only works)
The option --no-commit is used to avoid to create commits with commit log messages stating which commits have been reverted.
```
salvo@darkside:~/Work/Ross$ git status
```
<pre>
On branch master
You are currently reverting commit 671945c.
  (all conflicts fixed: run "git revert --continue")
  (use "git revert --abort" to cancel the revert operation)

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   file.py

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	README.md
</pre>
The file file.py is ready to be commited again but it has been reverted to commit 2
```
salvo@darkside:~/Work/Ross$ cat file.py 
```
<pre>
#st="COMMIT 1"
st="COMMIT 2"
print st
salvo@darkside:~/Work/Ross$
</pre>
