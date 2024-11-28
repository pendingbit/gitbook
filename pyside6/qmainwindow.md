# QMainWindow

`QMainWindow` 组件提供如下图所示的框架来建立UI界面。其中`QToolBars`, `QDockWidgets`, `QMenuBar`以及`QStatusBar`是框架统一布局的类，中间空白区域可以自定义各种小组件。

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

## 示例

<pre class="language-python"><code class="lang-python"><strong>import sys
</strong>from PySide6.QtWidgets import (
    QApplication,
    QMainWindow,
    QToolBar,
    QDockWidget,
    QTextEdit,
    QLabel,
    QStatusBar,
)
from PySide6.QtCore import Qt
from PySide6.QtGui import QAction


class MainWindow(QMainWindow):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QMainWindow 示例")
        self.resize(800, 600)

        # 设置中心部件
        self.text_edit = QTextEdit()
        self.setCentralWidget(self.text_edit)

        # 创建菜单栏
        self.create_menu_bar()

        # 创建工具栏
        self.create_tool_bar()

        # 创建停靠窗口
        self.create_dock_widget()

        # 创建状态栏
        self.create_status_bar()

    def create_menu_bar(self):
        # 新建菜单栏
        menu_bar = self.menuBar()

        # 向菜单栏添加文件菜单
        file_menu = menu_bar.addMenu("文件")
        # 创建action对象
        open_action = QAction("打开", self)
        save_action = QAction("保存", self)
        exit_action = QAction("退出", self)
        # 关联action动作
        exit_action.triggered.connect(self.close)
        # 添加anction到文件菜单
        file_menu.addAction(open_action)
        file_menu.addAction(save_action)
        file_menu.addSeparator()
        file_menu.addAction(exit_action)

        # 向菜单栏添加编辑菜单
        edit_menu = menu_bar.addMenu("编辑")
        # 创建action对象
        cut_action = QAction("剪切", self)
        copy_action = QAction("复制", self)
        paste_action = QAction("粘贴", self)
        # 添加action到编辑菜单
        edit_menu.addAction(cut_action)
        edit_menu.addAction(copy_action)
        edit_menu.addAction(paste_action)

    def create_tool_bar(self):
        # 创建工具栏对象
        tool_bar = QToolBar("工具栏", self)
        # 设置工具栏可移动
        tool_bar.setMovable(True)
        # 添加工具栏到UI
        self.addToolBar(Qt.TopToolBarArea, tool_bar)

        # 添加工具栏按钮
        new_action = QAction("新建", self)
        open_action = QAction("打开", self)
        save_action = QAction("保存", self)

        tool_bar.addAction(new_action)
        tool_bar.addAction(open_action)
        tool_bar.addAction(save_action)

    def create_dock_widget(self):
        dock = QDockWidget("停靠窗口", self)
        dock.setAllowedAreas(Qt.LeftDockWidgetArea | Qt.RightDockWidgetArea)
        dock.setWidget(QLabel("这是一个停靠窗口"))
        dock.setFloating(False)  # 不允许初始浮动

        self.addDockWidget(Qt.LeftDockWidgetArea, dock)

    def create_status_bar(self):
        status_bar = QStatusBar(self)
        status_bar.showMessage("这是状态栏消息", 5000)  # 显示消息 5 秒
        self.setStatusBar(status_bar)


if __name__ == "__main__":
    app = QApplication(sys.argv)
    window = MainWindow()
    window.show()
    sys.exit(app.exec_())

</code></pre>

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

