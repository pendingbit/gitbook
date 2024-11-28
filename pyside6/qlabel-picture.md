# QLabel-Picture

使用`QLabel`组件插入图片

## 示例

```python
import sys
from PySide6.QtGui import QPixmap
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

        self.setWindowTitle("QLabel")

        image = QLabel()
        image.setPixmap(QPixmap("./pic.png"))


        v_layout = QVBoxLayout()
        v_layout.addWidget(image)

        self.setLayout(v_layout)

app = QApplication(sys.argv)

messagebox = widget()
messagebox.show()

app.exec()
```

<figure><img src=".gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>
