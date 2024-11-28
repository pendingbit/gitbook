# QPushButton QLabel QLineEdit

`QPushButton`组件提供按键功能。

`QLabel`组件提供文本显示。

`QLineEdit`组件提供文本输入。

## 示例

```python
import sys
from PySide6.QtWidgets import (
    QApplication,
    QLabel,
    QPushButton,
    QVBoxLayout,
    QHBoxLayout,
    QWidget,
    QLineEdit,
)

class MessageBox(QWidget):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QMessageBox")

        button = QPushButton("BUTTON")
        button.clicked.connect(self.button_respond)

        label = QLabel("my label : ")
        lineedit = QLineEdit() 
        lineedit.textChanged.connect(self.lineedit_respond)

        h_layout = QHBoxLayout()
        h_layout.addWidget(label)
        h_layout.addWidget(lineedit)


        v_layout = QVBoxLayout()
        v_layout.addLayout(h_layout)
        v_layout.addWidget(button)

        self.setLayout(v_layout)


    def button_respond(self):
        print("Button is clicked")
    
    def lineedit_respond(self,data):
        print("input data is: ", data)


app = QApplication(sys.argv)

messagebox = MessageBox()
messagebox.show()

app.exec()

```

<figure><img src=".gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>
