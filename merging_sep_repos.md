# github_admin

Example merging 'duplicating_sequences' into the sperm_whales repo. First, make sure to record original URL in the repo-to-be-merged's README.md. Then, make sure to move every file into a subdirectory with the repo-to-be-merged's name (e.g. duplicating_sequences/README.md --> duplicating_sequences/duplicating_sequences/README.md)
```
git clone https://github.com/laninsky/sperm_whales.git
cd sperm_whales/
git remote add -f duplicating_sequences https://github.com/laninsky/duplicating_sequences.git
git merge duplicating_sequences/master --allow-unrelated-histories
git push https://github.com/laninsky/sperm_whales
```
After double-checking that the repo is now within sperm_whales, the original 'duplicating_sequences' repo can be deleted.
