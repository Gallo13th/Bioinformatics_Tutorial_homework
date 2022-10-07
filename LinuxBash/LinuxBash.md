# Linux Bash

## Task
写出一个 bash 脚本，可以使它自动读取一个文件夹（例如bash_homework/）的内容，将该文件夹下文件的名字输出到 filenames.txt, 子文件夹的名字输出到 dirname.txt 。

## Script

```bash
#!bin/bash
#/home/homework/bash_homework.sh
function getdir(){
	dirname=$2
	filename=$3
    for file in `ls -A $1`
    do
	    name=$1"/"$file
    if [ -d $name ];then
	    echo $name >> $dirname
	    getdir $name $dirname $filename
    elif [ -f $name ];then
	    echo $name >> $filename
    else
	    :
    fi
    done
}
getdir $1 $2 $3
```

## Running & Results

终端内运行
```
sh bash_homework.sh bash_homework dirname.txt filename.txt
```

输出结果：
**filename.txt**
```
bash_homework/bash_homework/a1.txt
bash_homework/bash_homework/a.txt
bash_homework/bash_homework/b1.txt
bash_homework/bash_homework/bam_wig.sh
bash_homework/bash_homework/b.filter_random.pl
bash_homework/bash_homework/c1.txt
bash_homework/bash_homework/chrom.size
bash_homework/bash_homework/c.txt
bash_homework/bash_homework/d1.txt
bash_homework/bash_homework/dir.txt
bash_homework/bash_homework/.DS_Store
bash_homework/bash_homework/e1.txt
bash_homework/bash_homework/f1.txt
bash_homework/bash_homework/human_geneExp.txt
bash_homework/bash_homework/if.sh
bash_homework/bash_homework/image
bash_homework/bash_homework/insitiue.txt
bash_homework/bash_homework/mouse_geneExp.txt
bash_homework/bash_homework/name.txt
bash_homework/bash_homework/number.sh
bash_homework/bash_homework/out.bw
bash_homework/bash_homework/random.sh
bash_homework/bash_homework/read.sh
bash_homework/bash_homework/test3.sh
bash_homework/bash_homework/test4.sh
bash_homework/bash_homework/test.sh
bash_homework/bash_homework/test.txt
bash_homework/bash_homework/wigToBigWig
bash_homework/__MACOSX/._bash_homework
bash_homework/__MACOSX/bash_homework/._a1.txt
bash_homework/__MACOSX/bash_homework/._a-docker
bash_homework/__MACOSX/bash_homework/._app
bash_homework/__MACOSX/bash_homework/._a.txt
bash_homework/__MACOSX/bash_homework/._b1.txt
bash_homework/__MACOSX/bash_homework/._backup
bash_homework/__MACOSX/bash_homework/._bam_wig.sh
bash_homework/__MACOSX/bash_homework/._b.filter_random.pl
bash_homework/__MACOSX/bash_homework/._bin
bash_homework/__MACOSX/bash_homework/._biosoft
bash_homework/__MACOSX/bash_homework/._c1-RBPanno
bash_homework/__MACOSX/bash_homework/._c1.txt
bash_homework/__MACOSX/bash_homework/._chrom.size
bash_homework/__MACOSX/bash_homework/._c.txt
bash_homework/__MACOSX/bash_homework/._d1.txt
bash_homework/__MACOSX/bash_homework/._datatable
bash_homework/__MACOSX/bash_homework/._db
bash_homework/__MACOSX/bash_homework/._dir.txt
bash_homework/__MACOSX/bash_homework/._download
bash_homework/__MACOSX/bash_homework/._.DS_Store
bash_homework/__MACOSX/bash_homework/._e1.txt
bash_homework/__MACOSX/bash_homework/._e-annotation
bash_homework/__MACOSX/bash_homework/._exRNA
bash_homework/__MACOSX/bash_homework/._f1.txt
bash_homework/__MACOSX/bash_homework/._genome
bash_homework/__MACOSX/bash_homework/._git
bash_homework/__MACOSX/bash_homework/._highcharts
bash_homework/__MACOSX/bash_homework/._home
bash_homework/__MACOSX/bash_homework/._hub29
bash_homework/__MACOSX/bash_homework/._human_geneExp.txt
bash_homework/__MACOSX/bash_homework/._ibme
bash_homework/__MACOSX/bash_homework/._if.sh
bash_homework/__MACOSX/bash_homework/._image
bash_homework/__MACOSX/bash_homework/._insitiue.txt
bash_homework/__MACOSX/bash_homework/._l-lwl
bash_homework/__MACOSX/bash_homework/._map2
bash_homework/__MACOSX/bash_homework/._mljs
bash_homework/__MACOSX/bash_homework/._module
bash_homework/__MACOSX/bash_homework/._mogproject
bash_homework/__MACOSX/bash_homework/._mouse_geneExp.txt
bash_homework/__MACOSX/bash_homework/._name.txt
bash_homework/__MACOSX/bash_homework/._node_modules
bash_homework/__MACOSX/bash_homework/._number.sh
bash_homework/__MACOSX/bash_homework/._out.bw
bash_homework/__MACOSX/bash_homework/._perl5
bash_homework/__MACOSX/bash_homework/._postar2
bash_homework/__MACOSX/bash_homework/._postar_app
bash_homework/__MACOSX/bash_homework/._postar.docker
bash_homework/__MACOSX/bash_homework/._random.sh
bash_homework/__MACOSX/bash_homework/._RBP_map
bash_homework/__MACOSX/bash_homework/._read.sh
bash_homework/__MACOSX/bash_homework/._rout
bash_homework/__MACOSX/bash_homework/._script
bash_homework/__MACOSX/bash_homework/._script_backup
bash_homework/__MACOSX/bash_homework/._software
bash_homework/__MACOSX/bash_homework/._tcga
bash_homework/__MACOSX/bash_homework/._test
bash_homework/__MACOSX/bash_homework/._test3.sh
bash_homework/__MACOSX/bash_homework/._test4.sh
bash_homework/__MACOSX/bash_homework/._test.sh
bash_homework/__MACOSX/bash_homework/._test.txt
bash_homework/__MACOSX/bash_homework/._tmp
bash_homework/__MACOSX/bash_homework/._tmp_script
bash_homework/__MACOSX/bash_homework/._var
bash_homework/__MACOSX/bash_homework/._wigToBigWig
bash_homework/__MACOSX/bash_homework/._x-rbp
```

