# 总结
编程语言通识
语言按照语法分类
非形式语言
    中文，英文
        理解：演变快，无固定规律
形式语言（乔姆斯基谱系）
    0型 无限制文法                                     （左右都无限制）
    1型 上下文相关文法 （js中this）                     （产生式可以有多个，上下文不变中间内容可改变）
    2型 上下文无关文法 （js大部分属于）                  （等号左边只能有一个非终结符）
    3型 正则文法 （对表达能力限制强）                    （只允许左递归）

        产生式（BNF）->自己跟着视频多做几遍
            语法结构：用尖括号括起来的名称
                基础结构 称 终结符 symbol
                复合结构 称 非终结符
            引号和中间的字符可以为终结符
            解析过程：语法分析
（js正则很慢，因为它支持回溯）
        其他产生式（EBNF ABNF）
现代语言特例
c++：非型
VB：1
Python：非型
Js：1


图灵完备性
    命令式——图灵机（所有东西能被计算）
        goto
        if和while
    声明式——lambda
        递归

    计算机语言必须是图灵完备的


动态语言
    在用户的设备/在线服务器上
    产品实际运行时
    Runtime
静态语言
    在程序员的设备上
    产品开发时
    compiletime（编译时）


类型系统
    动态类型系统与静态类型系统
    强类型（无隐式转换）与弱类型(有隐式转换)
        eg：
        string + number
    复合类型
        结构体（eg:对象）
        函数签名（函数参数、返回值）
    子类型（继承？）
        逆变/协变


一般命令式编程语言
atom                      expression  Statement  structure  program
原子（eg：变量名，直接量）  表达式      语句        结构化     程序集

重学js
语法  ->语义 -> 运行时


unicode
字符集
a: 97 A: 65

block
basic latin 0-128 ask范围
LINE FEED   十
Cjk 中/日/韩文字符
BMP:基本字符（4位字符，兼容性好）.fromCharCode 
非BMP .fromCodePont .codePontAt

category 分类
Separater Space   所有的space在js中都合法


 inputElement
    whiteSpace 空白
    LineTerminator 回车 换行
    Comment 注释
    Token 标记（js中有效的内容）

    whiteSpace 从完备性讲支持Unicode的空白
        <TAB> 制表符 使用tab键出现的空格  u+009
        <VT> 在js中是\v 纵向的tab 纵向制表符
        <FF> 10   ?
        <SP> 普通空格
        <NBSP> no-break space                   00a0 使用它可以将词连在一起当作一个词，换行的时候不分开
        <ZWNBS> zero with no break spance      feff  没懂？？？BOM bit order mask  零宽空格
        <usb> 
    LineTerminator 换行符
        <LF> 推荐使用 000a 
        <cr> 
        <LS> 不在Unicode编码内，最好不用
        <PS> 不在Unicode编码内，最好不用
    Comment
        单行 //
        多行 /**/
    Token
        IndentifierName 必须以字母开头 标识符（变量名，属性名） eg: 变量名，document，write
            keywords
            identifier 变量
            future reserved keywords：enum
        punctuator 符号 eg: 括号，等号，小于号
        literal
            Number
            String
            undefined
            null
            Bullean