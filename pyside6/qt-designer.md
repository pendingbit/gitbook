# Qt Designer

通过Qt Designer软件绘制ui界面，绘制完毕另存为.ui文件

<figure><img src=".gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

在python代码中加载.ui界面，并通过objectName获取对应组件。

```python
import sys
from PySide6 import QtWidgets
from PySide6.QtUiTools import QUiLoader

loader = QUiLoader()    #setup a loader object

app = QtWidgets.QApplication(sys.argv)
window = loader.load("widget.ui", None) #Load the ui

def fun():
    print(f"{window.name_line_edit.text()} is a {window.job_line_edit.text()}.")

window.commit_button.clicked.connect(fun)
window.show()
app.exec()

```

<figure><img src=".gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

```python
# class method
import sys
from PySide6 import QtWidgets,QtCore
from PySide6.QtUiTools import QUiLoader

loader = QUiLoader()    #setup a loader object

class UserInterfacce(QtCore.QObject):
    def __init__(self):
        super().__init__()
        self.ui = loader.load("widget.ui", None)
        self.ui.commit_button.clicked.connect(self.fun)
    
    def fun(self):
        print(f"{self.ui.name_line_edit.text()} is a {self.ui.job_line_edit.text()}.")

    def show(self):
        self.ui.show()

app = QtWidgets.QApplication(sys.argv)

window = UserInterfacce()
window.show()

app.exec()

```

