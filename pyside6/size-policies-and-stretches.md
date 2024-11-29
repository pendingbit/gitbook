# Size policies and stretches

`setSizePolicy` 函数用于设置窗口大小调整后，组件X Y方向上的变化，可以固定，也可以扩大。

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
    QSizePolicy,
)

class wedgit(QWidget):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QMessageBox")

        button1 = QPushButton("BUTTON1")
        button2 = QPushButton("BUTTON2")
        button3 = QPushButton("BUTTON3")

        label = QLabel("my label : ")
        lineedit = QLineEdit() 
        lineedit.setSizePolicy(QSizePolicy.Expanding, QSizePolicy.Fixed)#水平扩张，垂直固定
        label.setSizePolicy(QSizePolicy.Expanding, QSizePolicy.Expanding)#水平、垂直扩展
        h_layout = QHBoxLayout()
        h_layout.addWidget(label)
        h_layout.addWidget(lineedit)

        h1_layout = QHBoxLayout()
        h1_layout.addWidget(button1,2)#组件占用空间比例为2
        h1_layout.addWidget(button2,1)#组件占用空间比例为1
        h1_layout.addWidget(button3,1)#组件占用空间比例为1

        v_layout = QVBoxLayout()
        v_layout.addLayout(h_layout)
        v_layout.addLayout(h1_layout)

        self.setLayout(v_layout)


app = QApplication(sys.argv)

window = wedgit()
window.show()

app.exec()
```

<figure><img src=".gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>
