### 标准化与 0-1 空间 (Normalize & 0-1 Space)
规则： 你所有的 UV 都应该位于 0 到 1 的坐标空间 内。

操作： 截图中的 Normalize UVs Options 就是用来一键完成这个任务的。


### 反向 UV (Flipped UVs)
问题： 指的是 UV 面的朝向不对。

后果： 如果 UV 是翻转的（Flipped），你的贴图在模型上看起来就是反的（比如文字变成了镜像）。

小技巧： 在 Maya 的 UV 编辑器里，点击 Shaded（着色显示） 按钮，蓝色的面是正确的，红色的面就是 Flipped（翻转的）。


### 组件与物体的关系 (Component vs. Object)
这些组件（点、线、面）虽然在 3D 空间属于同一个 Object，但在 UV 空间里可能是相互分离的独立部分（即 UV Shells）。

------------------------------------------------------------------------------------------
1. 常见投影类型及应用场景 (Common Projection Types & Usage)
根据模型部位的不同，选择合适的映射方式至关重要：

圆柱形投影 (Cylindrical Maps):

角色： 头部、手臂、腿部。

环境： 管道、瓶子、柱子等柱状物体。

平面投影 (Planar Maps):

角色： 躯干的前后部、手掌和手背。

环境： 墙壁、窗户、街道等平整表面。

自动映射 (Automatic Mapping):

适用： 硬表面物体。

优势： 能自动生成符合环境工作比例（Scale）的 UV。

2. UV 空间管理 (UV Space Management)
0-1 坐标空间： 目标是将每个物体的所有 UV 放置在 0 到 1 的坐标空间内。

按物体分配 (Per Object): 始终记住 0-1 空间是针对单个物体而言的（除非是使用多象限 UDIM 等高级技术）。

时间投入： 布局 UV 空间是一个非常耗时的过程，需要耐心。

Summary in English
This tutorial covers the fundamentals of selecting UV projection methods and managing coordinate space:

Projection Methods: Use Cylindrical for limbs and cylindrical objects, Planar for flat surfaces like torsos or walls, and Automatic for hard surfaces to maintain proper scaling.

UV Layout: The primary goal is to fit all UVs within the 0-1 coordinate space.

Key Principle: Remember that the 0-1 space is allocated per object. While advanced multi-tiling exists, standard practice requires careful arrangement within this single tile, which is often a time-consuming process.
