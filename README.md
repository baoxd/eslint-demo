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




    
