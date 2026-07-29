# 生图提示词模板

每张图单独生成，不要多张拼一张。prompt 用英文，图上标注用中文。

**带角色的图，默认先上传 `assets/character-ref.png` 参考图再发 prompt。** 参考图是角色一致性的第一保障，文字描述只是兜底。

## 主模板（解释图，16:9 / 3:4）

```text
Use the attached image as the EXACT character design reference: keep the same cute chibi/anime girl identity, large warm brown eyes, long dark brown-black hair with wispy bangs, visible pink inner-layer/front hair streaks, light sky-blue T-shirt, soft blush, friendly expressive face, and clean rounded hand-drawn line style.

Generate one standalone {画幅: 16:9 horizontal / 3:4 vertical} Chinese hand-drawn explanatory illustration.

Visual DNA:
Pure white or transparent background. Clean rounded hand-drawn chibi line art, soft pastel coloring, lots of empty white space. Sparse handwritten Chinese annotations in blue/red/black when needed. Preserve the character colors from the reference image, especially the dark hair, pink hair streaks, and light blue T-shirt. No gradients, no heavy shadows, no paper texture, no complex background, no commercial vector style, no PPT infographic look, no realistic UI.

Character:
She must perform the core conceptual action of this image, not decorate the scene. She is an earnest, energetic office worker; the humor comes from the absurd situation, and her reaction to it is genuine (focused, overwhelmed, or proud). Keep the light sky-blue T-shirt and the same cute IP design; no extra fashion details.

Theme:
{这张图的主题}

Structure type:
{结构类型：Workflow / 系统局部 / 前后对比 / 角色状态 / 概念隐喻 / 方法分层 / 地图路线 / 小漫画分镜}

Core idea:
{这张图要表达的核心意思}

Composition:
{具体画面：角色在哪里、正在做什么、主要物件是什么、信息如何流动}

Suggested elements:
{元素1} / {元素2} / {元素3}

Chinese handwritten labels:
{标注词1} / {标注词2} / {标注词3} / {可选标注词4} / {可选标注词5}

Color use:
Dark ink for line art, objects, and ordinary labels. Blue for the main emphasis words, main flow arrows, and paths. Red only for warnings, pitfalls, key results, or emotional points. Pink should primarily appear in the character's hair streaks and should not become the dominant palette.

Constraints:
One image explains only one core structure. Keep the main subject around 40%-60% of the canvas. Preserve at least 35% blank white space. Use at most 5-8 short handwritten Chinese labels. Do not write a title in the top-left corner. Do not write the structure type on the image. Do not make it a formal diagram, course slide, or dense explainer. Invent a fresh visual metaphor for this specific content. It should be clear but not instructional, funny but not childish, hand-drawn but clean.
```

## 贴图模式模板

```text
Use the attached image as the EXACT character design reference: keep the same cute chibi/anime girl identity, large warm brown eyes, long dark brown-black hair with wispy bangs, visible pink inner-layer/front hair streaks, light sky-blue T-shirt, soft blush, friendly expressive face, and clean rounded hand-drawn line style.

Generate one standalone hand-drawn illustration on a pure white background.

Subject: {角色动作，如"角色认真敲电脑" / 单个物件}

Style: clean rounded hand-drawn chibi sticker illustration, pure white or transparent background, soft pastel coloring. Preserve dark hair, pink hair streaks, and light blue T-shirt. Up to 3 small mood symbols allowed (sparkles / sweat drop / speed lines) if they serve the emotion. No heavy sticker border, no gradients, no shadows, no background objects, no text (or at most one short Chinese label).

Composition: single centered subject, large white margins on all sides (subject occupies about 50-60% of canvas). Clean edges suitable for cutout use.
```

## 无角色物件图模板

单画物件/图标（不出现角色）时，用贴图模式模板去掉第一段参考图声明，Subject 换成物件即可。粉色禁用（粉色只属于角色头发）。

## 图像编辑提示

去掉多余文字/标题：

```text
Edit the provided image. Remove only the handwritten text "{要删除的文字}" from {位置}. Fill that area with the same clean white background. Preserve everything else exactly: character, labels, line style, composition, aspect ratio, and image quality. Do not add any new text or objects.
```

粉色跑出头发时：

```text
Edit the provided image. The pink color must appear ONLY in the character's inner-hair highlight. Recolor all other pink elements ({说明哪些地方}) to black line art. Preserve everything else exactly.
```

角色跑模时：

```text
Regenerate this illustration with the same composition and meaning, but redraw the character to EXACTLY match the attached character reference: same cute chibi girl face, same large warm brown eyes, same long dark brown-black hair with wispy bangs, same visible pink hair streaks, same light sky-blue T-shirt, same friendly expressive IP design.
```

角色太装饰时：

```text
Regenerate this illustration with the same core meaning and simple layout, but make the character central to the conceptual action. She should be doing the work that explains the idea, not standing beside the diagram. Keep it clean, sparse, black-and-white ink style with only the pink hair highlight as color.
```

角色不够跳时：

```text
Regenerate with the same composition, but draw the character with bolder line weight than the surrounding objects, and slightly larger, so she reads as the protagonist at a glance.
```

## 已知坑（实测沉淀）

- **不要用 "sticker-style" 开头描述整图**：会触发厚白边 + 上色 + 可爱贴纸包先验，压过所有后续描述（2026-07-08 实测翻车）。说 "hand-drawn illustration on pure white background" 就够。
- **ChatGPT 账号 memory 会污染人物形象**（把历史对话里的人物特征混进来）。带角色的图必须上传参考图；不带参考图时在 prompt 里明确 "ignore any saved user preferences or memories about appearance"。
- 中文标注错字率随字数上升，标注能短则短；错得多就减少标注数量重生成。
