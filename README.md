# K12 English Learning Skill

面向中国 K12 学生的英语学习 Skill。它把“教材版本识别、年级学段判断、预习、重点内容、考试、错题本、复盘”等能力组织成一条完整学习闭环，适合用于校内同步、单元预习、考试备考、错题整理和长期提分规划。

> 说明：本 Skill 以国家课程目标、常见中小学英语教材结构和公开可见的教培学习方法为参考，不复制或声称拥有新东方、学而思、猿辅导等机构的私有课程大纲。

## 目录结构

```text
k12-english-learning/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── curriculum-framework.md
    ├── textbook-selection.md
    ├── learning-workflows.md
    └── output-templates.md
```

文件说明：

- `SKILL.md`：Skill 主控文件，定义触发条件、总流程和内部模块。
- `agents/openai.yaml`：界面展示与默认调用提示。
- `references/curriculum-framework.md`：中小学英语学段、课程目标和难度控制。
- `references/textbook-selection.md`：出版社/教材版本识别逻辑。
- `references/learning-workflows.md`：学情诊断、预习、重点、考试、错题本、复盘等工作流。
- `references/output-templates.md`：输出模板，包括预习、考试、错题、周复盘等。

## 安装步骤

### 方法一：复制到 Codex Skills 目录

将整个 `k12-english-learning` 文件夹复制到 Codex 的 skills 目录：

```powershell
Copy-Item -Recurse -LiteralPath "D:\code\2026\k12-english-learning" -Destination "C:\Users\yun\.codex\skills"
```

如果目标目录已存在，可以先备份旧版本，再覆盖更新：

```powershell
Copy-Item -Recurse -Force -LiteralPath "D:\code\2026\k12-english-learning" -Destination "C:\Users\yun\.codex\skills"
```

### 方法二：从压缩包安装

如果你使用的是压缩包：

```powershell
Expand-Archive -LiteralPath "D:\code\2026\k12-english-learning-skill.zip" -DestinationPath "C:\Users\yun\.codex\skills"
```

## 校验步骤

安装后可运行校验脚本：

```powershell
python -X utf8 C:\Users\yun\.codex\skills\.system\skill-creator\scripts\quick_validate.py C:\Users\yun\.codex\skills\k12-english-learning
```

预期输出：

```text
Skill is valid!
```

如果不用 `-X utf8`，Windows 环境下可能因为中文内容和 GBK 默认编码出现读取错误；这通常不是 Skill 内容问题。

## 运行方式

在 Codex 对话中直接点名调用：

```text
用 $k12-english-learning 给六年级人教版英语 Unit 3 做预习、重点、练习和复盘方案。
```

也可以不显式点名，只要问题包含 K12 英语学习、教材版本、预习、考试、错题本、复盘等触发场景，Codex 通常会自动使用该 Skill。

## 在 WorkBuddy 中使用

WorkBuddy 支持通过技能市场添加和上传本地 Skill。推荐直接使用本项目打包好的 `k12-english-learning-skill.zip`，这样可以一次导入 `SKILL.md`、`agents/openai.yaml` 和所有 `references` 文件。

### WorkBuddy 安装步骤

1. 打开 WorkBuddy。
2. 进入技能市场或技能管理页面。
3. 点击“添加技能”或“上传技能”。
4. 选择本地压缩包：

```text
D:\code\2026\k12-english-learning-skill.zip
```

5. 等待 WorkBuddy 完成导入。
6. 在技能列表中确认出现 `K12 English Learning` 或 `k12-english-learning`。
7. 启用该 Skill。
8. 新建一个任务或对话，在提示词中显式写入：

```text
使用 k12-english-learning Skill，帮我按教材、年级、预习、重点、考试、错题本和复盘顺序制定英语学习方案。
```

如果 WorkBuddy 的界面文案发生变化，以页面中的“添加技能 / 上传技能 / 导入本地技能 / 启用技能”等同类入口为准。

### WorkBuddy 推荐任务写法

