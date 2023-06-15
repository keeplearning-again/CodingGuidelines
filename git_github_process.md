# Github工作流

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
  - 由于本地系统设置，如果在VSCode上的terminal运行的话，在commit的时候会弹出一个窗口，
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
