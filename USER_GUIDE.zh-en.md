# Etsy Image Studio — 中英文使用说明 / Bilingual User Guide

## 1. 这是什么 / What this is

这是一个面向 Etsy 商品图片的提示词与出图规划 Skill。它把产品保真、构图、色彩、材质灯光、文字后期和质量验收组合成一个可重复的工作流。

This skill turns Etsy image requests into production-ready prompts and shot plans. It combines product fidelity, composition, color, material-aware lighting, post-production text handling, and quality control.

## 2. 两个版本 / Two versions

### 英文版 / English

调用：`$etsy-image-studio`

适合英文工作流、海外团队协作，或希望最终提示词直接使用英文的场景。

Use `$etsy-image-studio` for English workflows, international collaboration, or prompts that will be run directly in English.

### 中文版 / Chinese

调用：`$etsy-image-studio-zh`

适合用中文描述产品、场景、材质和审美要求。Skill 名称仍使用 ASCII 字符，便于系统发现。

Use `$etsy-image-studio-zh` when you prefer to describe products, scenes, materials, and aesthetic goals in Chinese. The ASCII skill name keeps discovery reliable.

两个版本的工作原则一致，主要差别是说明语言和输出语言，不是图片质量等级。

Both versions use the same design principles. The main difference is instruction and response language, not image quality.

## 3. 最低输入 / Minimum input

开始前尽量提供：产品参考图、产品名称和品类、材质和颜色、不能改变的特征、图片用途和数量、文字或 Logo 要求，以及喜欢的视觉风格参考。

Before starting, provide product references, name and category, material and color, non-negotiable features, image role and count, text or logo requirements, and preferred visual references.

产品结构复杂时，提供正面、侧面、背面、顶部和细节图。复杂产品不要只依赖一张低清图片。

For complex products, provide front, side, back, top, and detail views. Do not rely on one low-resolution image for a structurally complex item.

## 4. 参考图职责 / Reference-image roles

- 图1 / Image 1：产品真值——结构、颜色、材质、图案和配件；product truth.
- 图2 / Image 2：构图或摆放；composition or placement.
- 图3 / Image 3：场景或光线；scene or lighting.
- 图4 / Image 4：动作或模特姿态；pose or gesture.

如果参考图冲突，以产品真值图为准。不要让风格参考图改变产品本身。

If references conflict, the product-truth image wins. A style reference must never change the product.

## 5. 推荐工作流 / Recommended workflow

### 第一步：确定图片职责 / Step 1: Define the image role

一张图片只承担一个主要任务：主图、细节图、场景图、模特图、合集图、四宫格底图或 GIF 帧。

Give each image one primary job: hero, detail, lifestyle, model, variant grid, collage base, or animation frame.

### 第二步：写产品锁 / Step 2: Write product locks

不要只写“不要改变产品”。列出轮廓、比例、部件数量、连接位置、缝线、五金、图案位置、材质和层级。

Do not only write “do not change the product.” List silhouette, proportions, component count, attachment points, seams, hardware, artwork placement, material, and layer order.

### 第三步：确定构图 / Step 3: Define composition

指定主体位置、占画面比例、视角、裁切、留白位置和道具用途。主图通常让产品占画面约 65%–78%，但复杂轮廓需要适当缩小。

Specify subject position, frame occupancy, camera angle, crop, negative-space side, and prop purpose. A hero image usually gives the product about 65–78% of the frame.

### 第四步：确定配色 / Step 4: Define color

使用“产品主色 + 中性背景 + 至多一个点缀色”。优先确保产品边缘和背景有明度差。

Use “product color + neutral background + at most one accent.” Prioritize luminance separation between product and background.

### 第五步：按材质设计灯光 / Step 5: Match light to material

织物用方向性侧光，金属用边缘高光，陶瓷用连续渐变，美妆包装控制反光，深色服装增加轮廓光。

Use directional side light for textiles, edge highlights for metal, smooth gradients for ceramics, controlled reflections for packaging, and rim separation for dark apparel.

