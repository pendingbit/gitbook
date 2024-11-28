# QMessageBox

`QMessageBox`组件提供一种对话弹窗，用来询问用户并接收答案。

## 示例

```python
import sys
from PySide6.QtWidgets import (
    QApplication,
    QMessageBox,
    QPushButton,
    QVBoxLayout,
    QWidget,
)

class MessageBox(QWidget):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QMessageBox")

        button1 = QPushButton("hard message box")
        button2 = QPushButton("easy message box")
        button1.clicked.connect(self.button1_respond)
        button2.clicked.connect(self.button2_respond)

        layout = QVBoxLayout()
        layout.addWidget(button1)
        layout.addWidget(button2)
        self.setLayout(layout)

# 复杂弹窗
    def button1_respond(self):
        message = QMessageBox()
        message.setMinimumSize(700,200)
        message.setWindowTitle("Message Title")
        message.setText("Something happened")
        message.setInformativeText("Do you want to do sth about it?")
        message.setIcon(QMessageBox.Critical)
        message.setStandardButtons(QMessageBox.Ok | QMessageBox.Cancel)
        message.setDefaultButton(QMessageBox.Ok)
        ret = message.exec()
        if ret == QMessageBox.Ok :
            print("User chose ok")
        else :
            print("User chose cancel")

# 简单弹窗
    def button2_respond(self):
        ret = QMessageBox.critical(self, "Message Title", "cRITICAL mESSAGE!", QMessageBox.Ok | QMessageBox.Cancel)
        if ret == QMessageBox.Ok :
            print("User chose ok")
        else :
            print("User chose cancel")

app = QApplication(sys.argv)

messagebox = MessageBox()
messagebox.show()

app.exec()
```



<figure><img src=".gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (9) (1).png" alt=""><figcaption></figcaption></figure>
