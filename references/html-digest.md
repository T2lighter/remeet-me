# HTML 沉淀（归档后生成）

> 本文件由 SKILL.md 按需加载：归档五步完成、准备生成 HTML 时读。访谈中不读。

## 1. 何时生成

- 用户选「归档」，五步完成后，默认生成一份。
- 用户说「这次不要 HTML」→ 跳过，不追问。
- 用户单独点单「给我沉淀一份」→ 已归档就生成到 `archive/`；尚未归档就先问是否归档，归档后再生成。
- 「丢弃/继续」→ 不生成。

## 2. 命名与位置

- `archive/YYYY-Wnn-主题-沉淀.html`
- 同一期同主题第二次归档：`YYYY-Wnn-主题-Part2-沉淀.html`，再冲突顺延 `-Part3`。
- 不覆盖已有文件；同名同内容 → 跳过；内容不同 → 另存 `YYYY-Wnn-主题-Part2-沉淀.html`。
- 用户明确要「一周合并版」时：`YYYY-Wnn-合并-沉淀.html`，合并同期快照；不覆盖单次版。

## 3. 结构

1. eyebrow：`自我采访 · 周记沉淀`
2. h1：本期主题，4–10 字，用户原词优先
3. meta：`2026 年 10 月 19—25 日｜访谈 N 问`；不写期号、路径
4. epigraph：一句用户原话 + 日期
5. `主线串联`：3–8 段。每段 h3 小标题 + 1–2 段叙述 + 1 句原话引用；按时间或主题推进，讲故事，不写摘要
6. `关键词`：12–24 个，3–6 个 core；用用户自己的名字；不造词
7. `要点`：6–10 条，每条一句；加粗关键词；不灌鸡汤
8. `未决`：5–8 个开放问题；不写答案
9. 收尾：一句用户原话 + 来源
10. footer：日期范围 + `引语皆为他当时的原话｜AI 提炼处可推翻`；不写路径、期号、文件名

## 4. 视觉

- 单文件 HTML，内联 CSS；不引用外部字体、CDN、图片、脚本。
- 纸色 `#F6F3EC`，墨色 `#2B2822`，强调 `#A6503E`；衬线字体栈。
- `max-width:700px`，正文 18px/2.05；移动端和打印媒体查询。
- 标题、引用、关键词的样式沿用下方骨架；不加动画。

## 5. 行文

- 引语逐字来自 progress / report / question-log；不改写、不补停顿。
- AI 归纳标 `AI 提炼｜可推翻`；不诊断、不贴标签。
- 非引语正文直接叙述事实和变化；「不是 A 而是 B」、三项排比、「真正 / 本质 / 关键 / 标志着」这类句式只在引语里保留。
- 引语里允许用户自己的对比和口语；不改。
- 不出现索引、快照、归档、期号、路径、`.tmp` 等后台词。
- 第三方敏感信息默认用角色称呼；用户明确要求才写细节。

## 6. 生成流程

1. 归档五步完成后再写；材料都在上下文里，不额外读历史。
2. 选 3–6 个 movement；每个 movement 配一句原话。
3. 写 `archive/...-沉淀.html.tmp`。
4. 按第 7 节自检；通过后 `mv -f` 成正式文件。
5. 写失败删不完整 `.tmp`；完整 `.tmp` 但 `mv` 失败 → 保留，下次只重试 `mv`。
6. HTML 失败不影响归档完成；如实说「这次沉淀没生成，下次补」，不把半份 HTML 当成品。

## 7. 自检

- [ ] 单文件能直接打开；无外部请求。
- [ ] 10 个结构块齐全。
- [ ] 每个 movement 至少 1 句原话；引语能在 progress / report / question-log 找到。
- [ ] AI 归纳标了「可推翻」。
- [ ] 正文和尾注没有后台词、路径、期号。
- [ ] 没有诊断、标签、鸡汤。
- [ ] 非引语正文没有「不是 A 而是 B」；排比不超过 1 处。
- [ ] 文件 10–22KB；手机宽度和打印预览正常。