在 WorkBuddy 中，建议把需求写成“背景 + 目标 + 调用顺序 + 输出要求”。

```text
使用 k12-english-learning Skill。

学生背景：
- 年级：七年级上
- 教材：外研版新标准英语
- 单元：Module 1 My classmates
- 当前问题：单词能认，但自我介绍说不完整；语法里 be 动词容易错
- 目标：完成本模块预习、重点梳理、单元测准备、错题本和一周复盘

请按以下顺序输出：
1. 教材版本判断
2. 年级/学段目标
3. 学情诊断
4. 预习计划
5. 重点内容
6. 专项突破
7. 单元测训练
8. 错题本模板
9. 一周复盘
10. 家长反馈
```

### WorkBuddy 演示案例

#### 演示输入

```text
使用 k12-english-learning Skill。

请给七年级上外研版新标准英语 Module 1 My classmates 做一套完整学习方案。

学生情况：
- 能背部分单词，但不会自然介绍自己
- be 动词 am/is/are 经常混用
- 阅读题能看懂大意，但容易漏掉姓名、年龄、城市等细节
- 每天可学习 25 分钟

请严格按顺序调用：
出版社选择 → 年级判断 → 学情诊断 → 预习 → 重点内容 → 专项突破 → 考试 → 错题本 → 复盘 → 家长反馈。
```

#### 演示输出节选

```markdown
**1. 教材版本判断**
- 年级/册次：七年级上
- 最可能版本：外研版新标准英语
- 置信度：高
- 判断依据：用户提供了“外研版新标准英语”“Module 1 My classmates”等信息
- 下一步：按七年级上 Module 1 的主题“自我介绍与同学信息”设计学习闭环

**2. 年级/学段目标**
- 学段：初中起始阶段
- 语言目标：能用简单句介绍姓名、年龄、城市、班级和朋友
- 语法目标：正确使用 am/is/are
- 阅读目标：能定位人物信息，如 name, age, city, class
- 写作目标：能写 60 词左右的自我介绍或同学介绍

**3. 学情诊断**
- 主要短板：
  - 词汇：认识单词，但放进句子时不熟练
  - 语法：be 动词人称匹配不稳定
  - 阅读：细节定位习惯不足
- 优先级：
  1. 先稳定 I am / He is / She is / They are
  2. 再练自我介绍句型
  3. 最后做阅读细节定位和短文写作

**4. 预习计划**
- 时间：25 分钟
- 词汇先认：name, age, city, class, friend, student, teacher
- 核心句型：
  - My name is...
  - I am from...
  - I am ... years old.
  - He/She is my classmate.
- 语法观察：I 搭配 am；he/she 搭配 is；we/they 搭配 are
- 自测题：
  1. 用英文说“我来自北京”
  2. 判断：He am twelve. 是否正确？
  3. 从短文中圈出人物的城市和年龄

**5. 重点内容**
- 必会词汇：name, age, city, class, friend, China, England
- 高频表达：be from, years old, in Class One
- 语法重点：be 动词和主语匹配
- 易错点：
  - I is 错，应为 I am
  - He am 错，应为 He is
  - They is 错，应为 They are

**6. 专项突破**
- 专项：be 动词 am/is/are
- 规则：
  - I am
  - He/She/It is
  - We/You/They are
- 练习：
  1. I ___ from Shanghai.
  2. She ___ my friend.
  3. They ___ in Class Two.
- 输出任务：用 4 句话介绍自己和一位同学

**7. 单元测训练**
- 5 分钟：词汇英汉互译
- 5 分钟：am/is/are 填空
- 5 分钟：阅读细节定位
- 10 分钟：写一段自我介绍
- 考前 checklist：
  - be 动词是否和主语一致
  - 年龄表达是否使用 years old
  - 阅读答案是否能在原文中找到证据

**8. 错题本模板**
- 错题：He am from Beijing.
- 错因分类：语法错误
- 正确规则：He 搭配 is
- 正确答案：He is from Beijing.
- 复测题：
  1. She ___ from London.
  2. They ___ my classmates.
- 复习日期：明天、3 天后、7 天后、14 天后

**9. 一周复盘**
- 已掌握：能用 My name is... 和 I am from... 做基础介绍
- 仍不稳定：he/she 与 is 的匹配
- 下周重点：人物介绍短文和阅读细节题
- 复习安排：
  - 周一：be 动词错题复测
  - 周三：阅读定位练习
  - 周五：完成 60 词自我介绍

**10. 家长反馈**
- 孩子能完成基础自我介绍，但语法准确性还需要巩固
- 家庭配合建议：每天用 2 分钟让孩子说 3 句自我介绍
- 下周目标：能准确介绍自己和一位同学，并减少 be 动词错误
```

