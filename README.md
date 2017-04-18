# Rust
/******************/
相关习题 
/*****************/
1. Generic lines iterator

问题描述

有时候我们可能做些文本分析工作, 数据可能来源于外部或者程序内置的文本.
请实现一个 parse 函数, 只接收一个 lines iterator 为参数, 并输出每行.
要求既能输出内置的文本, 也能输出文件内容.
调用方式及输出参考

let lines = "some\nlong\ntext".lines()
parse(do_something_or_nothing(lines))
some
long
text
use std::fs:File;
use std::io::prelude::*;
use std::io::BufReader;
let lines = BufReader::new(File::open("/etc/hosts").unwrap()).lines()
parse(do_some_other_thing_or_nothing(lines))
127.0.0.1       localhost.localdomain   localhost
::1             localhost.localdomain   localhost
...
Hint

本书类型系统中的几个常见 trait章节中介绍的 AsRef, Borrow 等 trait 应该能派上用场.
