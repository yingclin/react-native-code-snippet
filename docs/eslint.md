# ESLint

## VSCode 相關設定

### node 套件
```
npm install -g eslint
```
### VSCode extension
[ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) by Dirk Baeumer

### 專案

#### 方法一

套用通用設定
```
npm install --save-dev eslint-config-rallycoding
```

.eslint.rc
```
{
  "extends": "rallycoding",
  "rules": {
    "arrow-body-style": 0 // 避免 arrow-body-style 警告
  }
}
```
