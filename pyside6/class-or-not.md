# Class or not

## 全局

```python
#Global scope
from PySide6.QtWidgets import QApplication, QMainWindow, QPushButton
import sys

app = QApplication(sys.argv)

window = QMainWindow()
window.setWindowTitle("our first mainwindow app!")

button = QPushButton()
button.setText("Press Me")

window.setCentralWidget(button)
window.show()

app.exec()

```

## 类继承

```python
from PySide6.QtWidgets import QApplication, QMainWindow, QPushButton
import sys

#Subclass QMainWindow to customize your application's main window
class ButtonHolder(QMainWindow):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("Button Holder app")
        button = QPushButton("Press Me!")
        #set our button as the central widget
        self.setCentralWidget(button)
    
app = QApplication(sys.argv)
window = ButtonHolder()
window.show()
app.exec()
```





