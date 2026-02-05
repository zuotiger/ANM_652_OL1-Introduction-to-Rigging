# Measurement Tools & Mesh Cleanup / 测量工具与模型清理

Guide for verifying scale and fixing advanced geometric errors in Maya.
在 Maya 中验证比例以及修复高级几何错误的指南。

---

## 1. Measurement Tools / 测量工具

Use the Distance Tool to ensure your model conforms to the required real-world scale or character height.
使用距离工具确保模型符合要求的真实世界比例或角色高度。

* **Create > Measure Tools > Distance Tool**

<img width="500" alt="Measurement Tool" src="https://github.com/user-attachments/assets/c1e42820-9885-4784-9f37-46a0f459fb11" />

---

## 2. Mesh Cleanup / 模型自动清理

The Cleanup tool is essential for identifying and removing invisible geometry errors.
Cleanup 工具对于识别和移除肉眼难以察觉的几何错误至关重要。

* **Mesh > Cleanup (Options)**

<img width="500" alt="Cleanup Options" src="https://github.com/user-attachments/assets/7e56bb66-9e0d-4902-93fd-308190b0a4a2" />

### Highlighting Errors / 反选高亮错误面
Instead of auto-fixing, you can set the tool to select the problematic faces so you can inspect them manually.
除了自动修复，你可以将工具设置为“选择”模式，以便手动检查有问题的面。

<img width="500" alt="Highlighting Errors" src="https://github.com/user-attachments/assets/6aba60fd-e673-4340-a572-b1ca2ac8b512" />

### Using Materials to Tag Errors / 修改材质高亮错误
Assign a bright, contrasting material (like a red Lambert) to the selected error faces to make them easier to find and fix later.
为选中的错误面分配一个显眼的材质（如红色 Lambert），方便后续查找与修改。

<img width="400" alt="Material UI 1" src="https://github.com/user-attachments/assets/70e00d13-f809-4164-845f-f198c5a2f826" />
<img width="300" alt="Material UI 2" src="https://github.com/user-attachments/assets/6a166c5d-2dc4-45fc-b103-3ea8f2156ceb" />
<img width="500" alt="Highlighted Mesh" src="https://github.com/user-attachments/assets/7fb419b9-1a91-400b-b260-12f72ac018ea" />

---

## 3. Specific Geometry Issues / 特定几何问题排查

### Lamina Faces / 重叠面
Lamina faces occur when two or more faces share the exact same vertices and edges.
当两个或多个面完全共享相同的顶点和边时，就会产生 Lamina faces。

<img width="500" alt="Lamina Faces Concept" src="https://github.com/user-attachments/assets/f7f4c521-33bf-4894-9808-790fbcbf47e9" />
<img width="500" alt="Detecting Lamina" src="https://github.com/user-attachments/assets/eec74e3e-1e5f-48a0-a410-2a3f67c5ea1d" />
<img width="500" alt="Cleaning Lamina" src="https://github.com/user-attachments/assets/8722cfb3-92ea-4ff2-b5d6-1366ffe8294e" />

### Non-Manifold Geometry / 非流形几何体
Non-manifold geometry refers to configurations that cannot exist in a flat, 2D representation (e.g., three faces sharing a single edge). This will break rigging and rendering.
非流形几何体是指无法在 2D 平面上展开的结构（例如三个面共用一条边）。这会导致绑定和渲染出错。

<img width="500" alt="Non-Manifold Check" src="https://github.com/user-attachments/assets/396f6094-69b4-48dd-9ffe-6d9d38667c36" />
