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

