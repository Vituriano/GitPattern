## Getting started
1 - First, you need to init a git project:
```sh
git init
git remote add origin <url>
```
2 - Now, you will install the commitlint and the husky
```sh
yarn add @commitlint/{config-conventional,cli} -D
yarn add husky -D
```
3 - To lint commits before they are created you can use Husky's 'commit-msg' hook:
```json
{
  "husky": {
    "hooks": {
      "commit-msg": "commitlint -E HUSKY_GIT_PARAMS"
    }  
  }
}
```
4 - well, to use a interface for commits, you will use the commitizen. Install with the comand bellow:
```sh
yarn add commitizen -D
yarn commitizen init cz-conventional-changelog --yarn --dev --exact
```
5 - in package.json, add the line bellow in husky -> hooks:
```json
"prepare-commit-msg": "exec < /dev/tty && git cz --hook || true",
```