# QComboBox

`QComboBox`组件提供下拉菜单。

## 示例

```
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
    QComboBox,
    QTabWidget,
)

class wedgit(QWidget):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QComboBox")
        self.combobox = QComboBox(self)
        self.combobox.addItem("Earth")
        self.combobox.addItems(["Venus","Mars","Pluton","Saturn"])

        button1 = QPushButton("CURRENT")
        button1.clicked.connect(self.current_value)
        button2 = QPushButton("SET CURRENT")
        button2.clicked.connect(self.set_current)
        button3 = QPushButton("GET VALUE")
        button3.clicked.connect(self.get_value)

        layout = QVBoxLayout()
        layout.addWidget(self.combobox)
        layout.addWidget(button1)
        layout.addWidget(button2)
        layout.addWidget(button3)
        self.setLayout(layout)

    def current_value(self):
        print(f"current item: {self.combobox.currentText()}")
        print(f"current index: {self.combobox.currentIndex()}")

    def set_current(self):
        self.combobox.setCurrentIndex(2)

    def get_value(self):
        for i in range(self.combobox.count()):
            print(f"index [{i}] : {self.combobox.itemText(i)}")

app = QApplication(sys.argv)

window = wedgit()
window.show()

app.exec()
```

<figure><img src=".gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>
