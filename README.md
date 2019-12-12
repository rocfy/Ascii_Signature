### 介绍
此项目移植于网页版字符画生成器，最初是为了方便公众号生成图文素材的封面图片。移植到Linux下后，不仅可以更方便生成字符画，也可应用于linux命令行模式下，使其文字提示更加醒目美观。
### 文件说明
#### ascii_signature.sh
此文件为工具主程序，实现了查询当前可用字体，根据参数生成目标字符画的功能。
- 目前支持对大小写英文字母和数字转化，暂不支持特殊字符
- 脚本内自带一种默认字符画，其他字符画依赖于相同路径下`font`文件夹
- 没有 [-f|--font]参数时默认使用自带默认字体*smkeyboard*

具体操作如下：
```
PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh
usage:
    ./ascii_signature.sh --font|-f $font --str|-s $string   do work
                         --list|-l                            list all supported font

PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh -l
smkeyboard(default) blocks bubble doom smpoison template timesofl univers

PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh -s Diag -f univers
88888888ba,   88 
88      `"8b  "" 
88        `8b    
88         88 88 ,adPPYYba,  ,adPPYb,d8 
88         88 88 ""     `Y8 a8"    `Y88 
88         8P 88 ,adPPPPP88 8b       88 
88      .a8P  88 88,    ,88 "8a,   ,d88 
88888888Y"'   88 `"8bbdP"Y8  `"YbbdP"Y8 
                             aa,    ,88 
                              "Y8bbdP"  

PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$
```
#### `font` 文件夹
用于存放字符画风格的目录。其中，'template' 为模板文件，在新增字符画风格时，只需将'template' `copy` 成新的名字，然后将文件中大小写英文字母和数字填入对应位置即可
目前已经支持的字符画样式如下：
```
PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ls font/
blocks  bubble  doom  smpoison  template  timesofl  univers
PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh -s Diag 
 ____  ____  ____  ____ 
||D ||||i ||||a ||||g ||
||__||||__||||__||||__||
|/__\||/__\||/__\||/__\|
PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh -s Diag -f blocks
 .----------------.  .----------------.  .----------------.  .----------------.
| .--------------. || .--------------. || .--------------. || .--------------. |
| |  ________    | || |     _____    | || |      __      | || |    ______    | |
| | |_   ___ `.  | || |    |_   _|   | || |     /  \     | || |  .' ___  |   | |
| |   | |   `. \ | || |      | |     | || |    / /\ \    | || | / .'   \_|   | |
| |   | |    | | | || |      | |     | || |   / ____ \   | || | | |    ____  | |
| |  _| |___.' / | || |     _| |_    | || | _/ /    \ \_ | || | \ `.___]  _| | |
| | |________.'  | || |    |_____|   | || ||____|  |____|| || |  `._____.'   | |
| |              | || |              | || |              | || |              | |
| '--------------' || '--------------' || '--------------' || '--------------' |
 '----------------'  '----------------'  '----------------'  '----------------' 

PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh -s Diag -f bubble
  _    _    _    _  
 / \  / \  / \  / \ 
( D )( i )( a )( g )
 \_/  \_/  \_/  \_/ 

PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh -s Diag -f doom
______   _                  
|  _  \ (_)                 
| | | |  _    __ _    __ _  
| | | | | |  / _` |  / _` | 
| |/ /  | | | (_| | | (_| | 
|___/   |_|  \__,_|  \__, | 
                      __/ | 
                     |___/  

PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh -s Diag -f smpoison
@@@@@@@  @@@  @@@@@@   @@@@@@@  
@@!  @@@ @@! @@!  @@@ !@@       
@!@  !@! !!@ @!@!@!@! !@! @!@!@ 
!!:  !!! !!: !!:  !!! :!!   !!: 
:: :  :  :    :   : :  :: :: :  

PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh -s Diag -f timesofl
     ### ######## ######## ######## 
#  #  ## ###  ### ######## ######## 
#  ##  # ######## ###  ### ##   # # 
#  ##  # ##   ### ## #  ## #  ##  # 
#  ##  # # #  ### #  #  ## #  #   # 
#  #  ## ###  # # #  #  ## ##  #  # 
     ### ###   ## ##  #  # ####  ## 
######## ######## ######## #    ### 

PedroQin@LAPTOP-7QJ4FHLC MINGW64 /d/OneDrive - Lo/linux/Ascii_Signature (master)
$ ./ascii_signature.sh -s Diag -f univers
88888888ba,   88 
88      `"8b  "" 
88        `8b    
88         88 88 ,adPPYYba,  ,adPPYb,d8 
88         88 88 ""     `Y8 a8"    `Y88 
88         8P 88 ,adPPPPP88 8b       88 
88      .a8P  88 88,    ,88 "8a,   ,d88 
88888888Y"'   88 `"8bbdP"Y8  `"YbbdP"Y8 
                             aa,    ,88 
                              "Y8bbdP"  

```


**注**：当缺少小写字母对应字符画时，将对应位置留空即可。在进行转换时会自动使用大写字母字符画进行替换
