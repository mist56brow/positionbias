# positionbias

**找出评测裁判的位置偏差里互相矛盾的两处并排列出。**

`positionbias` —— 在同一个输入里两两比对，检测评测裁判的位置偏差相关的矛盾表述，把冲突双方原样并排呈现

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`positionbias.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install mist56brow-positionbias
```

装完直接用命令名调用：

```bash
positionbias --help
```

也可以不用安装，直接把 `positionbias.py` 拷走用——它只依赖标准库。

## 为什么需要它

不替用户猜哪一句是本意，只把矛盾双方并排摆出来，由人决定取舍

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 评测裁判的位置偏差 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python positionbias.py --file input.txt
python positionbias.py --text "示例内容"
python positionbias.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 一致性靠字面差异判定，语义等价但写法不同会误报。
- 不解析跨文档的引用关系。

## 跑测试

```bash
python test_positionbias.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/mist56brow/positionbias>

---

## 关于作者

mist56brow 做评测裁判的位置偏差相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://mist56brow.github.io>
- 仓库：<https://github.com/mist56brow/positionbias>

## 许可

MIT，见 [LICENSE](LICENSE)。
