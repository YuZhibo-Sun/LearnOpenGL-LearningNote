OpengGL是一个状态机

基本概念：

VertexShader，预定义的变量gl_position，计算坐标点位置

FragmentShader，计算坐标点的颜色

VBO

VAO

EBO

VBO和EBO都能存储在VAO中，但是VBO可以在设置完属性之后解绑，而EBO必须先解绑VAO再解绑EBO
