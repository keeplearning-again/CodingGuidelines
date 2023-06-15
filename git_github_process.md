# Github工作流
## 针对打算做一个新的repo或是第一次运行
- 第一步 在远端先fork一个别人的仓库
- 第二步 找到自己fork的仓库再git clone到本地和disk
  > `git clone .git`
- 第三步 在本地git上创建一个新的分支 
  > `git checkout -b my-feature`
- 第四步 在本地上进行修改（在my-feature分支上）
- 第五步 将改动提交到本地my-feature
  > `git diff`
  > `git add .`
  > `git commit`
  - 由于本地系统设置，如果在VSCode上的terminal运行的话，在commit的时候会弹出一个窗口
  - ![image-20230615162307000](https://raw.githubusercontent.com/keeplearning-again/Typora_blog_images/main/blog/202306151623188.png)
  - 这个时候的操作步骤是 
    - 键盘上在英文状态输入`i` 
    - 找到修改或是新建文件所在位置 然后将那一行前面的 `#` 删除
    - 按`Esc`
    - 大写的`ZZ`
- 第六步 将本地改动推送到远端 
  > `git push origin  my-feature`
- 第七步 假设同时远端有更新，所以就要先看看会不会冲突(optional)
  - 7.1 更新本地最新的main
    > `git checkout main`
    > `git pull origin master`
  - 7.2 将改动叠加
    > `git checkout my-feature`
    > `git rebase main`
    > `git push -f origin my-feature`
- 第八步 在远端 pull request & square and merge
- 第九步 保证与远端最新版一致 
  - 在远端delete my-feature branch
    > `git checkout main`
    > `git branch -D my-feature`
    > `git pull origin master`

## 针对已经完成第一次的文件夹
- 懒得继续搞新的branch+且对自己的代码很自信 -- 那么就直接在main上面修改
  - 在VSCode里面修改 
  - 添加到git本地端
    - `git add .`
    - ![git add](https://raw.githubusercontent.com/keeplearning-again/Typora_blog_images/main/blog/202306151736500.png) 
  - commit & push
    - 记得加上message
    - ![git插件push](https://raw.githubusercontent.com/keeplearning-again/Typora_blog_images/main/blog/202306151738672.png)