## 简易图片库

# 非常抱歉

1. 由于我——仓库所有者的疏忽，在交流群内与一位为我们项目做出巨大贡献的协作者产生矛盾，此项目后面可能会停更，甚至仓库会进行删除处理。

# 协助者注意

1. 提交更新或修补请push到patch分支中，并在分支的readme开头“更新”板块下按1、2、3的顺序写上本次推送的更新内容（方便后面合并main后修改main的readme），我会定期检查patch分支并合并到main中，并同步更新新的release包，谢谢您的协助与配合！

# Main主分支更新了！本次更新内容如下：

1. 修复了后端加载图片慢的问题，感谢某位已经离开此项目的合作者最后的付出！

# 更新预告

1. 由于网站采用了瀑布流布局来更美观地显示图片，所以原有的分页功能有必要被更适配瀑布流布局的“无限下滑”所取代，敬请期待……
2. 本次更新后出现的bug，详见：https://github.com/LhyYBMQ520/My-Image-Gallery/issues/10#issuecomment-2511374703 ，注：虽然文字中暗示了无限下滑功能，但实际并未更新，无视即可。
3. 网页布局仍存在问题，正在和合作者商量下一步改进相关的事，如重构整体代码，使用vue。

## 复现更新预告2中提到的bug方式以及bug的内容

（使用手机版chrome和firefox浏览器测试得来的过程）
1. 关闭原先打开的图片库页面并退出浏览器（或直接开个无痕模式窗口）
2. 再次进入图片库页面
3. 可以发现刚进去时的那个界面懒加载占位符挤在一起，从而使懒加载失效，加载了一个页面上的所有图。
4. 然后手动点页码换页，或者按上一页下一页按钮，甚至在切换到其他页面后再次回到最开始的页码，懒加载都正常运行。

# 简介

这是一个基于 Flask 后端框架和 Waitress WSGI 服务器的简易网页图片库，可以将存在本地固定路径的图片展示在页面上，并提供全屏原图查看和原图的下载。

## 如何使用

1. 下载项目源代码并解压到合适位置
2. 确保设备已经正确安装并配置了Python环境
3. 为了防止与系统中的其他pip包发生冲突，建议为项目**创建虚拟环境**
4. 如果第一次使用本软件，请在项目根目录执行`pip install -r requirements.txt`安装必要的运行前置。使用时需要虚拟环境，请**先激活虚拟环境**再执行命令
5. 将需要展示的图片放在`static/images`文件夹中（默认输入文件夹）。
6. 在项目的根目录启动终端，如果你需要使用虚拟环境运行，请先激活虚拟环境。然后执行：
```sh
python3 app.py
```
或
```sh
python app.py
```

即可运行后端。

（注意：第一次或后续有新增图片后开启后端时会初始化一段时间，此时Pillow正在按预设压缩图片，压缩后的图片保存在：  static/compressed_images 文件夹中。）

7. 随后即可从 `localhost:5000` `127.0.0.1:5000` `[::]:5000` 或公网IP访问网页。

## 其他事项

本代码包附带了一张背景图片，位于`/static/background/`中
如需自定义可以将新图片的名字改为和现在一样（leaves.webp）

也可以到`/static/css/`中修改css的这个部分：

```css
/* 设置背景图片 */
body {
    /* background/后的文件名 */
    background-image: url('/static/background/leaves.webp');
}
```

修改成实际图片的名字即可。
