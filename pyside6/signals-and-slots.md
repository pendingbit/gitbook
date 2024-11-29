# Signals and Slots

控件触发事件产生信号，与信号相关联的函数(slots)会被调用。

## Button控件

```python
from PySide6.QtWidgets import QApplication, QPushButton

#the slot(function) : responds when button clicked
def button_clicked():
    print("You clicked the button!")
    
app = QApplication()

button = QPushButton("Press Me!")
#connect the signal and slot
button.clicked.connect(button_clicked)
button.show()

app.exec()
```

<figure><img src=".gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

## Slider控件

```python
from PySide6.QtCore import Qt
from PySide6.QtWidgets import QApplication, QSlider

#the slot(function) : responds when slider value changed
def respond_to_slider(data):
    print("slider moved to : ", data)

app = QApplication()

slider = QSlider(Qt.Horizontal)
slider.setMinimum(1)
slider.setMaximum(100)
slider.setValue(25)
slider.valueChanged.connect(respond_to_slider)
slider.show()

app.exec()

```

<figure><img src=".gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>
