# JDK、JRE与JVM

## 基本概念

### 1. JDK (Java Development Kit)
Java开发工具包，包含了Java开发、编译、调试的所有工具。

#### 主要组成部分
- 开发工具（如javac、java、jar等）
- JRE（Java运行环境）
- Java类库（java API）
- 文档

#### 常用开发工具
```bash
javac: 编译器，将源代码转换为字节码
java: 解释器，运行Java程序
javadoc: 文档生成器
jar: Java归档工具
jdb: Java调试器
```

### 2. JRE (Java Runtime Environment)
Java运行环境，是运行Java程序所必需的环境。

#### 组成部分
- JVM
- Java核心类库
- 运行时所需文件

```java
// JRE示例：只需要JRE就能运行的Hello World程序
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### 3. JVM (Java Virtual Machine)
Java虚拟机，负责执行字节码文件。

#### 主要功能
- 加载、验证、执行字节码
- 内存管理和垃圾回收
- 提供与硬件和操作系统无关的运行环境

#### JVM内存结构
```java
// JVM内存区域示例
public class MemoryDemo {
    private static int staticVar;    // 方法区
    private int instanceVar;         // 堆
    
    public void method() {
        int localVar = 0;           // 栈
        // ...
    }
}
```

## 三者关系

```
JDK
├── 开发工具
├── JRE
│   ├── JVM
│   └── 核心类库
└── 其他资源
```

## 面试要点

1. JDK、JRE、JVM的区别与联系？
   - JDK包含JRE，JRE包含JVM
   - JDK面向开发者，JRE面向用户
   - JVM是Java平台无关性的基础

2. 为什么需要JVM？
   - 实现平台无关性
   - 提供自动内存管理
   - 保证Java程序的安全性

3. JVM的内存模型是怎样的？
   - 堆区
   - 栈区
   - 方法区
   - 程序计数器
   - 本地方法栈

## 答题技巧

1. 先说概念，后谈关系
2. 用图示说明三者关系
3. 结合实际开发经验
4. 适当提及版本差异（如Java 8后的变化）

## 实践建议

1. 环境配置
```bash
# 查看JDK版本
java -version

# 查看JDK安装路径
which java

# 设置JAVA_HOME
export JAVA_HOME=/path/to/jdk
```

2. 开发工具使用
```bash
# 编译Java文件
javac HelloWorld.java

# 运行Java程序
java HelloWorld
```

3. JVM调优实践
```bash
# 设置堆内存大小
java -Xms512m -Xmx1024m MyApp
``` 