# 我的计算机科学自学计划

> 这份计划是基于 [cs-self-learning 指南](https://github.com/PKUFlyingPig/cs-self-learning) 制定的个人学习路线图。
>
> **目标**：在两年内，系统性地掌握计算机科学核心知识，并构建一个个人项目作品集。

---

## 第一阶段：基础工具与入门 (预计3个月)

这个阶段的目标是**打好地基**，掌握最基本的工具和编程思维。
### 学习清单 (有序列表)
**基础技能**
- [x] 掌握 `Markdown` 进行日常笔记记录，用obsidian构建个人知识库
- [x] 学习如何使用Git和Github
- [ ] 构建有效的信息搜索途径如利用高级搜索，使用Google而不是百度，用ai代替搜索
- [ ] 构建高效的信息获取，处理，使用流程
**编程入门：CS50**
   - 学习平台：edX 或 Bilibili
   - 重点：*必须完成每周的编程作业 (Problem Sets)*！
### 本阶段期望产出
* 1.一个内容丰富的 GitHub 个人主页
* 2.至少 5 个 CS50 的编程作业项目仓库
---
## 第二阶段：核心理论（预计1.5年）

这是整个计划最硬核的部分，需要投入大量时间和精力。
### 核心课程表格

| 课程名称    | 推荐资源                    | 状态  | 备注                 |
| :------ | :---------------------- | :-- | :----------------- |
| 数据结构与算法 | 《算法》第四版                 | 未开始 | 需要配合 LeetCode等平台刷题 |
| 计算机组成原理 | 南京大学 ICS                | 未开始 | 实验课 `PA` 是重点       |
| 操作系统    | MIT 6.S081 (2020)与CSAPP | 未开始 | 实验课 `Lab` 极具挑战     |
| 计算机网络   | 《自顶向下方法》                | 未开始 | 重点理解协议栈            |

### 一个代码示例
学习C语言时,经常有读取键盘输出到数组中的需求,同时也需要将数组的内容输出到屏幕

```c
#include <stdio.h>
#include <stdbool.h>
#define MAX_LENGTH 1000
void read_stdin(char buffer[], int max_size);
void print_stdout(const char buffer[]);
int main() {
    char user_input[MAX_LENGTH];
    printf("Please enter your input. You can input up to %d characters.\n", MAX_LENGTH - 1);
    read_stdin(user_input, MAX_LENGTH);    
    printf("\nRead successfully!\n");
    printf("If you want to print your input, please enter 1: ");
    
    int choice = 0;    
    if (scanf("%d", &choice) == 1&&choice == 1){
            printf("\nYour input was:\n");
            print_stdout(user_input);  
        }
    printf("\nProgram finished.\n");
    return 0;
}
void read_stdin(char buffer[], int max_size){
    int i = 0;
    int c;
    while (i < max_size - 1 && (c = getchar()) != EOF && c != '\n'){
        buffer[i] = (char)c;
        i++;
    }
    buffer[i] = '\0';
}
void print_stdout(const char buffer[]){
    int i = 0;
    while (buffer[i] != '\0'){
        putchar(buffer[i]);  
        i++;
    }
    putchar('\n');  
}
```