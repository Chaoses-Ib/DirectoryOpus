# SetAttr
## 设置扩展属性
### 设置描述
```cmd
SetAttr DESCRIPTION "描述"
```
或
```cmd
SetAttr META "comment:描述"
```

### 设置标签
```cmd
SetAttr META tags:风景;夕阳
```
可通过 `+` `-` 来表示增减标签，例如 `tags:+风景;-夕阳` 表示增加 `风景` 标签，移除 `夕阳` 标签。

### 设置评分
```cmd
SetAttr META rating:5
```