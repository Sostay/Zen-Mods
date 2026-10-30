# Zen-Mods 🧘‍♂️

> 专注于 **Zen 浏览器** 优秀模组（Zen Mods / Sine Mods）的集中维护、长期修复与定制适配集合仓库。

随着 Zen 浏览器及上游 Firefox 快速迭代，许多优秀的社区 Mod（如右键菜单精简、悬浮搜索栏等）原作者因各种原因不再更新维护，出现样式错位、选择器失效或与新特性冲突的情况。本仓库用于集中收集、修复并持续维护这些实用模组。

---

## 📦 模组列表与安装指令

在 Zen 浏览器的 **设置 -> Sine Mods** 页面，找到 **“or, add your own locally from a GitHub repo”** 输入框，复制对应的命令并点击 **Install** 即可：

| 模组名称 | 简介 | Sine 安装指令 (直接复制填入输入框) |
| :--- | :--- | :--- |
| **Zen Context Menu Fix** | 精简右键菜单冗余选项，人体工程学重排标签右键菜单，提供 35 项图形化开关配置 | `Sostay/Zen-Mods/tree/main/mods/zen-context-menu` |
| **Floating Findbar Fix** | 居中悬浮搜索栏，带有优雅的展开/收起平滑过渡动画 | `Sostay/Zen-Mods/tree/main/mods/floating-findbar` |

---

## 🚀 安装与使用方法

### 方式 1：通过 Sine Mods 界面安装（推荐）

1. 打开 Zen 浏览器设置，进入 **Sine Mods** 页面。
2. 在 **Marketplace** 下方的文本框中填入你想安装的 Mod 子路径（见上方表格）。
3. 点击 **Install** 按钮。Sine 会自动识别多 Mod 聚合仓库，并将对应的子 Mod 独立解压、加载生效。
4. 安装完成后，在“Installed Mods”列表中即可看到对应的 Mod 卡片；点击齿轮 ⚙️ 图标可打开功能开关面板（如适用）。

> 💡 **提示**：如果点击 Install 提示网络超时或无法连接，请确保系统已开启网络代理/TUN 模式（以便浏览器访问 GitHub 资源下载服务）。

### 方式 2：本地文件直接加载

如果你想在本地开发调试，或者直接离线使用：
1. 将本仓库克隆到本地：
   ```bash
   git clone https://github.com/Sostay/Zen-Mods.git
   ```
2. 打开 Zen 配置目录下的 `chrome/sine-mods/`（可在 `about:support` -> “配置文件夹” 找到）。
3. 将 `mods/zen-context-menu` 或 `mods/floating-findbar` 文件夹复制（或通过软链接 `mklink /D`）放入 `chrome/sine-mods/` 下。
4. 在 Sine 列表中重新切换启用即可。

---

## 📂 仓库结构

```text
Zen-Mods/
├── mods/
│   ├── zen-context-menu/          # 右键菜单精简与人体工程学重排 Mod
│   │   ├── theme.json             # Mod 元数据
│   │   ├── chrome.css             # 核心 CSS 样式表
│   │   ├── preferences.json       # 图形化开关选项定义
│   │   ├── image.png              # 封面预览
│   │   └── README.md              # 详细说明与抓取排查教程
│   │
│   └── floating-findbar/          # 悬浮动画搜索栏 Mod
│       ├── theme.json             # Mod 元数据
│       ├── userChrome.css         # 搜索栏样式与动效
│       ├── cover.png              # 封面预览
│       └── README.md              # 详细说明
│
├── .gitignore
├── LICENSE
└── README.md                      # 仓库主页指南
```

---

## 🔍 问题排查与维护指南

若 Zen 浏览器更新导致某些元素选择器失效：
1. 按 `F12` 开启开发者工具并启用“chrome 和附加组件调试”与“远程调试”。
2. 按 `Ctrl + Shift + Alt + I` 打开 **Browser Toolbox**。
3. 点击工具箱右上角的“禁用弹出菜单自动隐藏”（四个小方块气泡图标）。
4. 使用元素选择器拾取界面元素并获取最新类名/ID，在对应 Mod 的样式文件中修改并提交。

---

## 📜 鸣谢与开源协议

- [KiKaraage/ZenMods](https://github.com/KiKaraage/ZenMods) - 原 Zen Context Menu 作者
- [qumeqa/floating-findbar](https://github.com/qumeqa/floating-findbar) - 原 Floating Findbar 作者
- 本项目遵循 [MIT 许可证](LICENSE)。