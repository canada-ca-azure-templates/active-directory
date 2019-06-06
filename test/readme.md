# Manually running validation

Manual execution of validation does like this:

Commit updates to dev branch then run:

```powershell
.\validate.ps1
```

If you want to keep the resources created during the validation to inspect them of troubleshoot issues run the validation with the following command:

```powershell
.\validate.ps1 -doNotCleanup
```

## Steps to merge dev branch commits in one commit to master and cleanup

```
git branch dev
git checkout dev
git add .
git commit -m "Commiting last changes in dev before merge"
git checkout master
git merge --squash dev
git commit -m "Updating validation process"
git push
git push origin :dev
git branch -D dev

```