### WorkBuddy 使用小技巧

- 第一次运行时，尽量显式写“使用 k12-english-learning Skill”。
- 如果只想做某一步，可以写“只调用错题本模块”或“只生成预习计划”。
- 如果要连续学习多个单元，可以让 WorkBuddy 每次先输出“本次假设”，再进入学习方案。
- 如果要给家长看，要求输出“家长反馈版”；如果要给老师看，要求输出“教学反馈版”。

## 推荐调用顺序

完整学习闭环建议按以下顺序调用：

1. 出版社选择 / 教材识别
2. 年级 / 学段判断
3. 学情诊断
4. 预习
5. 重点内容
6. 课堂同步 / 专项突破
7. 考试训练
8. 错题本
9. 复盘
10. 家长或老师反馈

这个顺序的核心逻辑是：先确认“学什么”，再确认“谁来学”，然后决定“怎么学、怎么练、怎么测、怎么改”。

## 完整案例展示

### 案例背景

学生信息：

- 年级：六年级上
- 地区：北京
- 教材：人教 PEP 小学英语
- 单元：Unit 3 My weekend plan
- 学习目标：提前预习本单元，掌握重点句型，准备单元测
- 当前问题：词汇会背但不会用，阅读题容易漏细节，作文句子比较单一
- 每天可用时间：20 分钟

### 第 1 步：调用出版社选择 Skill

用户输入：

```text
用 $k12-english-learning 先帮我判断教材版本：六年级上，北京，书上写着 PEP，小学英语，Unit 3 My weekend plan。
```

期望输出示例：

```markdown
**教材判断**
- 年级/册次：六年级上
- 最可能版本：人教 PEP 小学英语
- 置信度：高
- 判断依据：用户提供了 PEP、小学英语、六年级上、Unit 3 My weekend plan 等信息
- 还缺的信息：如果需要完全确认，可补充封面或目录页
- 下一步：按人教 PEP 六年级上 Unit 3 做单元预习和重点梳理
```

### 第 2 步：调用年级 / 学段 Skill

用户输入：

```text
继续按六年级上学生的水平，判断这个单元应该达到什么学习目标，不要太难。
```

期望输出示例：

```markdown
**年级目标**
- 学段：小学高段
- 核心目标：能围绕周末计划进行问答和简单表达
- 词汇目标：能认读、理解并使用活动类短语
- 句型目标：能使用 What are you going to do? I am going to...
- 阅读目标：能从短文中找出人物、时间、地点和活动安排
- 写作目标：能写 5-6 句话描述自己的周末计划
- 难度控制：少讲抽象语法术语，多用替换练习和生活化表达
```

### 第 3 步：调用学情诊断 Skill

用户输入：

```text
孩子词汇能背但不会用，阅读题经常漏细节，作文句子比较单一。请先做学情诊断。
```

期望输出示例：

```markdown
**学情诊断**
- 年级与教材：六年级上，人教 PEP Unit 3
- 当前目标：完成单元预习并准备单元测
- 当前表现：词汇记忆尚可，但迁移使用不足
- 主要短板：
  - 词汇：会认不会造句
  - 阅读：没有带问题找证据的习惯
  - 写作：句型变化少，内容展开弱
- 优先级：
  1. 先把活动短语放进句型中使用
  2. 再训练阅读定位细节
  3. 最后做 5-6 句小作文输出
- 本周关键动作：每天 20 分钟，完成“词汇使用 + 阅读证据 + 小段写作”闭环
```

