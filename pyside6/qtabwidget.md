# QTabWidget

`QTabWidget`组件提供多页显示功能。

## 示例

```python
import sys
from PySide6.QtWidgets import (
    QLineEdit,
    QLabel,
    QApplication,
    QWidget,
    QPushButton,
    QHBoxLayout,
    QVBoxLayout,
    QWidget,
    QListWidget,
    QAbstractItemView,
    QTabWidget,
)

class wedgit(QWidget):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QTabWidget")
        tabs = QTabWidget()

        widget1 = QWidget()
        label = QLabel("Full name:")
        edit = QLineEdit()
        layout1 = QHBoxLayout()
        layout1.addWidget(label)
        layout1.addWidget(edit)
        widget1.setLayout(layout1)

        widget2 = QWidget()
        button1 = QPushButton("KEY1")
        button2 = QPushButton("KEY2")
        layout2 = QVBoxLayout()
        layout2.addWidget(button1)
        layout2.addWidget(button2)
        widget2.setLayout(layout2)

        tabs.addTab(widget1,"info")
        tabs.addTab(widget2,"button")

        layout = QVBoxLayout()
        layout.addWidget(tabs)
        self.setLayout(layout)


app = QApplication(sys.argv)

window = wedgit()
window.show()

app.exec()
```

<figure><img src=".gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

<figure><img src=".gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>
