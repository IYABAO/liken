# liken（知音）— 给你喜欢的东西找个同类

> **Put a cousin to what you love.**
> （给你喜欢的东西，找个同类）

输入你喜欢的一个或多个东西——**不限类型**：书 / 电影 / 音乐 / App / 咖啡 / 城市 / 概念……
先提炼它们的共性品味维度，再跨域找相似，每条告诉你"为什么像"。

---

## 📦 已发布平台

| 平台 | 链接 | 说明 |
|------|------|------|
| GitHub | [IYABAO/liken](https://github.com/IYABAO/liken) | 主仓库 |
| skillhub.cn | 知音 | 中文名"知音" |
| clawhub.ai | 已发布 | |
| skills.sh | 已发布 | |

---

## ✨ 特性

- 🎯 **不限领域**：书 / 电影 / 音乐 / App / 咖啡 / 城市 / 工作方式 / 任意概念都能输入
- 🔍 **先画像再推荐**：不直接列清单，先拆出 3-5 个可对照的品味维度（气质/主题/结构/情绪）
- 🌉 **真跨域**：从一本书的气质联想到一首歌、一款咖啡、一个城市
- 📊 **同域≥7 校验样本量**：同领域给 7+ 候选，让你判断它抓的品味对不对
- 🚪 **入门路径**：不只给清单，告诉你"先从这一个开始，再读那个"
- 🏷️ **记忆点总标签**：给这组品味起个名字（如"在深渊里点灯的人"）
- ✅ **存在性核实**：书走 OpenLibrary、音乐走 iTunes、电影走 Wikidata，推荐前核实真实存在
- 🔮 **诚实标注**：抽象类候选标 🔮（品味推理），拿不准的标"待核实"，不编造
- 🛡️ **防回音壁**：同域 7+ 校验样本量，跨域每类含"冒险款"跳出舒适区
- ⚡ **快捷命令**：`liken` / `知音`

---

## 🚀 快捷触发

```bash
# 给两个喜欢的东西找同类
liken 我喜欢《百年孤独》、Notion、手冲耶加雪菲

# 中文触发
知音 《星际穿越》和 Radiohead

# 多 item 混合类型
liken 我喜欢极简主义博客和 macOS

# 只看某几类
liken 我喜欢《海边的曼彻斯特》、冰岛后摇 --domains book,music
```

---

## 📝 输出示例

### 输入：庄子 / 尼采

**总标签：自由的叛逆者**

**共性维度**：反主流 / 个体自由 / 诗化不说教 / 生命自然本位 / 视角相对主义

**入门路径**：先《西西弗神话》→ 再《瓦尔登湖》

**同域延伸（哲学书，8 本）**：

| 候选 | 它是什么 | 为什么像 | 难度 |
|---|---|---|---|
| 《西西弗神话》加缪 | 推石上山自己赋予意义 | 反主流·个体自由 | ⭐ |
| 《沉思录》马可·奥勒留 | 皇帝在军营写给自己的笔记 | 个体自由·生命本位 | ⭐ |
| …… | | | |

**跨域**：电影《潜行者》《都灵之马》/ 音乐贝多芬第九、比才卡门 / 体验锡尔斯玛利亚 🔮

---

## 📦 安装

### 方式 1：复制到 skills 目录

```bash
git clone https://github.com/IYABAO/liken.git
cp -r liken/skills/liken ~/.your-agent/skills/liken
```

### 方式 2：通过 Skill 市场安装

```bash
skillhub install liken
```

### 前置要求

- Python 3.8+（用于存在性核实脚本，无 key）
- 支持 Skill 系统的 AI Agent（如 Claude、Doubao 等）
- 推荐配 HTTP 代理访问 OpenLibrary / iTunes / Wikidata（国内环境）

---

## 🧪 评估

### 评测结果（v0.3.0）

| 评测工具 | 分数 |
|---|---|
| NVIDIA 5 维 rubric（Correctness/Discoverability/Effectiveness/Efficiency/Security） | **90.0/100** |
| agent-creator 7 维 rubric | **70/70** |
| 自有 6 维 rubric（EVAL.md） | **12/12** |
| 真实用户输入验收 | 3 组全部通过 |

详细报告见 [EVAL-REPORT.md](EVAL-REPORT.md)。

---

## 📁 项目结构

```
liken/
├── skills/liken/
│   ├── SKILL.md              # 主技能文件（v0.3.0，121 行）
│   ├── skill-card.md         # 技能卡片
│   └── scripts/
│       └── recommend.py      # 存在性核实（OpenLibrary/iTunes/Wikidata/TVmaze）
├── EVAL.md                   # 自进化评测规范
├── EVAL-REPORT.md            # 评测报告
├── README.md
├── CHANGELOG.md
├── LICENSE
└── CONTRIBUTING.md
```

---

## 🆚 liken vs 普通书单推荐

| 维度 | liken | 普通"给我推荐类似的书" |
|---|---|---|
| **核心产出** | 品味画像 + 跨域对照 | 一个书单 |
| **跨域** | ✅ 书→影→音→产品→城市→体验 | ❌ 只推同类型 |
| **可解释性** | ✅ 每条"它是什么+为什么像+命中维度" | ❌ 只给名单 |
| **校验样本量** | ✅ 同域≥7，让你判断抓得准不准 | ❌ 3-5 条无法判断 |
| **入门路径** | ✅ "先从这一个开始" | ❌ 面对清单无从下手 |
| **存在性核实** | ✅ 4 个免费 API 核实 | ❌ 常编造书名 |
| **诚实标注** | ✅ 抽象类标🔮、拿不准标待核实 | ❌ 把推理伪装成数据库结果 |
| **防回音壁** | ✅ 同域 7+ + 跨域冒险款 | ❌ 越推越像 |

---

## 🛠️ 开发

### 运行存在性核实脚本

```bash
cd skills/liken/scripts
py recommend.py book "百年孤独"
py recommend.py music "Karma Police Radiohead"
py recommend.py movie "Inception"
```

### 验证 Skill

```bash
py ~/.skills/skill-creator-for-work/scripts/quick_validate.py skills/liken
```

---

## 📋 Roadmap

- [x] v0.1.0：基础书影音推荐 + TasteDive/OpenLibrary
- [x] v0.2.0：跨域品味画像 + 3 轮自进化评测
- [x] v0.2.3：清理不可用接口（TasteDive/Google Books/iTunes movie）
- [x] v0.3.0：同域≥7、表格化输出、入门路径、总标签、领域动态不预设
- [ ] v0.4.0：HF Space Demo（Gradio 输入→输出品味画像）
- [ ] v0.5.0：接入真实相似召回 API（TasteDive 替代 / TasteKid / BGM score）
- [ ] v0.6.0：多语言英文版 SKILL.en.md
- [ ] v1.0：Tier 3 live evaluation（with/without skill A/B）

---

## 📄 License

MIT
