# github_admin

## Merging distinct repos
Example merging 'duplicating_sequences' into the sperm_whales repo. First, make sure to record original URL in the repo-to-be-merged's README.md. Then, make sure to move every file into a subdirectory with the repo-to-be-merged's name (e.g. duplicating_sequences/README.md --> duplicating_sequences/duplicating_sequences/README.md)
```
git clone https://github.com/laninsky/sperm_whales.git
cd sperm_whales/
git remote add -f duplicating_sequences https://github.com/laninsky/duplicating_sequences.git
git merge duplicating_sequences/master --allow-unrelated-histories
git push https://github.com/laninsky/sperm_whales
```
After double-checking that the repo is now within sperm_whales, the original 'duplicating_sequences' repo can be deleted.

## Pulling in single files/folders from another repo
After experimenting with this, I found it easier to pull in whole repo and just delete what you don't need. Make sure there aren't any "top level" files (e.g. README.md) with the same names before starting.
```
git clone https://github.com/laninsky/beetles.git
cd beetles
git remote add -f project_logs https://github.com/laninsky/project_logs.git
git merge project_logs/master --allow-unrelated-histories
git rm -r chickadee # removing directories we are not interested in from project_logs
git rm -r harbour_seals
git rm -r hectors_hologenome
git rm -r lamprey
git rm -r penguin
git rm -r README.md # superflous README.md from project_logs
git mv README.mdbeetles README.md # Can move our "dummy named" repo README.md back to what it should be
git mv beetles downsampled_dataset # giving the 'beetles' subrepo a more useful name
git rm -r LICENSE
git commit -m "Removing extraneous stuff from project_logs"
git push https://github.com/laninsky/beetles
```
