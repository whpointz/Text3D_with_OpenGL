# Text3D_with_OpenGL
Render 3D Texts with OpenGL!

这是一个用OpenGL渲染3D文字的程序，想要全面了解其原理，需要具备以下知识：

1. C/C++
2. OpenGL & GLSL（OpenGL基本的绘制方式以及顶点着色器和片元着色器）
3. 计算机图形学（二次贝塞尔曲线）
4. FreeType2（涉及FT_Outline_Decompose函数，需要了解字形轮廓的分解）
5. 计算几何相关算法（多边形的三角剖分）

当前的实现版本使用GLU库进行三角剖分，不过GLU库非常古老，不太好用了~不久后将会实现我们自己的三角剖分程序！

先来看一下基本的流程：
1. 使用FreeType2获取字形的轮廓信息，我们将获取到的信息封装为FreeTypeFont这个类型；
2. 使用GLU库对获取到的字形轮廓进行多边形的三角剖分，生成三角网格面片，注意，这时的字形还不是3D文字，而是只有一个面；
3. 使用在上一步生成的字形三角网格面生成3D文字的背面和侧面；
4. 使用OpenGL对3D文字模型进行渲染；

注：

所有第三方依赖库都放在了3rdParty.rar里面，而实现文件都在Text3D文件夹下面！

FreeType的文档请看这里：https://www.freetype.org/freetype2/docs/documentation.html

在处理图形学中的数学类型时，我们使用了glm库，参考这里：https://github.com/g-truc/glm/tags

GLU库的文档可以看这里https://khronos.org/registry/OpenGL/specs/gl/glu1.3.pdf

Windows系统的字体文件可以在C:\Windows\Fonts路径下找到！

Text3D工程中需要包含的第三方依赖库如下图：

<img src="http://ovi8mw7d8.bkt.clouddn.com/Text3D%E5%B7%A5%E7%A8%8B%E4%BE%9D%E8%B5%96%E5%BA%93.png" width="500" />

Render_with_OpenGL工程中需要包含的第三方依赖库如下图：

<img src="http://ovi8mw7d8.bkt.clouddn.com/Render_with_OpenGL%E9%A1%B9%E7%9B%AE%E4%BE%9D%E8%B5%96%E5%BA%93.png" width="500" />

其中opengl32.lib和glu32.lib是已经在Windows系统中存在的了，其他系统尚不清楚，抱歉~

下图为实现效果：

<img src="http://ovi8mw7d8.bkt.clouddn.com/3D%E6%96%87%E5%AD%97%E5%B1%95%E7%A4%BA.png" width="400" /><img src="http://ovi8mw7d8.bkt.clouddn.com/3D%E6%96%87%E5%AD%97%E7%BA%BF%E6%A1%86%E6%A8%A1%E5%BC%8F%E5%B1%95%E7%A4%BA.png" width="400" />

项目仍在持续更行中，敬请期待！

文档尚未完成，README NOT COMPLETED YET！
