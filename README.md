# 孙学 × 黄毛学 · 访谈行动助手

**把听懂的观点变成一个可检查的行动，再用真实反馈调整。**

这是一个独立制作的Agent Skill，依据Alan邵艾伦与孙宇晨的公开访谈整理。版本1.0.0，2026-10-13。采用`SKILL.md`规范，包含心法、执行流程、来源索引和五份通用记录模板。

## 它能做什么

| 请求 | 得到什么 |
|---|---|
| “别人都反对，我该坚持吗？” | 用黄毛学分清自己的目标、评价中的证据与边界，给一个可控行动 |
| “这两个方向怎么选？” | 用孙学比较规则、需求、投入与不确定性，设计一个小实验 |
| “帮我按访谈方法安排这一周” | 在真实时间与预算内，输出任务、成果、验收和调整条件 |
| “复盘今天实际做的事情” | 区分计划和事实，整理日报，提出明天的一项改进 |
| “读我的Notion目标” | 使用已有授权连接读取相关项目；无连接时处理提供的内容 |
| “结合健康记录调整日常活动” | 核对提供的摘要或可读取数据的日期和口径，分析可用部分 |

心法的使用规则由项目整理，不代表嘉宾本人已经提出这份完整Skill或授权本项目。项目与两位嘉宾及其团队无隶属或合作关系。

## 安装到Codex

如果已安装Git，可直接从[公开仓库](https://github.com/uiuier/alan-sun-action-system)安装：

```bash
mkdir -p ~/.agents/skills
git clone https://github.com/uiuier/alan-sun-action-system.git ~/.agents/skills/alan-sun-action-system
```

如果使用GitHub仓库页面的 **Code > Download ZIP**，解压后通常得到`alan-sun-action-system-main`文件夹；先将它改名为`alan-sun-action-system`，再按下面的方法放入技能目录。

下载并解压发布包，将里面的`alan-sun-action-system`完整文件夹放入用户技能目录：

```text
~/.agents/skills/alan-sun-action-system/
```

也可在项目内使用`.agents/skills/alan-sun-action-system/`。这是当前[OpenAI官方技能文档](https://learn.chatgpt.com/docs/build-skills)列示的位置；旧版本使用的目录可能不同，按所在客户端说明处理。

macOS/Linux在解压包所在目录可执行：

```bash
mkdir -p ~/.agents/skills
cp -R ./alan-sun-action-system ~/.agents/skills/
```

已有同名技能时先备份，再替换。进入Codex的新聊天，尝试：

```text
用 $alan-sun-action-system 帮我把一个正在犹豫的目标变成这周能验证的小实验。
```

也可使用客户端的技能选择入口。修改后若未显示，重启客户端再检查。结构遵循Agent Skills规范，其他客户端的安装位置和实际兼容性需按各自文档确认。本包没有运行Claude Code等其他客户端的端到端测试。

不支持本地Skill的纯聊天环境，可以提供`SKILL.md`与本次所需参考文件作为上下文；这属于提示词使用，不等于安装了原生技能。

## 第一次用，给这些信息就够

```text
我想解决：……
当前限制：可用时间……，预算……，已有进度……
我想要：一个行动 / 本周计划 / 日报 / 复盘 / 两个方向的比较
```

有多项独立时间预算时分别说明。没有健康、财务或Notion资料也可以从一个具体问题开始。

## 快速演示

```text
用 $alan-sun-action-system。
我想练习技术文档整理，但朋友说学AI没用。
这周可以额外投入三次，每次25分钟，没有新增预算。
请用黄毛学与孙学给一个可验收的小实验，并说明什么反馈会让你改变建议。
```

一个合格结果应包含自己的目标、值得检验的意见、75分钟内的具体步骤、可检查作品和调整条件；不会仅用赞美或模仿名人的语气代替方案。

## 数据与自动化

Skill提供方法与模板，不包含账号、凭据、数据采集服务器或常驻程序。Notion等来源依赖用户已有连接和权限；健康数据依赖所在客户端实际支持或用户提供的摘要；后台日报需要另行设置并验证自动化。

个人档案和真实记录保存到用户选择的资料位置，不放在公开Skill包内。时间不够、数据缺失或连接不存在时，输出明确可实施的部分和缺口。

## 包含的文件

```text
alan-sun-action-system/
├── SKILL.md
├── agents/openai.yaml
├── references/
│   ├── mindsets.md
│   ├── workflows.md
│   └── sources.md
├── assets/templates/
│   ├── profile.md
│   ├── daily.md
│   ├── weekly.md
│   ├── decision.md
│   └── experiment.md
├── README.md
├── VALIDATION.md
└── LICENSE
```

## 来源与使用

[原视频](https://www.youtube.com/watch?v=0Z-vhBvBmUY) · [用户指定的访谈转录](https://github.com/AayuBal/shaoailun-sunyuchen-podcast/blob/main/%E5%85%A8%E6%96%87.md) · [时间戳与整理说明](references/sources.md)。

本项目仅保存有限归纳与链接，没有打包访谈全文、视频或第三方Skill代码。转录有重叠与说话人错位，引用人物原话时需要回听原视频。

结构校验和三次独立行为试用已完成，具体结果与未覆盖范围见 [验证记录](VALIDATION.md)。示例和验证输入都是演示资料，不是用户的收益、健康或学习成效。

原创技能指令、模板和文档采用MIT许可证，允许使用、修改与再分发，保留许可证即可。第三方视频、姓名和原材料仍归各自权利人；MIT许可不表示取得人物授权或原材料再许可。

适合介绍为“基于公开访谈整理的个人行动Skill”。对外说明实际功能和连接条件，不把它包装成训练过的名人模型或已经取得用户成效的产品。