### 第六步：生成、检查、修复 / Step 6: Render, check, correct

先检查产品还原，再检查结构、构图、材质、色彩和清洁度。强制项失败或总分低于 85 分时，定向修改或重新生成。

Check product fidelity first, then structure, composition, material, color, and cleanliness. Correct or regenerate if a mandatory lock fails or the score is below 85.

## 6. 各图片用途 / Image-role guidance

| 用途 / Role | 核心目标 / Primary goal | 推荐方法 / Recommended method |
|---|---|---|
| 主图 / Hero | 一眼识别产品 / instant recognition | 干净背景、主体清晰、少道具 / quiet background, crisp subject, few props |
| 细节图 / Detail | 材质或卖点 / material or selling point | 一张图只突出一个细节 / one feature per image |
| 场景图 / Lifestyle | 使用情境和品牌气质 / use context and brand mood | 前景—主体—背景三层 / three depth layers |
| 模特图 / Model | 穿着效果和比例 / fit and scale | 动作不遮挡服装卖点 / pose must not cover selling features |
| 合集图 / Variant grid | 方便比较款式 / compare variants | 数量、比例、曝光一致 / consistent count, scale, exposure |
| 四宫格 / Collage | 分别表达四个卖点 / four distinct messages | 分别生成后拼接 / render panels separately, then compose |
| GIF 帧 / GIF frames | 只改变一个动作变量 / one motion change | 锁定相机、背景、光线和尺寸 / lock camera, scene, light, and scale |

## 7. 文字处理 / Text handling

长段文案、尺寸、箭头、标签、Logo 和准确封面文字不要完全交给图像模型。更稳定的流程是先生成干净底图、预留文字区域，再后期排版或贴图。

Do not rely on an image model for long copy, measurements, arrows, labels, logos, or exact cover text. Render a clean base, reserve space, then typeset or composite deterministically.

建议提示词：

> 图片中不生成文字，为右侧预留约 25% 的干净空间，文字由后期排版添加。
>
> Do not generate text. Reserve approximately 25% clean space on the right for post-production typesetting.

## 8. 审美检查 / Aesthetic review

交付前回答：缩略图 3 秒内能否认出产品？产品是否是唯一主要焦点？主体与背景是否有明度差？配色是否控制在主色、中性背景和一个点缀色以内？光线是否表现真实材质？道具是否有明确功能？关键卖点是否清晰且未被遮挡？和同一 Listing 的其他图片是否统一？

Before delivery, ask: Can the product be identified within three seconds at thumbnail size? Is it the single dominant focus? Is there enough luminance separation? Is the palette restrained? Does the light reveal the material? Do props have a clear purpose? Is the selling feature visible? Does the image belong to the same listing system?

如果两个以上答案不确定，先简化画面，不要继续添加装饰。

If two or more answers are uncertain, simplify the image before adding more styling.

## 9. 调用示例 / Invocation examples

```text
使用 $etsy-image-studio-zh，根据这张包袋参考图生成 1 张 Etsy 主图、
1 张材质细节图和 1 张生活方式图。产品是深红色灯芯绒托特包，必须保留
提手、印花和缝线。整体配色温暖克制，主图适合手机缩略图。生成后按
照审美检查表评分，低于 85 分请指出问题并修改提示词。
```

```text
Use $etsy-image-studio to create one Etsy hero image, one material detail image,
and one lifestyle image from this bag reference. Preserve the silhouette, handle
count, print placement, seams, and corduroy texture. Keep the palette warm and
restrained, optimize the hero for mobile thumbnails, and score the results with
the aesthetic checklist. If the score is below 85, revise the prompt.
```

## 10. 版本维护 / Version maintenance

记录模板 ID、提示词版本、模型版本、参考图职责、输出文件和质量得分。修改时优先做小范围调整，不要一次重写所有变量。

Record the template ID, prompt version, model version, reference roles, output files, and quality score. Prefer localized changes instead of rewriting every variable at once.
