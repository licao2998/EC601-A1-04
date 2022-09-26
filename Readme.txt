git@github.com:licao2998/myself.git
通过 创建新文件 或 上传现有文件开始。我们建议每个存储库都包含一个 README、 LICENSE和.gitignore。
git clone :克隆仓库
git pull :更新本地仓库

git branch :查看本地分支
git branch -r ：查看远程分支
git checkout -b sprdlinux5.15 origin/sprdlinux5.15  取远程分支并将其命名为
git branch -d sprdlinux5.15 删除某分支 -D 强制删除
git checkout . 放弃工作区全部修改
git checkout -- filename 放弃工作区中对某文件修改
git checkout sprdlinux5.15 切换到某分支

git log -p filename  显示某文件的修改历史

git format-patch ... -1 :用commit id生成补丁
git apply --check ...  测试是否可以打该patch
git am -s < ...  应用该补丁
git am --abort 放弃之前打补丁
git apply --reject ... 强制打patch,会有.rej的冲突文件
git add
git am --continue
git rebase : HEAD~4 数字表示改几次的修改

git stash 将修改放到暂存区,有没保存的修改，但需切换分支
git stash list 列出暂存区内容
git stash pop 将内容从暂存区放出来（暂存区内删除
git stash apply 将内容应用到当前目录（暂存区仍有
git stash clear 清除堆栈所有内容

git reset --hard commit id 回退版本

git cherry-pick 将一些提交复制到当前位置

git push git@github.com:licao2998/myself.git
git remote add origin git@github.com:licao2998/myself.git

make -k -f makeFind
 (-f 表示指定文件、
  -k  让make命令在发现错误时仍然继续执行，而不是在检测到第一个错误时就停下来、
  -n:它的作用是让make命令输出将要执行的操作步骤，而不真正执行这些操作）

pwd 知道当前所处目录
touch   创建文件（文件不存在时）  更新文件修改时间（文件存在时）
mv  移动命令
grep 'text' ./* -rin