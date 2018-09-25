# InterpreterProject-2016302580007
A project about interpreter at 2016302580007
* 陈开一 2016302580007 (代码Githup部分)
* 南思宇 2016302580017 (设计文档)
* 史雪峰 2016302580019 (设计文档)
* 张凯康 2016302580020 (设计文档)
* 叶晟柯 2016302160017 (设计文档)

利用LLVM构造一个简单的语法分析器，输入表达式之后能够打印出抽象语法树。

### 一.抽象语法树的构造完善
在原有的LLVMchapter2代码基础上补全抽象语法树AST。由于后面表达式的字符都是父类指针指向的子类对象，所以我们无法事先预知表达式的类型，所以在基类'ExprAST'中添加虚函数：virtual toString()，子类中实现，输出自身。下图中给出了父类的虚函数声明以及部分子类的实现：  
![image text](https://github.com/Bluchris/Expression-2016302580007/blob/master/virtual%20method.png)

值得注意的是，我们的表达式类BinaryExprAST中包含有运算符的左子树和右子树，因此我们需要调用get()方法获取父类的指针，而后调用toString()函数实现打印：如下图
