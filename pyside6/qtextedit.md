# QTextEdit

`QTextEdit`组件提供一个文本输入小窗。

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
    QTextEdit,
)

class widget(QWidget):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QTextEdit")

        self.textEdit = QTextEdit()

        copy_bt= QPushButton("copy")
        copy_bt.clicked.connect(self.textEdit.copy)

        cut_bt = QPushButton("cut")
        cut_bt.clicked.connect(self.textEdit.cut)


        h_layout = QHBoxLayout()
        h_layout.addWidget(copy_bt)
        h_layout.addWidget(cut_bt)


        v_layout = QVBoxLayout()
        v_layout.addLayout(h_layout)
        v_layout.addWidget(self.textEdit)

        self.setLayout(v_layout)



app = QApplication(sys.argv)

messagebox = widget()
messagebox.show()

app.exec()

```

<figure><img src=".gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>
