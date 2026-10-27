# taskdecomp

**检查任务分解是否覆盖了原始需求。**

`taskdecomp` —— 把原始需求拆成子点，比对分解结果，标出未覆盖的子点与多余步骤

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`taskdecomp.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install thecornet-taskdecomp
```

装完直接用命令名调用：

```bash
taskdecomp --help
```

也可以不用安装，直接把 `taskdecomp.py` 拷走用——它只依赖标准库。

## 为什么需要它

「没做」和「多做」分开列，因为它们的修法不同

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 智能体任务分解 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python taskdecomp.py --file input.txt
python taskdecomp.py --text "示例内容"
python taskdecomp.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 覆盖率的分母取自你登记的清单，清单不全就会偏高。
- 只做映射，不追责。

## 跑测试

```bash
python test_taskdecomp.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/thecornet/taskdecomp>

---

## 关于作者

thecornet 做智能体任务分解相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://thecornet.github.io>
- 仓库：<https://github.com/thecornet/taskdecomp>

## 许可

MIT，见 [LICENSE](LICENSE)。
