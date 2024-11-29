# Grid Layout

使用`QGridLayout`函数创建的layout将组件以坐标形式布局。

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
    QGridLayout,
)

class wedgit(QWidget):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QGridLayout")

        button1 = QPushButton("one")
        button2 = QPushButton("two")
        button3 = QPushButton("three")
        button3.setSizePolicy(QSizePolicy.Expanding, QSizePolicy.Expanding)
        button4 = QPushButton("four")
        button5 = QPushButton("five")
        button6 = QPushButton("six")
        button7 = QPushButton("seven")

        layout = QGridLayout()
        layout.addWidget(button1,0,0)
        layout.addWidget(button2,0,1,1,2)  #take up 1 row and 2 columns
        layout.addWidget(button3,1,0,2,1)  #tak up 2 rows and 1 column
        layout.addWidget(button4,1,1)
        layout.addWidget(button5,1,2)
        layout.addWidget(button6,2,1)
        layout.addWidget(button7,2,2)

        self.setLayout(layout)


app = QApplication(sys.argv)

window = wedgit()
window.show()

app.exec()

```

<figure><img src=".gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>
