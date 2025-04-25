git remote: konfigurer eksterne repos. E.g. GitHub​

git fetch: opdater lokal kopi af remote branch​

git pull: fetch + checkout (evt. forsøg merge)​

git push: upload lokale commits til remote branch​

git clone: opret en lokal kopi af et remote repo

git diff: viser forskellen.

git checkout: Gå til en eller anden version eller branch (tror også den kan slette og oprette branches).
(kan også bruge git switch til at ændre hvilken branch man sidder i)

git stash: gemmer noget der er WIP (så du kan komme tilbage til det senere)
git stash list: viser ændringer
git stash show: viser hvilke filer der er blevet ændret i
git stash apply: sætter dit stash ind på der hvor du nu er så du kan fortsætte med det du var i gang med.

**git branch**: viser eller opretter branches
    - `git branch <branch-navn>` → opret en ny branch
    - `git branch -d <branch-navn>` → slet en branch
**git merge `<branch-navn>`**: fletter en branch ind i den nuværende branch
**git rebase `<branch-navn>`**: anvender ændringer fra en branch oven på en anden

- **git log**: viser commit-historikken
    - `git log --oneline --graph` → kortere visning med graf
- **git status**: viser ændringer i working directory
- **git add `<fil>`**: tilføjer filer til staging
- **git commit -m "besked"**: laver et commit
- **git commit --amend**: ændrer det sidste commit
- **git reset**: nulstiller commits
    - `git reset --soft HEAD~1` → fjerner sidste commit, men bevarer ændringer
    - `git reset --hard HEAD~1` → fjerner sidste commit + ændringer

- **git revert `<commit-id>`**: laver et nyt commit, der ophæver et gammelt
- **git checkout -- `<fil>`**: genskaber en fil fra sidste commit
- **git restore `<fil>`**: samme som `git checkout -- <fil>` (nyere Git-versioner)

- **git tag `<tag-navn>`**: opretter et tag (f.eks. til versioner)
- **git tag -a `<tag-navn>` -m "besked"**: opretter et annoteret tag

- **git remote -v**: viser konfigurerede remotes
- **git push --tags**: uploader tags til remote
- **git fetch --prune**: henter ændringer og fjerner slettede branches

- **git cherry-pick `<commit-id>`**: anvender et specifikt commit fra en anden branch
- **git bisect**: hjælper med at finde et fejlende commit ved binær søgning
- **git blame `<fil>`**: viser, hvem der har lavet ændringer i en fil
- git blame -L 10,20 `<file>`: specifikke linjer
- git blame -w `<file>`: (ignorer whitespace)
- git blame --author="Author Name" `<file>`: Se hvad en specifik aktør har lavet
- git blame -C `<file>`: (vis linjer fra bestemt commit)

