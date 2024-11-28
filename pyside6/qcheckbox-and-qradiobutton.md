# QCheckBox and QRadioButton

`QCheckBox`组件提供单选(复选)框功能

`QRadioButton`组件提供单选功能

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
    QGroupBox,
    QCheckBox,
    QButtonGroup,
    QRadioButton,
)

class wedgit(QWidget):
    def __init__(self):
        super().__init__()

        self.setWindowTitle("QCheckBox and QRadioButton")

        #checkbox 
        os = QGroupBox("Chose operating system")
        check1 = QCheckBox("Windows")
        check2 = QCheckBox("Linux")
        check3 = QCheckBox("Mac")
        checklayout = QVBoxLayout()
        checklayout.addWidget(check1)
        checklayout.addWidget(check2)
        checklayout.addWidget(check3)
        os.setLayout(checklayout)

        #exclusive checkbox
        drink = QGroupBox("Choose your drink")
        beer = QCheckBox("Beer")
        juice = QCheckBox("Juice")
        coffee = QCheckBox("Coffee")
        #set exclusive item
        exclusive_button_group = QButtonGroup(self)
        exclusive_button_group.addButton(beer)
        exclusive_button_group.addButton(juice)
        exclusive_button_group.addButton(coffee)
        exclusive_button_group.setExclusive(True)

        drinklayout = QVBoxLayout()
        drinklayout.addWidget(beer)
        drinklayout.addWidget(juice)
        drinklayout.addWidget(coffee)
        drink.setLayout(drinklayout)

        #Radio Button
        answer = QGroupBox("Choose Answer")
        a = QRadioButton("A")
        b = QRadioButton("B")
        c = QRadioButton("C")
        answerlayout = QVBoxLayout()
        answerlayout.addWidget(a)
        answerlayout.addWidget(b)
        answerlayout.addWidget(c)
        answer.setLayout(answerlayout)

        layout0 = QHBoxLayout()
        layout0.addWidget(os)
        layout0.addWidget(drink)

        layout1 = QVBoxLayout()
        layout1.addLayout(layout0)
        layout1.addWidget(answer)

        self.setLayout(layout1)

app = QApplication(sys.argv)

window = wedgit()
window.show()

app.exec()
```

<figure><img src=".gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>
