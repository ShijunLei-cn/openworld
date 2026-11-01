# GPT 龙娘 · 汉服皮肤初稿

以用户提供的白发紫瞳龙娘三视图为角色参考，参照 [weit0529/gpt-pet](https://github.com/weit0529/gpt-pet) 所述 GPT 娘形象，并以本工作区鲸鱼娘为配套风格参考。保留白发、呆毛、龙角、尖耳、紫色龙翼、龙尾与盘结流苏，服饰加入交领、宽袖、腰封与浅紫纹样。图片均由内置 imagegen 生成或编辑。

## 文件

- `dragon-girl-original-reference-study-a.png`：用户选定的 A 稿，仅以用户指定原版四方向图作为图像输入，保留淡紫配色与细节；仍需目视检查动画和最终画面尺寸。
- `dragon-girl-atlas-study-a.json`、`preview-atlas-study-a.js`：A 稿的 16 帧 Phaser 坐标与预览数据。分隔线按透明度大于 32 的像素检查，低透明度边缘可能仍有残留。
- `dragon-girl-original-reference-study-b.png`：同一原图的另一张探索稿。
- v2 图片已由用户删除，剩余 `dragon-girl-phaser-atlas-v2.json` 和 `preview-atlas-v2.js` 不再被预览使用；v3 图片当前也不在素材目录中。
- `dragon-girl-hanfu-4x4-v1.png`：1287×1222 透明四方向源图；从上到下正面、左侧、背面、右侧，每行四帧。帧为 AI 生成的近似动作，连贯性待视觉验收。
- `dragon-girl-phaser-atlas.json`：16 个命名帧（`down_0`—`down_3`、`up_0`—`up_3`、`left_0`—`left_3`、`right_0`—`right_3`），图像边界不等宽，使用单独坐标和统一逻辑画布。
- `preview.html`：本地独立预览，默认显示 A 稿四方向，允许对照原版和查看三种表情，可切换 64、32、16 像素画布；依赖同目录的两个预览数据脚本和对应 PNG 文件。
- `dragon-girl-portrait-neutral.png`、`dragon-girl-portrait-happy.png`、`dragon-girl-portrait-worried.png`：平静、高兴、担心三张透明对话立绘，后两张以第一张为基础编辑；生成过程可能引入表情以外的细微差异。
- `prompts.md`：参考来源和生成提示词。

## 使用边界

源图不是原生 16×16 像素帧；预览只是实时缩放。四帧存在造型及动作变化，低分辨率辨识度与动作连贯性需要视觉检查和进一步像素精修。分帧坐标选择了透明度大于 32 的像素为空的分隔线；低透明度边缘仍可能存在。Phaser 图集与 OpenWorld 现有露米一行四格加载方式不同；本次只制作独立素材，没有接入游戏或运行游戏验收。

参考仓库 README 称 MIT 许可覆盖其代码、文档及提供的宠物图集和展示素材，并署名素材图片来源于社区创作者 @ZipZipPipe 和 @这个刀子真甜；用户提供的三视图为单独参考图，不假定它就是该仓库发布的图集。保留出处以便后续整理素材清单。
