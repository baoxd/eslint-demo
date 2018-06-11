## 有两种方式进行代码git提交前的语法检查
    
* husky
* pre-commit

## 使用husky

1. 安装依赖

```
npm i husky -D
```

2. 修改 package.json，增加配置

```
{
  "scripts": {
    "precommit": "eslint src/**/*.js"
  }
}
```

3. 尝试Git提交，会收到提交信息

```
git commit -m "husky test"
```

## 在旧项目中使用husky，会导致旧项目报海量的错误，该怎么办？

可以使用lint-staged解决问题，每次提交只检查本次提交所修改的文件, 其中 staged 是 Git 里面的概念，指待提交区,
使用 git commit -a，或者先 git add 然后 git commit 的时候，你的修改代码都会经过待提交区


lint-staged 用法如下:

1. 安装依赖

```
npm i lint-staged -D
```

2. 修改 package.json 配置

```
"scripts": {
    "precommit": "lint-staged"
},
"lint-staged": {
    "src/**/*.js": "eslint"
}
```

lint-staged 给了你提交前代码操作的更大自由度，比如使用下面的配置，自动修复错误

```
"scripts": {
    "precommit": "lint-staged"
},
"lint-staged": {
    "src/**/*.js": ["eslint --fix", "git add"]
}
```

或者使用下面的配置，自动格式化代码

```
{
  "scripts": {
    "precommit": "lint-staged"
  },
  "lint-staged": {
    "src/**/*.js": ["prettier --write", "git add"]
  }
}
```









    
