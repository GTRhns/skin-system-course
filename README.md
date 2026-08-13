<div align="center">

<img src="assets/linna_avatar.png" alt="Linna" width="300">

<br>

# hello，大家好，我是 linna

> **欢迎来到《皮肤系统教程开源课程》** —— 用我的第一个版本皮肤系统（HnsSkin v1.0.0），做一堂真正的开源课。
> 不跳步、不省略、不"你懂的"——**哪怕是一个 `if`，也给你讲清楚。**

[![AMX Mod X](https://img.shields.io/badge/AMX_Mod_X-1.8.3+-blue)]()
[![ReGameDLL](https://img.shields.io/badge/ReGameDLL-5.x-red)]()
[![语言](https://img.shields.io/badge/语言-Pawn-blue)]()
[![课程](https://img.shields.io/badge/课程-13课-red)]()
[![源码](https://img.shields.io/badge/源码-2175行-green)]()
[![版本](https://img.shields.io/badge/版本-1.0.0-red)]()
[![License](https://img.shields.io/badge/License-GPLv3-success)]()

> **主讲人：LINNA** · Art by Linna

</div>

---

## 目录

- [这是什么](#这是什么)
- [课程目录](#课程目录)
- [建议学习方式](#建议学习方式)
- [源码与配置](#源码与配置)
- [技术栈](#技术栈)
- [期末寄语](#期末寄语)
- [开源协议](#开源协议)

---

## 这是什么

这是一门**零基础也能跟上**的 AMX Mod X 插件开发课。我们不讲抽象理论，只做一件事：

> 把 `HnsSkin.sma`（2175 行源码）**从头到尾、逐行逐句**拆开，讲明白每一行在干什么、为什么这么写、如果删掉会怎样。

学完之后，你会：

- 看懂一个完整的 CS1.6 皮肤插件是怎么工作的
- 认识 Pawn 语言的基本语法（变量、数组、函数、if、for、switch）
- 理解 AMXX 的生命周期（precache / init / end / 玩家进出）
- 学会菜单、命令、存档（nvault）、权限检查这些核心套路
- 有能力自己改一个插件、甚至写一个插件

> <span style="color:red">**这不是"背代码"的课，是"看懂代码"的课。**</span> 代码会过时，技术会更新，但"看懂一件事"的能力，永远不会过时。

---

## 课程目录

| 课时 | 主题 | 覆盖源码 |
|------|------|---------|
| [第 0 课](lessons/00-课程导论.md) | 课程导论：这门课怎么上 | 全局 |
| [第 1 课](lessons/01-插件骨架.md) | 插件骨架：include / 常量 / 全局变量 | 第 1-110 行 |
| [第 2 课](lessons/02-生命周期与初始化.md) | 生命周期：precache / init / end | 第 113-195 行 |
| [第 3 课](lessons/03-配置文件加载.md) | 配置文件加载：读 INI、内置默认 | 第 388-519 行 |
| [第 4 课](lessons/04-模型预缓存.md) | 模型预缓存：precache_model | 第 521-550 行 |
| [第 5 课](lessons/05-模型应用.md) | 模型应用：换皮肤的核心 | 第 242-286, 552-673 行 |
| [第 6 课](lessons/06-主菜单系统.md) | 主菜单：/skin 怎么弹出来 | 第 197-237 行 |
| [第 7 课](lessons/07-皮肤选择菜单.md) | 皮肤选择菜单：分页与翻页 | 第 676-963 行 |
| [第 8 课](lessons/08-管理员发放.md) | 管理员发放：giveskin 全家桶 | 第 679-1543 行 |
| [第 9 课](lessons/09-存档系统.md) | 存档系统：nvault + JSON | 第 1549-1938 行 |
| [第 10 课](lessons/10-工具函数.md) | 工具函数：has / give / take / find | 第 1940-2176 行 |
| [第 11 课](lessons/11-玩家生命周期.md) | 玩家生命周期：进出服务器 | 第 298-382 行 |
| [第 12 课](lessons/12-哲学结语.md) | 期末寄语：喜欢就足够了 | 全文 |

> <span style="color:#1e90ff">**每一课都做到"哪怕一个 if 也讲清楚"**</span> —— `if (!f)` 为什么是容错、`if (iPos >= 0)` 为什么防越界、`if (iPage < iMaxPage)` 为什么防无限翻页，每个判断的用途、删掉会怎样，都写了。

---

## 建议学习方式

1. **先看第 0 课**，了解课程怎么安排。
2. **每节课对照源码看**：把 `source/HnsSkin.sma` 打开，跟着课文的行号走。
3. **不着急**：一天一节就很好，看不懂就回头再看。
4. **动手改**：每节课末尾都有"小练习"，改坏了也没关系，源码可以随时重新下载。

> <span style="color:red">**慢慢来，不着急。**</span> 会一点，就多会一点；今天不会，明天再看。

---

## 源码与配置

- [完整源码 source/HnsSkin.sma](source/HnsSkin.sma)（v1.0.0，2175 行）
- [版本说明 source/VERSION.md](source/VERSION.md)
- [皮肤配置示例 configs/player_models.ini](configs/player_models.ini)

---

## 技术栈

| 项 | 说明 |
|----|------|
| **语言** | Pawn（AMX Mod X 脚本语言，C 风格） |
| **运行环境** | Counter-Strike 1.6 + AMX Mod X 1.8.3+ |
| **依赖模块** | `amxmodx`、`fakemeta`、`amxmisc`、`reapi`、`nvault` |
| **数据存储** | `nvault`（AMXX 内置持久化键值库） |
| **编译工具** | `amxxpc`（AMX Mod X 自带编译器） |

> Pawn 是 AMX Mod X 的官方脚本语言，语法类似 C，但用 `new` 声明变量、用 `stock` 声明可复用函数。所有 CS 插件都用它写，编译产物是 `.amxx` 二进制插件。

---

## 期末寄语

> 我并不希望你们会学会某个东西来让它变得完善，喜欢就足够了，没有必要去真正在意，不喜欢的地方。

完整版见 [第 12 课：期末寄语](lessons/12-哲学结语.md)。

> <span style="color:#1e90ff">**你不需要学会它，才能喜欢它。**</span> 你只需要喜欢它，然后，慢慢来。

> <span style="color:red">**无论怎样，我的代码也有很多缺陷——但喜欢，就足够了。**</span>

---

## 开源协议

本项目基于 **GPLv3** 协议开源，自由使用、修改和分发。

---

**皮肤系统教程开源课程** — Built with passion for the CS 1.6 HNS community.
主讲人：**LINNA**

---

<div align="center">

### <span style="color:red">⚠️ 严令禁止倒卖插件 ⚠️</span>

<span style="color:red">**本项目为原创独立开发作品，严禁任何形式的倒卖、转售或商业牟利行为！**</span>

<span style="color:red">源码已开源仅供学习交流与个人使用，未经授权不得将其打包、改头换面后用于收费出售、捆绑销售或二次分发获利。</span>

<span style="color:red">**一经发现，将直接追究相关法律责任，并停止后续更新与技术支持。**</span>

<span style="color:#ff8c00">如发现有人倒卖本插件，欢迎向主讲人 **LINNA** 举报。</span>

</div>
