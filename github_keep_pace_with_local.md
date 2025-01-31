## 本地git与github同步

```shell
git remote add origin URL(仓库的URL)
git branch -M main//此命令将主分支更改为main
git push -u origin main//此命令确保我们本地分支和origin分支共享相对名称main
```

---

### 有新的内容的时候

直接全部提交之后再次push就可以了

```shell
git add .
git commit -m "refresh"
```


