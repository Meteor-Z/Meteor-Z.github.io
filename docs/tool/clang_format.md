# clang-format

用于C++格式化用

```shell
# 基于LLVM
BasedOnStyle: LLVM

# 设置缩进是 4 空格
IndentWidth: 4 

# 使用空格
UseTab: Never

# 设置访问修饰符（public、private、protected）的偏移量为-4，使得与class对其
AccessModifierOffset: -4  

# 允许排序#include
SortIncludes: false

# 指针和引用的对齐: Left, Right, Middle
PointerAlignment: Left

# 模板换行
AlwaysBreakTemplateDeclarations: Yes

# 允许重新排版注释
ReflowComments: true

# 对齐连续的尾随的注释
AlignTrailingComments: true

ColumnLimit: 90

# 设置初始化的
Cpp11BracedListStyle: false

SpaceBeforeCpp11BracedList: true
```
