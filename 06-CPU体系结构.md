# CPU 体系结构

CPU 由两大部分组成，分别是控制器和运算器。

## 控制器

组成：
 - 程序计数器【PC】:用于指出下条指令在主存中的存放地址，CPU根据程序计数器的内容去主存处取得指令；
 - 数据寄存器【DR】:用于暂存从“内存储器”中读出或写入的指令或数据；
 - 指令寄存器【IR】:用于保存当前正在执行的这条指令的代码；
 - 地址寄存器【AR】:用于存放CPU当前访问的内存单元地址；
 - 指令译码器：用于对获取的指令进行译码，产生该指令操作所需要的一系列微操作信号，以控制计算机各部件完成该指令。

![image](https://github.com/anna-symington/web-engineering/assets/160561460/6d5e1af4-9443-4d93-b572-ef1d655a98b8)

![image](https://github.com/anna-symington/web-engineering/assets/160561460/7992794b-430c-4321-9cda-60dccac7f2f1)

## 运算器

组成：
 - 算数逻辑单元【ALU】：用于进行各种**逻辑运算【如：与、或、非等】**、**算数运算【如加、减、乘、除等】**
 - 通用寄存器：用来存放操作数、中间结果和各种地址信息的一系列存储单元。
 - 数据暂存器：用来暂存从“主存储器”读出的数据
 - 程序状态字寄存器【PSW】：用来存放“体现当前指令执行结果的各种状态信息”和“控制信息”的

### 通用寄存器
 - 数据寄存器
 - 地址指针寄存器
 - **累加寄存器**

累加寄存器：
 - 例：要计算2（被减数）-1（减数）的结果，就要先把2存放在累加寄存器中，然后从指令中调取减数，获得运算结果后将结果存储在累加寄存器中。

## 指令

 计算机中的一条【指令】就是机器语言的一个语句。
 
一条【指令】由两部分构成

 - 操作码：用于决定要完成的操作
 - 地址码：用于说明操作数的地址，而操作数指的是参加运算的数据及其所在 的单元地址

 操作码 | 地址码
 
 **结论：CPU中指令的执行过程分为:取指令、取操作数、执行操作**

 ![image](https://github.com/anna-symington/web-engineering/assets/160561460/fe3322d9-edc0-4597-9ff3-ed6cf6e5bc68)

## 例子：计算 1+1

 ![image](https://github.com/anna-symington/web-engineering/assets/160561460/f54ceb25-d6af-4e15-9d8f-a743edca8724)

![image](https://github.com/anna-symington/web-engineering/assets/160561460/b645daad-142a-4705-908f-3b41112c6882)

**用户通过键盘等输入设备输入1+1**

![image](https://github.com/anna-symington/web-engineering/assets/160561460/ed114a2b-1139-4c3d-b5a4-4d27f6ca0c7e)

**输入设备将数据放在存储器中**

![image](https://github.com/anna-symington/web-engineering/assets/160561460/a7660051-7619-44d8-bc4b-ebf1a65905db)

**控制器发送控制指令取得数据，存储器将数据提供给运算器**

![image](https://github.com/anna-symington/web-engineering/assets/160561460/dedb5804-796c-456e-8b27-599b9b723679)

![image](https://github.com/anna-symington/web-engineering/assets/160561460/16113e7c-d580-4eff-973f-72c60c7e2232)

**控制器给运算器发送指令，运算器计算完毕后提供给存储器**

![image](https://github.com/anna-symington/web-engineering/assets/160561460/a8b47de0-6c49-4f6c-b3ac-6e2cbc43ff37)

**控制器给存储器发送指令，存储器将数据提供给输出设备**

![image](https://github.com/anna-symington/web-engineering/assets/160561460/308f7109-ed69-4f13-b590-339d17222ee3)

**控制器给输出设备发送指令，输出设备输出内容给用户**

![image](https://github.com/anna-symington/web-engineering/assets/160561460/28a8db93-4541-4cbc-9ff4-df3d15070cdb)
