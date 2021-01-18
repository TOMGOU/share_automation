### gitbook使用步骤
##### Step-1: 创建github仓库
##### Step-2: 克隆github仓库

```
git clone git@github.com:TOMGOU/share_automation.git
```
##### Step-3: 进入项目并初始化

```
// npm初始化
nmp init -y

// gitbook初始化
gitbook init
```
##### Step-4: 创建自动化发布shell脚本git.sh

```
cd _book
git init
git add .
git commit -m 'update'
git push -f git@github.com:<USERNAME>/<REPO>.git master:gh-pages
cd ../
```
**用户名：USERNAME = TOMGOU**

**仓库名：REPO = share_automation**

##### Step-5: 修改package.json

```
"scripts": {
    "gh-pages": "./git.sh"
},
```
##### Step-6: 本地编辑

```
gitbook init
gitbook serve
```
- Step-7: github发布

```
npm run gh-pages
```
**页面地址：https://tomgou.github.io/share_automation/**

### 这样使用gitbook的好处
- 不暴露源码（只要不push主分支）
- 及时预览：gitbook serve 
- 及时发布：npm run gh-pages