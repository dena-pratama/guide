## [Trunk Based Development](https://dora.dev/capabilities/trunk-based-development/)

Main charachteristics of Trunk Based Development

- There's only one main branch, called the `main` (trunk) branch.
- Working branch should be created from the `main` branch and called `release` branch, `release/[feature-name]` or `release/[major.minor.fix]` branch.
- When releasing, always `tag` the merged commit on the main branch.

Initially
* create a new repository
* clone the newly created project local development machine `git clone git@[host_url.tld_alias]:[path/to-repo].git`

### Daily
#### Start your day with a main branch checkout
``` 
/> cd ~/path/to/project
~/path/to.project> git checkout main
```
#### Fetch & Pull the latest changes from the remote repository
```
~/path/to/project> git fetch && git pull
```
#### Create a new branch from the main branch for the new feature or bug fix
```
~/path/to/project> git checkout -b release/[feature-name]
// if there's a changes, in the main branch
```
#### Merge main
```
~/path/to/project> git merge main
// if there's conflict, resolve the conflicts
```
#### Make changes to the code
```
~/path/to/project> git add .
```
#### Commit the changes
```
~/path/to/project> git commit -m "commit message"
```

#### Start working

* Work on a small problem one at a time, and immediately commit as soon as you finish the work (commit often).
* Use meaningful and descriptive commit messages like[](https://cbea.ms/git-commit/)
    * start your commit message with a one word imperative verb (mood); `[ADD] | [FIX] | [MODIFY] | [REMOVE] | [REFACTOR]`
    * Followed by a space, and then short description of the commit.
* Push your finished work to the remote repository.
```
~/path/to/project> git push origin release/[feature-name]
```
* Create pull request, from the `release/[feature-name]` branch as the source to the `main` as the destinantion.
* Assign a reviewer to the pull request.
* Once the pull request is approved, merge the pull request with `--squash` option.
* Delete the `release/[feature-name]` branch.
* Tag the merged commit on the main branch, with semantic versioning.
[](https://semver.org/)
```
0.2.0 // udah ada 2 fitur masuk
0.2.1 // ketemu 14 error di fitur 2 
```