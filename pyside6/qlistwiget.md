# QListWiget

`QListWiget`组件提供列表功能。

## 示例

```python
import sys
from PySide6.QtWidgets import (
    QApplication,
    QPushButton,
    QVBoxLayout,
    QWidget,
    QListWidget,
    QAbstractItemView,
)

class wedgit(QWidget):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QListWidget")

        self.list = QListWidget()
        self.list.setSelectionMode(QAbstractItemView.MultiSelection)
        self.list.addItem("one")
        self.list.addItems(["two","three"])

        add = QPushButton("add")
        add.clicked.connect(self.add_item)
        delete = QPushButton("delete")
        delete.clicked.connect(self.delete_item)

        layout = QVBoxLayout()
        layout.addWidget(self.list)
        layout.addWidget(add)
        layout.addWidget(delete)

        self.setLayout(layout)

    def add_item(self):
        self.list.addItem("new item")
    
    def delete_item(self):
        self.list.takeItem(self.list.currentRow())


app = QApplication(sys.argv)

window = wedgit()
window.show()

app.exec()

```

<figure><img src=".gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
