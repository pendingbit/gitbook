# Using Resources

使用Qt Designer绘制包含resources的UI界面，将resources保存为.qrc文件。

<figure><img src=".gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

将resources编译为python代码，资源以二进制进行使用，原图片不再关联。

```
command：
    pyside6-rcc resource.qrc -o resource_rc.py
```



<figure><img src=".gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

```python
# widget.py use ui and resource
import sys
from PySide6 import QtWidgets
from PySide6.QtWidgets import QWidget
from ui_widget import Ui_Widget

class Widget(QWidget, Ui_Widget):
    def __init__(self):
        super().__init__()
        self.setupUi(self)
    

app = QtWidgets.QApplication(sys.argv)

window = Widget()
window.show()

app.exec()

```

