# caocao-skills

个人技能（skills）仓库，**同时是一个 DeepSeek Harness 可直接注册的技能源**。

## 结构

```
skills/
├── analyzing-tech-events/    # 新技术事件深度分析（P0-P6 六阶段方法论）
│   ├── SKILL.md
│   ├── references/           # 方法库 / 风格指南 / 完整范例
│   ├── scripts/md_to_pdf.py  # Markdown → PDF（WeasyPrint）
│   └── evals/                # 端到端验证产物
└── caochengxiang-writer/     # 曹丞相公众号写作（阳光极客君子人设）
    ├── SKILL.md              # 含内容安全红线 + 四层自检体系
    └── references/           # 人设素材库 / 名言引用库 / 风格示例库
```

## 在 DeepSeek Harness 中注册（推荐方式）

在 `~/.dsh/profiles/<profile>/cordis.patch.yml`（补丁层）追加：

```yaml
- name: "@deepseek-ai/dsh-skill"
- name: "@deepseek-ai/dsh-skill-filesystem"
  config:
    customSkillDirs:
      - "<本仓库路径>/skills"
```

重启 DSH 后，两个技能进入全局技能目录，随提示词自动触发；目录带热重载监视，修改 SKILL.md 直接生效，无需同步。

## 触发方式

- **分析**：「深度分析这个刚开源的项目 XXX」/「XX开源了怎么看」/「用 analyzing-tech-events 分析」
- **写作**：「用曹丞相的口吻写篇文章」/「帮丞相写篇稿」/「用 caochengxiang-writer 写」
- **串联**：「先用 analyzing-tech-events 深度分析 XXX，然后用 caochengxiang-writer 写成公众号文章」

## 技能简介

### analyzing-tech-events

当全新 IT 技术事件发生（super-agent/大模型/框架开源、重大发布、融资并购）时，产出 8,000-15,000 字深度判断报告——机制（真突破还是新编排）、时机（Why Now）、动机（ACH 竞争性假设矩阵）、冲击（利益相关方地图+二阶传导）、前景（2×2 情景+可证伪预测）。核心纪律：每步结论标证据等级（A 实测/B 一手/C 二手/D 推测）、预测必须可证伪、未实测必须显式降级、交付 PDF 优先失败回退 Markdown。

### caochengxiang-writer

「曹丞相的AI之路」公众号长文。人设：阳光帅气、极客风格、言之有物、幽默风趣、有长者之风和君子之风。特色：内容安全红线（政治敏感严格禁止，最高优先级）、引用纪律（只引出处可查的真实名言，禁止伪托，附三问自检）、亲历细节占位规则（不编造一手经历）、四层自检体系（L1 硬性规则含安全与引用扫描 → L4 活人感终审）、图片全部与内容强相关。

> 旧版 `caocao-writer`（半文半白+毒舌+丞相曰金句）不在本仓库，两者并存于工作区 skills 目录。

## 安装为本机技能（备选方式）

不想走全局注册的话，把 `skills/<技能名>` 文件夹复制到你运行时的技能目录即可。

## License

内容仅供学习交流使用。
