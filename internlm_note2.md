# InternLM 大模型实战营笔记-2
## 入门岛
### 第二关 Python基础知识
#### 任务一：python实现 word count

编写单词统计函数如下：
```py
text = """
Got this panda plush toy for my daughter's birthday,
who loves it and takes it everywhere. It's soft and
super cute, and its face has a friendly look. It's
a bit small for what I paid though. I think there
might be other options that are bigger for the
same price. It arrived a day earlier than expected,
so I got to play with it myself before I gave it
to her.
"""

def wordcount(text):
    text = text.lower()
    word_count = {}

    for char in [',','.','\n','!']:
        text = text.replace(char,' ')
    
    words = text.split()

    for word in words:
        if word in word_count:
            word_count[word] += 1
        else:
            word_count[word] = 1

    return word_count

a = wordcount(text)
print(a)

```
单词统计结果如下：
![alt text](image.png)

{'got': 2, 'this': 1, 'panda': 1, 'plush': 1, 'toy': 1, 'for': 3, 'my': 1, "daughter's": 1, 'birthday': 1, 'who': 1, 'loves': 1, 'it': 5, 'and': 3, 'takes': 1, 'everywhere': 1, "it's": 2, 'soft': 1, 'super': 1, 'cute': 1, 'its': 1, 'face': 1, 'has': 1, 'a': 3, 'friendly': 1, 'look': 1, 'bit': 1, 'small': 1, 'what': 1, 'i': 4, 'paid': 1, 'though': 1, 'think': 1, 'there': 1, 'might': 1, 'be': 1, 'other': 1, 'options': 1, 'that': 1, 'are': 1, 'bigger': 1, 'the': 1, 'same': 1, 'price': 1, 'arrived': 1, 'day': 1, 'earlier': 1, 'than': 1, 'expected': 1, 'so': 
1, 'to': 2, 'play': 1, 'with': 1, 'myself': 1, 'before': 1, 'gave': 1, 'her': 1}

#### 任务二、在远程开发机上debug单词统计函数

##### part A
1. 新建一个python文件：python_debug用来debug

![alt text](image-2.png){width=500}

2. 设置断点并启动debug
![alt text](image-3.png){width=800}

##### part B
在vscode中使用命令行进行debug
1. 配置一下debug的config,通过remote的方法连接我们在命令行中发起的debug server：点击VSCode侧边栏的“Run and Debug”（运行和调试），单击"create a lauch.json file"
2. 选择debugger时选择python debuger。选择debug config时选择remote attach就行，随后会让我们选择debug server的地址，因为我们是在本地debug，所以全都保持默认直接回车就可以了，也就是我们的server地址为localhost:5678。
3. 在命令行发起debug
   `python -m debugpy --listen 5678 --wait-for-client ./myscript.py`
4.先在终端中发起debug server，然后再去vscode debug页面单击一下绿色箭头开启debug。
![alt text](image-4.png)