### 第 4 步：调用预习 Skill

用户输入：

```text
请生成 Unit 3 的预习计划，控制在 20 分钟内。
```

期望输出示例：

```markdown
**预习计划**
- 对应教材：人教 PEP 六年级上 Unit 3 My weekend plan
- 本课主题：周末计划
- 预习目标：能听懂、认读并初步使用“将要做某事”的表达
- 词汇先认：
  - visit my grandparents
  - see a film
  - take a trip
  - go to the supermarket
  - dictionary, comic book, word book, postcard
- 核心句型：
  - What are you going to do?
  - I am going to see a film.
  - Where are you going?
  - When are you going?
- 语法观察：be going to 表示计划或打算
- 课文预测：本单元可能会谈论人物的周末安排、地点和时间
- 自测题：
  1. How do you say “看电影” in English?
  2. What are you going to do this weekend?
  3. Where are you going this Saturday?
  4. 找出一句表示计划的英文句子
  5. 用 I am going to... 造一个句子
- 上课重点听：老师如何区分 what, where, when 三类问题
```

### 第 5 步：调用重点内容 Skill

用户输入：

```text
请提炼这个单元的重点内容和易错点。
```

期望输出示例：

```markdown
**重点内容**
- 必会词汇：film, trip, supermarket, evening, tomorrow, tonight, dictionary, postcard
- 高频短语：see a film, take a trip, visit grandparents, go to the supermarket
- 核心句型：
  - What are you going to do?
  - I am going to + 动词原形.
  - Where are you going?
  - When are you going?
- 语法重点：be going to + 动词原形，表示计划
- 阅读/听力策略：听到人物后，注意对应的时间、地点和活动
- 写作/口语输出：用 5 句话介绍自己的周末计划
- 易错点：
  - I am going to go to... 中不要漏掉动词
  - What/Where/When 的回答方向不同
  - going to 后面接动词原形
- 今日练习：用 4 个活动短语分别造句
```

### 第 6 步：调用课堂同步 / 专项突破 Skill

用户输入：

```text
针对“词汇会背但不会用”，做一个 15 分钟专项突破。
```

期望输出示例：

```markdown
**词汇使用专项**
- 目标：把活动短语放入真实句型中使用
- Step 1 词汇分组：
  - 出行：take a trip
  - 娱乐：see a film
  - 购物：go to the supermarket
  - 家庭：visit my grandparents
- Step 2 句型替换：
  - I am going to see a film.
  - I am going to take a trip.
  - I am going to visit my grandparents.
- Step 3 问答练习：
  - What are you going to do?
  - I am going to...
- Step 4 小输出：
  - This weekend, I am going to see a film. I am going with my friend.
- 小测：随机给 3 个中文短语，学生用英文说完整句子
```

### 第 7 步：调用考试 Skill

用户输入：

```text
请按单元测标准，设计一份 20 分钟考前训练。
```

期望输出示例：

```markdown
**考试备考方案**
- 考试类型：Unit 3 单元测
- 目标：稳定掌握词汇、句型和基础阅读
- 当前失分点：词汇使用、阅读细节、写作句型单一
- 优先突破题型：
  1. 词汇短语英汉互译
  2. 句型问答
  3. 阅读细节题
  4. 小作文
- 每日安排：
  - 5 分钟：短语听写或看图说句
  - 5 分钟：What/Where/When 问答
  - 5 分钟：短文找细节
  - 5 分钟：写 3-5 句话
- 限时训练：阅读题每篇控制在 4 分钟
- 错题复测：第二天重做错题变式
- 考前 checklist：
  - be going to 后接动词原形
  - 问什么答什么
  - 阅读题必须回原文找证据
```

