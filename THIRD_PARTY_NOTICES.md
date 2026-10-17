# 第三方素材清单与许可（Third-Party Notices）

本文件与 `LICENSE` 配套，发布时放在 `index.html` 同一目录，随包一起分发。
「版权声明原文」逐字抄自素材文件头或上游 LICENSE，未改写。

## 总表

| # | 名称 | 版本 | 来源 | 许可 | 本作品是否修改 |
|---|---|---|---|---|---|
| 1 | BodyParts3D | 4.0 | DBCLS BodyParts3D 档案库 | CC BY-SA 2.1 JP | 是（见 §1.5） |
| 2 | BodyParts3D | 3.0 | DBCLS BodyParts3D 档案库 | CC BY-SA 2.1 JP | 是（见 §2.4） |
| 3 | three.js 核心 | r160（`three.module.js`） | threejs.org / GitHub | MIT | 否（原样引入） |
| 4 | OrbitControls | r160（examples/jsm/controls） | three.js 仓库 | MIT | 否（原样引入） |
| 5 | OutlineEffect | r160（examples/jsm/effects） | three.js 仓库 | MIT | 否（原样引入） |

本页内嵌的网格数据块共 88 段（`<script type="text/plain" class="meshobj">`），其数据来自 1、2 两项。

---

## 1. BodyParts3D 4.0

- 名称：BodyParts3D（解剖网格数据集）
- 版本：4.0（`isa_BP3D_4.0_obj_99`，兼容版本 4.0）
- 来源：`https://dbarchive.biosciencedbc.jp/data/bodyparts3d/LATEST/`
  项目主页：`https://lifesciencedb.jp/bp3d/`
  许可说明页：`http://dbarchive.biosciencedbc.jp/en/bodyparts3d/lic.html`
- 许可：Creative Commons Attribution-Share Alike 2.1 Japan（CC BY-SA 2.1 JP）
  `https://creativecommons.org/licenses/by-sa/2.1/jp/`
- 本作品用到的部位：喉软骨（甲状/环状/杓状/舌骨/会厌）、声带与声韧带、喉内肌、气管、胸骨、肋骨、膈、下颌骨、舌、舌骨上下肌群等。

### 1.4 版权声明原文（逐字，来自 4.0 OBJ 文件头）

```
# The license for this database is specified in the Creative Commons Attribution-Share Alike 2.1 Japan. If you use data from this database, please be sure attribute this database as follows: "BodyParts3D, (c)  The Database Center for Life Science licensed under CC Attribution-Share Alike 2.1 Japan".
# http://dbarchive.biosciencedbc.jp/en/bodyparts3d/lic.html
```

建议的署名串（与上述原文一致）：

> BodyParts3D, (c) The Database Center for Life Science licensed under CC Attribution-Share Alike 2.1 Japan

### 1.5 本作品做的修改（须随数据一起说明）

1. 与 3.0 数据统一坐标系：以气管为刚体配准，把 3.0 件并入 4.0 坐标系；
2. 量化：顶点坐标取整压缩（体积/精度权衡后再内嵌进页面）；
3. 绕轴旋转与整体缩放（对齐页面的 Y 轴向上与展示比例）；
4. 顶点焊接（去掉重复顶点，减面/合并接缝）；
5. 结构重命名（中文教学名，如「甲杓肌-右」「环杓后肌-左」）；
6. 按教学需要把同一结构拆成多件显示（如环甲肌直部/斜部、声带肌与甲杓肌分别建块）。

因为做了上述修改，本作品内嵌的网格属于**改编素材**：按 CC BY-SA 2.1 JP 要求，这些改动后的网格同样以 CC BY-SA 2.1 JP 提供，并保留署名。

### 1.6 注意

内嵌进页面的数据块头部只有来源与量化说明，**没有**版权声明。因此署名靠三处承担：页面页脚、「关于」弹窗、本文件 + `LICENSE`。数据块头是否需要补一行署名，留待后续版本再定。

---

## 2. BodyParts3D 3.0

- 名称：BodyParts3D（解剖网格数据集）
- 版本：3.0（`BodyParts3D_3.0_obj_95.zip`，95% 减面版，按需抽取部件）
- 来源：`https://dbarchive.biosciencedbc.jp/data/bodyparts3d/LATEST/`
  许可说明页：`http://dbarchive.biosciencedbc.jp/en/bodyparts3d/lic.html`
- 许可：CC BY-SA 2.1 JP（同上链接）
- 本作品用到的部位：面部表情肌（口轮匝肌、颧大/小肌、咬肌浅/深部、颊肌、额肌、颈阔肌等）、肺叶。

### 2.3 版权声明原文（逐字，来自 3.0 OBJ 文件头）

```
# Wavafront OBJ file of BodyParts3D
# BodyParts3D, Copyright(C) 2010-2011 The Database Center for Life Science licensed under CC Attribution-Share Alike 2.1 Japan.
```

### 2.4 本作品做的修改

同 §1.5：并入 4.0 坐标系、量化、旋转缩放、顶点焊接、中文重命名；部分面肌按教学需要做了左右拆分。

---

## 3. three.js 核心（r160）

- 名称：three.js
- 版本：r160（文件内 `REVISION = '160'`）
- 文件：`lib/three@0.160.0/build/three.module.js`
- 来源：`https://threejs.org/`；源码仓库 `https://github.com/mrdoob/three.js/tree/r160`
- 许可：MIT
- 版权声明原文（逐字，文件头）：

```
/**
 * @license
 * Copyright 2010-2023 Three.js Authors
 * SPDX-License-Identifier: MIT
 */
```

- 是否修改：否，原样引入（未改动一个字节）。

---

## 4. OrbitControls（three.js r160 examples）

- 名称：OrbitControls
- 版本：r160
- 文件：`lib/three@0.160.0/examples/jsm/controls/OrbitControls.js`
- 来源：`https://github.com/mrdoob/three.js/blob/r160/examples/jsm/controls/OrbitControls.js`
- 许可：MIT（随 three.js 仓库，同一许可）
- 版权声明原文：**该文件内没有任何版权头**（文件从 `import {` 直接开始）。MIT 义务由本文件 §6 的许可证全文 + §3 的版权行承担。
- 是否修改：否，原样引入。

---

## 5. OutlineEffect（three.js r160 examples）

- 名称：OutlineEffect
- 版本：r160
- 文件：`lib/three@0.160.0/examples/jsm/effects/OutlineEffect.js`
- 来源：`https://github.com/mrdoob/three.js/blob/r160/examples/jsm/effects/OutlineEffect.js`
- 许可：MIT
- 版权声明原文：**该文件内没有任何版权头**（文件从 `import {` 直接开始）。
- 是否修改：否，原样引入。

---

## 6. MIT 许可证全文（覆盖第 3、4、5 项）

```
MIT License

Copyright (c) 2010-2023 Three.js Authors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## 7. 分发要点（给上传/再分发的人）

1. 三处署名必须同时在：页面页脚、「关于」弹窗、`LICENSE` + 本文件。
2. **任何情况下不得去除 BodyParts3D 的署名与许可标注**；截取网格数据单独使用也算再分发。
3. 如果你改了网格，要保留本文件的修改说明，并让改后的网格继续以 CC BY-SA 2.1 JP 共享。
4. 代码、文案、题库部分另有约定（见 `LICENSE` 第一部分），与本文件的第三方许可互不覆盖。
