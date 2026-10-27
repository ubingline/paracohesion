# paracohesion

**检查被切出的每个片段在语义上是否自洽。**

`paracohesion` —— 对每个片段计算首尾衔接度，标出依赖前文才能理解的片段

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`paracohesion.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install ubingline-paracohesion
```

装完直接用命令名调用：

```bash
paracohesion --help
```

也可以不用安装，直接把 `paracohesion.py` 拷走用——它只依赖标准库。

## 为什么需要它

只标出不自洽的片段，不做片段重排或重写

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 段落连贯性 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python paracohesion.py --file input.txt
python paracohesion.py --text "示例内容"
python paracohesion.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 切分按行与标点做，不理解语义段落。
- 空槽判定靠槽位关键词，措辞特殊时会漏。

## 跑测试

```bash
python test_paracohesion.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/ubingline/paracohesion>

---

## 关于作者

ubingline 做段落连贯性相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://ubingline.github.io>
- 仓库：<https://github.com/ubingline/paracohesion>

## 许可

MIT，见 [LICENSE](LICENSE)。
