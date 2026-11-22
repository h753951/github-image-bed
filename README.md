# 408 + 数学二 题图 · GitHub 图床

就是一个 **public 仓库 + 两个图片文件夹**，完整镜像本地题库里的题目配图。

| 文件夹 | 数量 | 体积 |
| --- | ---: | ---: |
| `images/408/` | 137 张 | 约 2.73 MB |
| `images/math2/` | 29 张 | 约 0.32 MB |
| **合计** | **166 张** | **约 3.05 MB** |

## 预览

408（2024-11，外排序败者树）：

![408-2024-11](images/408/03818048370bb028cf3e4b20c83ab7d49182af0668979d420a80bb3df9eb6ed0.jpg)

数学二（2008-2）：

![math2-001](images/math2/math2_001.jpg)

## 外链格式

```text
https://raw.githubusercontent.com/h753951/github-image-bed/main/images/408/<文件名>.jpg
https://raw.githubusercontent.com/h753951/github-image-bed/main/images/math2/math2_001.jpg
```

例如：

```text
https://raw.githubusercontent.com/h753951/github-image-bed/main/images/408/03818048370bb028cf3e4b20c83ab7d49182af0668979d420a80bb3df9eb6ed0.jpg
```

Markdown：

```markdown
![408-2024-11](https://raw.githubusercontent.com/h753951/github-image-bed/main/images/408/03818048370bb028cf3e4b20c83ab7d49182af0668979d420a80bb3df9eb6ed0.jpg)
```

HTML：

```html
<img src="https://raw.githubusercontent.com/h753951/github-image-bed/main/images/408/03818048370bb028cf3e4b20c83ab7d49182af0668979d420a80bb3df9eb6ed0.jpg" alt="408-2024-11">
```

在 408 题库数据里替换时，只换括号里的路径：

```text
改前：![image](题目图片/03818048370bb028cf3e4b20c83ab7d49182af0668979d420a80bb3df9eb6ed0.jpg)

改后：![image](https://raw.githubusercontent.com/h753951/github-image-bed/main/images/408/03818048370bb028cf3e4b20c83ab7d49182af0668979d420a80bb3df9eb6ed0.jpg)
```

数学二同理，文件名 `math2_001.jpg` 不变，只换前缀。

## 按题号查图

GitHub 只是静态文件托管，本身**不能按题号搜索图片**；408 的文件名又是哈希，直接看看不出来。
所以根目录附了一份 [`题号索引.csv`](题号索引.csv)：

- 408：114 道题、145 条图片引用；
- 数学二：21 道题、29 条图片引用；
- 列：`project,question_id,file,url`，一个题有多张图就有多行。

用法一：用 Excel / VSCode / 记事本打开，`Ctrl+F` 搜题号。

用法二：PowerShell 里直接筛：

```powershell
Import-Csv .\题号索引.csv | Where-Object { $_.question_id -eq '2024-11' }
```

输出里的 `url` 列就是可以直接用的 raw 链接。

## 文件名说明

- `images/408/`：137 张，文件名沿用原题库的 64 位内容哈希，和 408 题库里的
  `题目图片/<hash>.jpg` 一一对应。以后把题库改成图床链接时，直接换前缀即可，不需要改文件名。
- `images/math2/`：29 张，文件名为 `math2_001.jpg` ~ `math2_029.jpg`，和数学二题库里的
  `题目图片/math2_xxx.jpg` 一一对应。

## 更新

图片有增删时，在本地替换 `images/` 下对应文件，然后：

```powershell
cd D:\my_projects\github-image-bed
git add -A
git commit -m "Update question images"
git push
```

## 注意

- 仓库是 **public**，raw 链接才能匿名访问。
- GitHub 单文件上限 100 MB，这些图都很小。
- 不要用 Git LFS，raw 只会返回指针文本，不是图片。
- raw 有约 5 分钟缓存，刚 push 完看不到新图是正常的。
- 真题图片版权归原权利人，这里只做个人学习和技术测试。
