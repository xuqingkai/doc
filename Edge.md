### 打开网页卡顿怎么处理
- 打开设置，搜索关键字“加速”，找到“硬件加速模式的选项”，关闭掉，重启浏览器。
- 如果上一步解决问题，就不用下一步了
- 地址栏输入：chrome://flags/，然后回车，再搜索“gpu”，列表中找到：“GPU rasterization”(GPU 渲染) 以及 “Accelerated 2D canvas”(2D 图形加速) 两项
- 将它们都设为“Disabled”禁用即可。点击右下角的“ReLaunch”重启浏览器。
