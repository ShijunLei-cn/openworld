# 图像生成提示词与参考

生成工具：Codex 内置 imagegen。输出为透明 PNG。角色参考为用户指定的[鲸鱼娘开源资产库](https://treapgogo.github.io/deepseek-whale-girl/index.html)首页 Q 版三视图，参考 PNG 的 SHA-256 为 `539548DBDF78A6488B9BACA3AF07521FE422C62BD8DEE6E5664A1880754325B6`；风格参考为 OpenWorld 的露米精灵图和立绘。

## 四方向源图 v1

```text
Use case: stylized-concept
Asset type: transparent pixel-art character sprite atlas for a top-down 2D JRPG.
Reference images: Image 1 is the exact user-selected DeepSeek whale-girl character turnaround; preserve her recognizable character identity and costume. Image 2 is the existing game's companion sprite and establishes the target 16-bit pixel scale, dark outlines and chibi proportions, not the character's colors.
Task: Create a clean 4-column by 4-row pixel art atlas of the same whale-girl character for a pixel RPG, with one complete isolated character in each equal-sized invisible square cell. Four character directions, one per ROW, in this exact order from top to bottom: facing camera/front, facing left/profile, facing away/back, facing right/profile. In each row four CELLS are a subtle four-frame gentle floating loop of exactly that same direction. No other objects. Keep character size, baseline and center identical in all cells so that all 16 frames can be sliced on the grid. Leave generous fully transparent padding around the figures inside each cell; no parts touch cell edges.
Appearance: match image 1 closely: deep navy to ocean-blue long hair, small curved ahoge, white ruffled maid headband, side whale-fin ears with blue bows, bright blue eyes, deep-navy and white maid dress with white apron, cobalt bow at collar and the small blue whale on the apron when facing front, thick rounded deep blue whale tail curving behind the skirt, white socks and navy shoes. Preserve the silhouette and fin placements in the back view. Chibi and cute with an expressive, soft face.
Style: genuine hand-drawn retro Japanese RPG pixel art, chunky exact same-sized pixels throughout each figure, hard pixel edges, limited coherent palette with flat color clusters, no smoothing, no gradient airbrushing. Suitable for a 16x16-cell game character; simplify ornament while keeping blue hair, white headband, apron, and whale tail clearly distinguishable at tiny in-game sizes.
Constraints: 16 sprites total, no text, no headers, no frames, no grid lines, no shadows, no decoration outside the characters, no checkerboard or false transparency. Genuine alpha transparency across the entire background and padding. Do not create a 3D render, mockup, interface, character sheet annotations, or a background.
```

## 四方向源图 v2（布局实验，未用于图集）

```text
Use case: stylized-concept.
Asset type: machine-sliceable transparent 4-by-4 sprite sheet for an existing tiny 2D pixel RPG.
Image 1: the whale-girl generated in a previous iteration. Keep her character identity, colors and expression, but REDRAW and rearrange her into the exact grid described below.
Image 2: the source reference for her precise whale-girl hair, costume, fin-ears, maid headband and thick blue tail.
Image 3: the actual existing game atlas; copy ONLY its exact 4x4 organization and tiny 16x16 pixel-art scale, NOT its green zombie characters.
Critical layout: 4 equal WIDTH columns and 4 equal HEIGHT rows filling a perfectly square uncropped transparent canvas. Place a complete whale-girl sprite at the center of each grid cell. COLUMNS from left to right: front/down, back/up, left profile, right profile. ROWS from top to bottom: floating frame 1, frame 2, frame 3, frame 4. Thus each column is an animation of exactly the same pose and direction, with tiny tail or hair movement. All 16 characters are the same size and perfectly centered on the same baseline, within their cell with a few transparent pixels around each body, and NO sprite crosses any cell edge. A program will split the canvas at precisely 25%, 50% and 75%, so visual padding, precise center and equal 4x4 alignment are essential. No grid lines, no text, no margins outside the 4x4 grid.
Draw pixels as precise large, hard-edged blocks, hand-crafted native 16x16 pixel character art, not a polished illustration with a pixel filter. Compact Q version with blue gradient hair simplified to a handful of flat pixel colors, dark outline, white maid hairband, blue fin ears, white apron on navy maid dress, blue-white fish tail, white socks and dark shoes. Keep an attractive expressive face, but simplify detail so it reads at native 16x16. Limited palette, flat pixel clusters, no antialiasing, no shadows, no blur.
Make the entire background and cell padding genuinely transparent; no checkerboard, label, background texture, glow, borders, captions, or extra objects.
```

## 平静立绘

```text
Use case: stylized-concept.
Asset type: transparent-background character portrait for an existing 2D JRPG companion panel.
Reference image 1 is the user's chosen whale-girl character design; she must remain recognizably the same blue-haired whale maid. Image 2 is her pixel-sprite version for the same game skin. Image 3 establishes the existing game's clean portrait framing and visual finish; do not copy Lumi's hair, wings, flower, or clothing.
Create ONE finished, polished waist-up game dialogue portrait of the exact whale-girl from images 1 and 2, naturally matching the game's portrait style and the sprite's identity. Slightly chibi, expressive, warm and charming: a large blue-eyed face, long layered navy-to-ocean-blue hair with a curved ahoge, white ruffled maid headband, whale-fin ears with two blue bows, dark navy and white maid dress, dark blue collar bow with blue jewel, white ruffled apron with a small blue whale motif, and a plump blue whale tail subtly visible curling behind her. Calm friendly closed-mouth smile, looking toward the player, arms relaxed. Chest and head must be fully visible with all hair/fin/tail inside frame; centered and large enough for a character dialogue panel.
Fine clean anime line art, nuanced shading, soft highlights, coherent proportions, high artistic quality; preserve the exact navy, cobalt, ocean blue, white and small gold accents of the reference. No image grid, no text, no captions, no backgrounds, no border, no props. Genuine transparent alpha background throughout.
```

## 表情变化

以平静立绘为编辑目标，两次调用共用以下约束：

```text
Edit the attached transparent game portrait. Keep the exact same character, hairstyle, ears, maid headband, hair bows, navy and white dress, apron whale, tail, anatomy, pose, framing, lighting, color palette and image dimensions. Do not add objects, text, a border or background. Only change the facial expression; preserve the transparent alpha background.
```

- 高兴：`Give her a genuinely cheerful open-mouth smile, bright eyes and a little warm blush. Do not change her head angle, gaze, clothing or pose.`
- 担心：`Give her a gentle worried expression with slightly raised inner eyebrows and a small concerned mouth, open blue eyes and a light blush. Do not change her head angle, gaze, clothing or pose.`
# 小尺寸探索稿 v3

输入参考：`whale-girl-source-4x4-v1.png` 与 `whale-girl-portrait-neutral.png`。使用 imagegen，要求透明背景。下述是提交给生成器的完整提示；生成结果仍为 1287×1222 的大图，并非真正 16×16 像素文件。

```text
Create an actual very low-resolution pixel-art game character sprite sheet for a 16×16-tile 2D top-down RPG. The attached existing sheet and portrait are the SAME CHARACTER and her precise identity must remain immediately recognizable: cute DeepSeek whale girl, long navy-to-blue hair, curved ahoge, white maid headband, blue fin ears, large blue eyes in the front view, white apron, navy maid dress, short rounded whale tail. This is specifically a simplified redraw for a tiny in-game character, NOT a detailed illustration and NOT a realistic figure.

CRITICAL PIXEL CONSTRAINTS: Each sprite is designed as if manually drawn on an imaginary 16×16 grid, using at most 16×16 very large square pixels, no single-pixel details smaller than that grid, no antialiasing, no gradients, no fine textures, no perspective distortion, no diagonal stroke thinner than a pixel block. Each block is uniformly colored with a deliberately restricted palette (navy, royal blue, sky blue, pale blue-white, skin, dark outline, two eye-blue pixels). Simplify face, ears, apron and tail to very small block clusters that survive at 16×16. Emphasize a readable silhouette and matching features more than decorative detail. Show no pixel grid lines or borders. Render the 16×16 sprites enlarged with crisp nearest-neighbor square edges (do not add details inside a pixel block).

SHEET LAYOUT: transparent background. A single clean 4 columns × 4 rows sprite sheet, with VERY generous fully transparent gutters and no labels. Each cell has one complete separated character, all characters same apparent size and feet baseline. Row 1 front views; row 2 left-facing side views; row 3 back views; row 4 right-facing side views. Four columns show subtle coordinated animation frames: idle, one step, idle, opposite step. No part, tail, hair or pixels may cross the empty gutter into another cell. No image frame or background. Preserve each view's direction and clear same character identity. No other objects, words, watermark or extra figures.
```

## 小尺寸深蓝配色稿 v6

内置 imagegen 先用小尺寸 v3 作为编辑对象、用户指定的 v1 与中性立绘作为配色参考，生成 v4 中间稿；因第四列鲸尾贴边，再以 v4、v3 和 v1 重新生成有透明间隔的 v6。v4 为中间稿，不作最终素材。以下为两次使用的完整提示。

### 配色编辑

```text
Use case: precise-object-edit. Image 1 is the EDIT TARGET: a transparent four-direction pixel sprite sheet of the whale girl with sixteen sprites. Image 2 is the USER-SELECTED COLOR REFERENCE: the original delicate whale-girl pixel sheet. Image 3 is the color reference portrait for the SAME character. The user specifically wants the sprite color unified to the reference's deep navy hair and costume.

Change only the palette of Image 1 to visually match Images 2 and 3. Recolor the unusually vivid royal blue/cobalt blue hair, whale ears and tail on EVERY sprite into the original reference's restrained dark ocean/navy blue: deep navy outlines and dress, muted medium-deep blue at the crown and bangs, slightly lighter blue on lower hair, matching whale tail; keep small sky-blue highlights, blue eyes, white headband/apron, skin and the dress colors consistent with the reference. Keep one consistent palette across all four directional views and all four frames, no variation in base hair color between views. Aim for Image 2's actual DARK BLUE hue, not violet, teal, grey, black, bright cyan, or saturated electric blue.

Strictly preserve Image 1's pixel-art style, individual 16 poses, row order (front, left, back, right), each frame's size and position, silhouette, linework, facial expressions, whale fin ears, bows, tail, clothes, composition and 4-by-4 sprite grid. Keep the same large transparent gaps between all sprites. Preserve genuine transparency, no background, no text, no frame, no additional characters. Do not redraw or change the pose, only harmonize colors.
```

### 帧间距修正

```text
Use case: precise-object-edit. The primary image (Image 1) is a transparent 4-by-4 whale-girl pixel sprite sheet to correct. Reference Image 2 shows the same character with clear empty gutters; reference Image 3 shows the selected dark blue color palette. Preserve Image 1's coloring and precise character design. Fix the frame layout as a sprite atlas only: make EACH of the 16 sprites about 10 percent smaller without otherwise changing their appearance, and center each fully within its own original cell. Leave a broad perfectly transparent strip BETWEEN every two neighboring rows and columns and around the full outer edges. There must be empty transparent gutters both horizontally and vertically; no hair, ahoge, bow, shoes or tail can touch a neighboring frame or the sheet edge. The rightmost tail in the second row must be complete. Each sprite has an ample clear margin on every side.

EXACT CONTENT: 4 columns and 4 rows. Four front-facing sprites in row 1; four left-facing sprites in row 2; four back-facing sprites in row 3; four right-facing sprites in row 4. Deep navy to muted ocean-blue hair, deep blue tail, white maid headdress and apron, and dark navy dress uniformly across all sprites. Pixel art, same character; preserve all 16 facial expressions and poses. No labels, no background, no grid lines, no shadows outside the sprites, no extra characters.
```