### 第 8 步：调用错题本 Skill

用户输入：

```text
错题：What are you going to do tonight? 孩子回答 I go to see a film. 请整理错题本。
```

期望输出示例：

```markdown
**错题记录**
- 题型：句型问答
- 原因分类：语法 + 句型迁移
- 错因说明：题目问的是计划，回答需要使用 be going to；孩子用了普通现在时 I go
- 正确规则：be going to + 动词原形，表示将要做某事
- 正确答案：I am going to see a film.
- 类似例句：
  - I am going to visit my grandparents.
  - I am going to go to the supermarket.
- 复测题：
  1. What are you going to do tomorrow?
  2. What are you going to do this weekend?
- 复习日期：明天、3 天后、7 天后、14 天后
```

### 第 9 步：调用复盘 Skill

用户输入：

```text
根据这周的学习，做一份一周复盘和下周计划。
```

期望输出示例：

```markdown
**一周复盘**
- 本周学了什么：Unit 3 的活动短语、be going to 句型、What/Where/When 问答
- 已掌握：
  - 能认读大部分活动短语
  - 能用 I am going to... 说简单计划
- 仍不稳定：
  - 回答问题时有时不用 be going to
  - 阅读题容易不回原文找证据
  - 作文句子之间缺少连接
- 典型错题：What are you going to do tonight? 回答成 I go...
- 下周重点：
  1. 每天 3 句 be going to 口头输出
  2. 每次阅读题圈出证据句
  3. 写一篇 5-6 句 My weekend plan
- 复习安排：
  - 周一：重做错题
  - 周三：做变式问答
  - 周五：完成小作文
  - 周日：单元混合小测
```

### 第 10 步：调用家长反馈 Skill

用户输入：

```text
请把上面的情况整理成家长能看懂的反馈。
```

期望输出示例：

```markdown
**家长反馈**
- 孩子当前状态：词汇记忆基础不错，但还需要把词汇放进完整句子中使用
- 本周进步：已经能围绕周末计划进行简单表达
- 主要困难：
  - 回答计划类问题时容易漏掉 be going to
  - 阅读时有时凭印象答题，没有回原文找依据
  - 写作内容偏简单
- 家庭配合建议：
  - 每天用 2 分钟问一句 What are you going to do...?
  - 鼓励孩子说完整句，不只说短语
  - 阅读题做完后让孩子指出答案来自哪一句
- 下周目标：能独立写出 5-6 句话的 My weekend plan
```

## 可复制 Prompt 模板

### 单元预习

```text
用 $k12-english-learning 按【年级】【出版社/教材版本】【单元】生成一份预习计划，包含词汇、句型、语法观察、课文预测、自测题和上课重点听。
```

### 重点提炼

```text
用 $k12-english-learning 提炼【年级】【教材版本】【单元/课文】的重点内容，按必会词汇、高频短语、核心句型、语法重点、易错点和练习输出。
```

### 考试备考

```text
用 $k12-english-learning 根据【考试类型】【目标分数】【当前失分点】制定一份考前训练计划，包含题型优先级、限时训练、错题复测和考前 checklist。
```

### 错题本

```text
用 $k12-english-learning 整理下面这道英语错题：题目是【题目】，孩子答案是【错误答案】，正确答案是【正确答案】。请输出错因分类、规则、类似例句、复测题和复习日期。
```

### 周复盘

```text
用 $k12-english-learning 根据本周学习内容【内容】和错题【错题】生成一份一周复盘，包含已掌握、仍不稳定、典型错题、下周重点和复习安排。
```

## 使用建议

- 如果只知道年级，不知道教材，先做“教材待确认”的通用计划。
- 如果有教材封面、目录或单元标题，优先让 Skill 做教材识别。
- 如果目标是提分，先输入试卷或错题，不要直接要求泛泛刷题。
- 如果是小学低年级，优先听说和短句输出，少用抽象语法术语。
- 如果是初中或高中，优先围绕题型、失分点和复测周期设计。
