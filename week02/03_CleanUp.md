# Scene Data & Topology Refinement / 场景数据与拓扑优化

Essential workflows for auditing scene statistics, fixing asymmetry, and cleaning extracted meshes.
用于审计场景统计、修复不对称以及清理提取网格的核心工作流。

---

## 1. Display Scene Heads-Up Data / 显示场景数据
Enable the Heads-Up Display (HUD) to monitor polycount, vertices, and edges in real-time.
开启抬头显示（HUD）以实时监控多边形、顶点和边的数量。

* **Display > Heads Up Display > Poly Count**

<img width="500" alt="Poly Count HUD" src="https://github.com/user-attachments/assets/18ae1e49-c31c-4e71-bfc9-078c7e130bcd" />

---

## 2. Topology Repair / 拓扑修复

### Merging Vertices to Reduce Overlapping Faces / 合并顶点以减少重合面
Select all vertices and perform a Merge operation to eliminate duplicate geometry.
选中所有顶点并执行合并操作，以消除重复的几何结构。
* **Edit Mesh > Merge**

<img width="500" alt="Select All Verts" src="https://github.com/user-attachments/assets/bc7cdc5d-7fc1-4688-84f8-330f677c1c91" />
<img width="500" alt="Merge Result" src="https://github.com/user-attachments/assets/caf8b817-1327-4add-857d-8d969d1fb9ce" />

### Soften Edges for Organic Surfaces / 软化边缘以显示光滑表面
If an organic surface appears too "hard" or faceted, use Soften Edge to achieve a smooth look.
如果有机体表面显得太硬或有棱角，使用软化边缘来获得光滑效果。
* **Mesh Display > Soften Edge**

<img width="500" alt="Soften Edge" src="https://github.com/user-attachments/assets/45e8909b-910b-490e-a085-1fbd37ec1c65" />

### Modifying Edge Flow & Adding Geometry / 修改线方向与加面
* **Flip Triangle Edge**: Change the orientation of edges to improve topology flow. (修改线方向以优化拓扑流。)
* **Multi-Cut Tool**: Manually add edges or split faces for precise control. (使用 Multi-Cut 工具手动切线加面。)

<img width="400" alt="Flip Edge" src="https://github.com/user-attachments/assets/05c93541-14ce-4119-836e-eb53459507ff" />
<img width="200" alt="Multi-Cut 1" src="https://github.com/user-attachments/assets/14020987-aa17-4b7d-b7ff-487b6682ce39" />
<img width="150" alt="Multi-Cut 2" src="https://github.com/user-attachments/assets/363752e4-f38f-4fca-98b8-d945f96a54a2" />

---

## 3. Asymmetry Issues / 不对称问题修复

Fixing errors on one side of a mesh can be extremely difficult. The most efficient method is to mirror the clean side.
手动修复单边错误非常困难，最高效的方法是镜像干净的一侧。

### Step 1: Delete Half / 删除一半
Remove the problematic side of the mesh. (删除模型有问题的半边。)

<img width="500" alt="Delete Half" src="https://github.com/user-attachments/assets/e1983f50-69c0-408e-b15d-0ff54b4ea26c" />
<img width="500" alt="Half Mesh" src="https://github.com/user-attachments/assets/67bac538-4b48-49cb-b967-fbe9f0867fc3" />

### Step 2: Zero Out Centerline / 中线归零
Select the centerline vertices and set their **X-axis** value to **0** in the Channel Box/Input field to ensure a perfect seam.
选择中线顶点并将 **X 轴**数值设为 **0**，以确保镜像缝合完美。

<img width="400" alt="Zero X Axis" src="https://github.com/user-attachments/assets/1df3fde0-0bf7-45ca-8811-81947cc32126" />

### Step 3: Mirror Settings / 镜像设置
Adjust the **Mirror Direction** and merge threshold in the Mirror Options to get the desired result.
调整镜像方向和合并阈值以获得满意的结果。
* **Mesh > Mirror (Options)**

<img width="150" alt="Mirror Options" src="https://github.com/user-attachments/assets/721552aa-f7e3-4e67-b98f-1908f0e7dfb1" />
<img width="300" alt="Mirror Result" src="https://github.com/user-attachments/assets/291f7895-4672-4e03-bfb4-f8f69d25158f" />

---

## 4. Cleaning Extracted Meshes / 提取表面的清理 (Extract)

When extracting a surface to create items like clothing, the new mesh carries over unnecessary history and attributes.
从模型中提取表面制作衣服等物品时，新网格会携带多余的历史记录和属性。

### Post-Extraction Cleanup / 提取后清理
After using the **Extract** command, you must clean the mesh to maintain pipeline stability.
使用提取命令后，必须清理网格以维持工作流稳定性。
* **Delete History**: Remove input nodes. (删除历史记录。)
* **Freeze Transformations**: Reset position/rotation data. (冻结变换。)

<img width="500" alt="Extracting Surface" src="https://github.com/user-attachments/assets/80992d70-b477-456a-bc32-268e7b2bba38" />