## 8. 骨架

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>2026 · 主题</title>
<style>
  :root{--paper:#F6F3EC;--ink:#2B2822;--soft:#4A453B;--muted:#8A8375;--hairline:#D9D2C2;--accent:#A6503E;}
  *{margin:0;padding:0;box-sizing:border-box;}
  body{font-family:"Noto Serif SC","Source Han Serif SC","Songti SC",serif;color:var(--ink);background:var(--paper);max-width:700px;margin:0 auto;padding:80px 32px 100px;font-size:18px;line-height:2.05;letter-spacing:.02em;}
  .eyebrow{font-size:13px;font-weight:600;letter-spacing:.42em;color:var(--muted);text-align:center;margin-bottom:28px;}
  h1{font-size:42px;font-weight:700;letter-spacing:.14em;text-align:center;margin-bottom:20px;}
  .meta{font-size:14px;color:var(--muted);text-align:center;letter-spacing:.12em;margin-bottom:58px;}
  .epigraph{text-align:center;font-size:19px;font-weight:600;line-height:2.15;max-width:570px;margin:0 auto 14px;}
  .epigraph-src{text-align:center;font-size:13px;color:var(--muted);letter-spacing:.2em;margin-bottom:66px;}
  .rule{border:none;border-top:1px solid var(--hairline);margin:0 auto 66px;width:56px;}
  h2{font-size:18px;font-weight:700;letter-spacing:.3em;margin:70px auto 34px;text-align:center;}
  h2 .part{display:block;font-size:12px;letter-spacing:.5em;color:var(--muted);margin-bottom:10px;font-weight:500;}
  .movement{margin-bottom:52px;}
  .movement h3{font-size:22px;font-weight:700;letter-spacing:.12em;margin-bottom:16px;}
  .movement h3 .num{color:var(--accent);margin-right:14px;}
  .movement p{text-align:justify;color:var(--soft);font-size:17px;margin-bottom:12px;}
  blockquote{margin:20px 0;padding:6px 0 6px 22px;border-left:3px solid var(--accent);font-size:19px;font-weight:650;line-height:2;}
  .keywords{display:flex;flex-wrap:wrap;justify-content:center;gap:14px 12px;margin-top:40px;}
  .keywords span{font-size:15px;font-weight:600;letter-spacing:.14em;color:var(--soft);border:1px solid var(--hairline);border-radius:2px;padding:7px 16px;background:rgba(255,255,255,.4);}
  .keywords .core{color:var(--accent);border-color:rgba(166,80,62,.4);font-weight:700;}
  .points{margin-top:40px;}
  .point{display:flex;gap:20px;margin-bottom:26px;}
  .point .pn{flex:none;width:34px;color:var(--accent);font-size:16px;font-weight:700;}
  .point .pt{text-align:justify;color:var(--soft);font-size:17.5px;}
  .hooks{margin-top:76px;padding-top:44px;border-top:1px solid var(--hairline);}
  .hook{display:flex;gap:18px;margin-bottom:18px;font-size:16.5px;color:var(--soft);}
  .hook .dot{color:var(--accent);}
  .closing{text-align:center;font-size:20px;font-weight:650;line-height:2.15;margin-top:48px;}
  .closing-src{text-align:center;font-size:13px;color:var(--muted);letter-spacing:.2em;margin-top:8px;}
  footer{margin-top:84px;padding-top:26px;border-top:1px solid var(--hairline);font-size:13px;color:var(--muted);text-align:center;line-height:2.1;}
  @media(max-width:480px){body{padding:60px 22px 80px;font-size:17px;}h1{font-size:30px;}blockquote{font-size:18px;}.movement h3{font-size:19px;}}
  @media print{body{padding:40px 20px;}}
</style>
</head>
<body>
<div class="eyebrow">自我采访 · 周记沉淀</div>
<h1>主题</h1>
<div class="meta">2026 年 10 月 19—25 日｜访谈 N 问</div>

<p class="epigraph">「一句用户原话」</p>
<div class="epigraph-src">—— 他，2026-10-25</div>
<hr class="rule">

<h2><span class="part">主 线 串 联</span>一句小标题</h2>
<div class="movement">
  <h3><span class="num">一</span>小标题</h3>
  <p>叙述。</p>
  <blockquote>「用户原话」</blockquote>
</div>

<h2><span class="part">关 键 词</span>他自己起的名字</h2>
<div class="keywords"><span class="core">原词</span><span>原词</span></div>

<h2><span class="part">要 点</span>带走的话</h2>
<div class="points">
  <div class="point"><div class="pn">一</div><div class="pt">一句要点。</div></div>
</div>

<div class="hooks">
  <div class="hook"><span class="dot">○</span><span>一个开放问题。</span></div>
  <div class="closing">「收尾原话」</div>
  <div class="closing-src">—— 他，日期</div>
</div>

<footer>这场对话发生在 2026 年 10 月 19—25 日<br>引语皆为他当时的原话 ｜ AI 提炼处可推翻</footer>
</body>
</html>
```