**dirname.txt**
```
bash_homework/bash_homework
bash_homework/bash_homework/a-docker
bash_homework/bash_homework/app
bash_homework/bash_homework/backup
bash_homework/bash_homework/bin
bash_homework/bash_homework/biosoft
bash_homework/bash_homework/c1-RBPanno
bash_homework/bash_homework/datatable
bash_homework/bash_homework/db
bash_homework/bash_homework/download
bash_homework/bash_homework/e-annotation
bash_homework/bash_homework/exRNA
bash_homework/bash_homework/genome
bash_homework/bash_homework/git
bash_homework/bash_homework/highcharts
bash_homework/bash_homework/home
bash_homework/bash_homework/hub29
bash_homework/bash_homework/ibme
bash_homework/bash_homework/l-lwl
bash_homework/bash_homework/map2
bash_homework/bash_homework/mljs
bash_homework/bash_homework/module
bash_homework/bash_homework/mogproject
bash_homework/bash_homework/node_modules
bash_homework/bash_homework/perl5
bash_homework/bash_homework/postar2
bash_homework/bash_homework/postar_app
bash_homework/bash_homework/postar.docker
bash_homework/bash_homework/RBP_map
bash_homework/bash_homework/rout
bash_homework/bash_homework/script
bash_homework/bash_homework/script_backup
bash_homework/bash_homework/software
bash_homework/bash_homework/tcga
bash_homework/bash_homework/test
bash_homework/bash_homework/tmp
bash_homework/bash_homework/tmp_script
bash_homework/bash_homework/var
bash_homework/bash_homework/x-rbp
bash_homework/__MACOSX
bash_homework/__MACOSX/bash_homework
```