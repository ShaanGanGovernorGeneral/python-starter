Python刷题记录
题目描述
给你两个字符串 word1 和 word2。请你将这两个字符串合并，合并方法是交替添加字母，从 word1 开始。如果一个字符串比另一个长，则将多余的字母添加到合并字符串的末尾。返回合并后的字符串。

代码和解析
python

运行

复制
class Solution:
【定义一个类Solution，这是力扣（LeetCode）题目的标准格式】

python

运行


    def mergeAlternately(self, word1: str, word2: str) -> str:
【这里是一个在类里面的函数，所以这里需要class】

python

运行

复制
        result = ""
【创建了一个空字符串用来储存结果，也就是像是准备了一个空盒子用来放置物品】

python

运行

复制
        i = 0
【创建一个计数器，从0开始】

python

运行

复制
        # 先处理两个字符串共同长度的部分
        while i < len(word1) and i < len(word2):
【在这里使用了while函数，什么是while函数呢？就是一个循环。这个循环里面的内容一定要符合这个循环结束的要求时这个循环才会结束。我们可以这么说循环的几个基本条件：
1."当...时，一直重复做..."
2.必须有一个结束的条件
3.循环内的操作要能够最终达到结束条件。
那么在这里我们就可以将第一句话翻译成当i小于len(word1)并且i小于len(word2)时：】

python

运行

复制
            result += word1[i] + word2[i]
【在这里的意思就是，在result原来的基础上加上word1和word2的第i位数】

python

运行

复制
            i += 1
【在这里的意思就是，当i还没有达到满足小于len(word1)并且i小于len(word2)的要求时，i在每轮循环中都要加上1】

python

运行

复制
        # 处理剩余的字符（如果有的话）
        result += word1[i:] + word2[i:]
【在这里的意思就是，如果word1或者word2比另外一个字符串要长的话，那么就在由while出来的result后面加上多出来的那部分，也就是：这个符号后面截断的那一部分】

python

运行

复制
        return result
【在这里我们可以返还由几步加工形成的result的最终结果】

完整代码
python

运行

复制
class Solution:
    def mergeAlternately(self, word1: str, word2: str) -> str:
        result = ""
        i = 0
        
        # 先处理两个字符串共同长度的部分
        while i < len(word1) and i < len(word2):
            result += word1[i] + word2[i]
            i += 1
            
        # 处理剩余的字符（如果有的话）
        result += word1[i:] + word2[i:]
        
        return result
