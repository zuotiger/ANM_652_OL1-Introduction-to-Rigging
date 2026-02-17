# UV 映射第二部分：清理、规范与验证 (UV Mapping, Part 2: Cleanup)

> **课程编号：** ANM_652_OL1 - Introduction to Rigging
> **核心目标：** 将原始 UV 投影优化为符合行业标准的专业布局，并进行材质验证。

---

## 1. UV 清理核心流程 (Cleanup Workflow)

在创建完基础 UV 投影后，清理布局（Cleanup）通常是整个流程中**最耗时**的部分。

### 常用工具集 (Preferred Tools)
* **剪切 (Cut):** 定义 UV 边界和缝合线。
* **移动与缝合 (Move and Sew):** 合并碎小的 UV 壳以减少接缝。
* **标准化 (Normalize):** 将 UV 壳缩放到标准的 $0-1$ 空间。
* **展开 (Unfold):** 推荐使用 **Unfold 3D** 算法处理有机生物模型。

---

## 2. 行业布局准则 (Industry Guidelines)

为了确保资产在游戏引擎或渲染器中正常显示，必须遵守以下准则：

1. **0-1 空间限制:** 所有的 UV 壳必须严格位于 **$0$ 到 $1$** 的坐标方格内。
   * *(注：视频字幕中的 "EV" 实为 **UV** 的误读)*
2. **禁止翻转 (No Flipped UVs):** 必须确保没有任何翻转的 UV 壳，否则贴图会呈现镜像反转效果。
   * *(注：视频字幕中的 "UAVs" 实为 **UVs** 的误读)*
3. **组件独立性:** UV 组件（Shells）在 UV 空间中可以与 3D 物体的物理连接状态分离，作为独立片段存在。

---

## 3. 标准化设置详解 (Normalize UVs Options)

在执行 **Normalize** 操作时，建议使用以下配置以保证纹理精度：

| 选项 | 推荐设置 | 说明 |
| :--- | :--- | :--- |
| **Normalize Along** | **UV** | 在 U 和 V 两个轴向上同时缩放。 |
| **Normalize** | **Collectively** | **集体缩放**：保持多个 UV 壳之间的相对比例。 |
| **Preserve aspect ratio** | **勾选** | 防止 UV 产生拉伸或变形。 |
| **Center on closest tile** | **勾选** | 将 UV 放置在最接近的整数坐标象限内。 |

---

## 4. TA 进阶：属性传递与复杂选择 (Advanced TA Techniques)

### 属性传递 (Transfer Attributes)
适用于将一个平面参考源的完美 UV 传递给形状复杂的凹凸模型（如地形）。
* **Attributes to Transfer:** UV Sets (All)。
* **Sample Space:** 建议设为 **UV** 或 **World**。

### 有机生物模型工具 (Organic Tools)
* **Shortest Edge Path Tool:** 用于在复杂模型（如豹子）上快速选择最短路径作为剪切线。
* **Proportional Scale:** 在 Layout 时确保不同物体间的 **纹理密度 (Texel Density)** 一致。

---

## 5. 材质验证工作流 (Material Verification)

清理完成后，必须通过 **Hypershade** 链接测试贴图进行校验。

1. **创建材质:** 新建 `lambert` 材质，按规范命名（如 `sidewall_MAT`）。
2. **链接贴图:** 创建 **File** 节点并加载棋盘格文件（如 `uvMappingGrid_1.psd`）。
3. **增加密度:** 通过 **place2dTexture** 节点调整 **Repeat UV**（如 $16 \times 16$），检查是否有微小拉伸。

---

> **⚠️ 版本兼容性说明：** > 教程中的 "Auto Unwrap UVs" 等旧版工具 在新版 Maya 中已整合至 **UV Toolkit** 的 **Unfold** 和 **Arrange and Layout** 面板中。
