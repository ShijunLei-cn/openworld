# 鲸鱼娘四方向像素素材

用户指定以 [鲸鱼娘开源资产库的 Q 版参考图及提示词](https://treapgogo.github.io/deepseek-whale-girl/index.html)为基础，结合 OpenWorld 露米的像素风格制作。源图使用内置 imagegen 生成；这是对指定参考的演绎，具体参考图的授权范围仍以其来源说明为准，不在这里宣称素材为 CC0。用户当前只喜欢 v1（对话中称图二），后续以 v1 为造型基准。

## 文件

- `whale-girl-source-4x4-v1.png`：透明 PNG 源图，1287×1222；从上到下依次为正面、左侧、背面、右侧，每行四帧。四帧是 AI 生成的近似动作，需要进一步人工检查连贯性。
- `whale-girl-source-small-v3.png`：尝试面向小尺寸简化的另一版透明源图，1287×1222，方向与帧排列同 v1；实际生成结果仍不是原生 16×16 像素画。
- `whale-girl-source-small-navy-v6.png`：以用户指定的 v1 深蓝像素图与中性立绘为配色参考，统一四方向发色、鲸尾与服饰后重新生成的小尺寸探索稿。四周和帧间保留透明间隔；生成过程中造型边缘和细节也有变化，不是逐像素换色。
- `whale-girl-portrait-neutral.png`、`whale-girl-portrait-happy.png`、`whale-girl-portrait-worried.png`：透明立绘，分别是平静、高兴和担心表情，均为 1199×1312；后两张在平静立绘基础上使用 imagegen 修改表情。
- `whale-girl-phaser-atlas.json`：对应 v1 的 Phaser JSON Hash 图集，提供 `down_0`–`down_3`、`up_0`–`up_3`、`left_0`–`left_3`、`right_0`–`right_3` 命名帧；依据源图分帧坐标并统一逻辑画布和脚部锚点。
- `whale-girl-small-v3-phaser-atlas.json`：对应小尺寸探索稿的 Phaser 命名帧坐标。
- `whale-girl-small-navy-v6-phaser-atlas.json`：对应深蓝小尺寸探索稿的 Phaser 命名帧坐标。
- `preview.html`：双击打开的独立预览，只显示用户选定的 v1 图集。左侧直接从原图按比例绘制，右侧先缩成 16 像素高再放大；可切换模拟镜头倍数并对照四方向。预览依赖同目录的 v1 PNG、三张立绘与 `preview-atlas.js`，不改动图片文件。
- `preview-atlas.js`、`preview-atlas-small-v3.js`、`preview-atlas-small-navy-v6.js`：分别由 JSON 图集同步生成的数据；当前预览只使用 v1 对应的 `preview-atlas.js`。
- `prompts.md`：各次生成与表情编辑使用的提示词及参考来源。

## 接入范围

v1 是 1287×1222 图集，而非每帧原生 16×16。预览按 16 世界单位高度、约 19.2 单位宽度等比例显示，并模拟 1–4 倍镜头；图中画布像素不等于游戏最终运行结果。研究副本正常镜头的 `fitZoom()` 为 2–4 倍，实际效果还取决于画布分辨率、镜头和屏幕；输出像素有限时细节仍会丢失。Phaser 可以缩放精灵，但 OpenWorld 现有的露米加载器使用一行四格，其他普通角色加载器使用等宽网格，均不会直接读取这份非等宽图集；替换露米需后续适配资源加载和动作映射。四帧动作差异很小，动画连贯性仍需精修。尚未在游戏中运行或验收，未修改游戏代码、正式资源及存档。

## 生成提示概要

以指定 Q 版鲸鱼娘三视图为角色身份参考，以现有露米精灵图为像素风格参考：深蓝至海蓝长发、呆毛、白色女仆发箍、鲸鳍耳、蓝色蝴蝶结、海军蓝女仆裙、白色围裙和粗圆鲸尾；生成正面、侧面、背面和另一侧面，各四帧，透明背景、像素风格、无文字边框。对话立绘在相同角色设定下参考露米现有立绘的构图，随后保持造型并分别改出高兴和担心表情。
