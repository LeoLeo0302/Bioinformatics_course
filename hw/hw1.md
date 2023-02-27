## Getting started
[The homepage of Zhiyan Liao](https://github.com/LeoLeo0302)

## Linux-basic command
### 0. 把文件共享给 Docker 里面的 Linux
mv test_command.gtf ~/Desktop/bioinformatics/bioinf_tsinghua_share/
docker exec -it zhiyanliao bash
cp share/test_command.gtf linux/
cd linux

### 1.统计文件的行数以及字符数
wc -l -c test_command.gtf

### 2.尝试筛选并输出示例文件中以 chr_ 起始，并且基因id为YDL248W的行
grep 'chr_' test_command.gtf|grep 'YDL248W'

### 3.将示例文件中的 chr_ 替换为 chromosome_ 并输出每行的第1，3，4，5列。
sed 's/chr_/chromosome_/g' test_command.gtf|cut -f '1,3,4,5'

### 4.互换示例文件的第2列和第3列，并且对输出结果利用 sort 命令依照第4和第5列数字大小排序，将最终结果输出到result.gtf文件中
awk -F $'\t' '{t = $2; $2 = $3; $3 = t; print; } ' OFS=$'\t' test_command.gtf|sort -k '4,5' > result.gtf

### 5.更改示例文件的权限，使得文件所有者及所在用户组用户可读、写、执行而其他用户只可读，展示权限修改前后的权限变化
ls -hl
chmod ug=rwx,o=r test_command.gtf
ls -hl

