# Common Issues & Troubleshooting / 常见问题与排查

This guide covers essential mesh auditing steps in Maya to ensure your model is ready for rigging.
本指南涵盖了 Maya 中基础的模型审计步骤，以确保您的模型已为绑定做好准备。

---

## 1. Reversed Normals / 法线反面

Incorrect normal orientation can cause shading issues and artifacts during skinning.
错误的法线朝向会导致着色异常以及蒙皮时的瑕疵。

### How to Display Normals / 如何显示法线朝向
To visualize which way your faces are pointing:
查看面朝向的操作步骤：
* **Display > Polygons > Face Normals**

<img width="500" alt="Display Normals" src="https://github.com/user-attachments/assets/cd891450-0f73-423b-ae5a-f311d65e69c9" />
<img width="500" alt="Normals Menu" src="https://github.com/user-attachments/assets/0d5e3207-e1b3-4187-a7a8-b146c245d4fb" />

### Adjusting Normals Display Size / 如何调整法线显示大小
If the normal lines are too long or too short, you can adjust them here:
如果法线显示线条过长或过短，可以在此处调整：
* **Display > Polygons > Normals Size**

<img width="500" alt="Adjusting Normals Size" src="https://github.com/user-attachments/assets/15810a36-763e-4e99-88b2-b8ebf65e3a0b" />

### Quick Check: Disable Two-Sided Lighting / 快速检查：关闭双面照明
Turning off **Two Sided Lighting** will make reversed normals appear black in the viewport.
关闭“双面照明”后，反向的法线在视图中会直接显示为黑色，便于快速识别。
* **Viewport Menu: Lighting > Two Sided Lighting (Uncheck)**

<img width="500" alt="Two Sided Lighting Off" src="https://github.com/user-attachments/assets/fcaabf7d-7e2e-46f1-9280-17e4cd6b20a5" />

---

## 2. Overlapping Vertices / 重复点

Duplicate vertices in the same position can break your edge loops and deformation.
在同一位置重叠的点会破坏循环边并导致变形异常。

### Inspecting with Vertex Face Mode / 进入 Vertex Face 检查
Use **Vertex Face** mode to visually separate components and find hidden overlapping points or edges.
使用 **Vertex Face** 模式可以从视觉上分离组件，从而找出隐藏的重复点或边。
* **Right-click on Mesh > Vertex Face**

<img width="500" alt="Vertex Face Mode" src="https://github.com/user-attachments/assets/d20aa8b5-03ef-47dd-98bd-cfd9ddda1710" />
<img width="500" alt="Finding Duplicate Verts" src="https://github.com/user-attachments/assets/1572b04e-f244-4fb0-9913-cf4d8138f02d" />

### How to Fix: Merge Vertices / 修复方法：合并顶点
Select the overlapping vertices and merge them into one.
选中重叠的顶点并将它们合并为一个。
* **Edit Mesh > Merge (Options)**
* *Tip: Adjust the Threshold to ensure only very close vertices are merged.*

<img width="400" alt="Merge Tool" src="https://github.com/user-attachments/assets/fcc3ee84-a165-4af5-9553-4aaa5cdb78e9" />
<img width="500" alt="Merge Result" src="https://github.com/user-attachments/assets/253c8572-100d-490a-a3d0-bbf26c6ca62f" />

---
*Created for Introduction to Rigging*
