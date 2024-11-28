# Compiling .ui Files to Python

将.UI文件编译成python文件

```
Command：
    pyside6-uic widget.ui > ui_widget.py
```

```python
# -*- coding: utf-8 -*-

################################################################################
## Form generated from reading UI file 'widget.ui'
##
## Created by: Qt User Interface Compiler version 6.8.0
##
## WARNING! All changes made in this file will be lost when recompiling UI file!
################################################################################

from PySide6.QtCore import (QCoreApplication, QDate, QDateTime, QLocale,
    QMetaObject, QObject, QPoint, QRect,
    QSize, QTime, QUrl, Qt)
from PySide6.QtGui import (QBrush, QColor, QConicalGradient, QCursor,
    QFont, QFontDatabase, QGradient, QIcon,
    QImage, QKeySequence, QLinearGradient, QPainter,
    QPalette, QPixmap, QRadialGradient, QTransform)
from PySide6.QtWidgets import (QApplication, QHBoxLayout, QLabel, QLineEdit,
    QPushButton, QSizePolicy, QVBoxLayout, QWidget)

class Ui_widget(object):
    def setupUi(self, widget):
        if not widget.objectName():
            widget.setObjectName(u"widget")
        widget.resize(411, 111)
        self.verticalLayout = QVBoxLayout(widget)
        self.verticalLayout.setObjectName(u"verticalLayout")
        self.horizontalLayout = QHBoxLayout()
        self.horizontalLayout.setObjectName(u"horizontalLayout")
        self.name_label = QLabel(widget)
        self.name_label.setObjectName(u"name_label")

        self.horizontalLayout.addWidget(self.name_label)

        self.name_line_edit = QLineEdit(widget)
        self.name_line_edit.setObjectName(u"name_line_edit")

        self.horizontalLayout.addWidget(self.name_line_edit)


        self.verticalLayout.addLayout(self.horizontalLayout)

        self.horizontalLayout_2 = QHBoxLayout()
        self.horizontalLayout_2.setObjectName(u"horizontalLayout_2")
        self.job_label = QLabel(widget)
        self.job_label.setObjectName(u"job_label")

        self.horizontalLayout_2.addWidget(self.job_label)

        self.job_line_edit = QLineEdit(widget)
        self.job_line_edit.setObjectName(u"job_line_edit")

        self.horizontalLayout_2.addWidget(self.job_line_edit)


        self.verticalLayout.addLayout(self.horizontalLayout_2)

        self.commit_button = QPushButton(widget)
        self.commit_button.setObjectName(u"commit_button")

        self.verticalLayout.addWidget(self.commit_button)


        self.retranslateUi(widget)

        QMetaObject.connectSlotsByName(widget)
    # setupUi

    def retranslateUi(self, widget):
        widget.setWindowTitle(QCoreApplication.translate("widget", u"Form", None))
        self.name_label.setText(QCoreApplication.translate("widget", u"NAME", None))
        self.job_label.setText(QCoreApplication.translate("widget", u"JOB", None))
        self.commit_button.setText(QCoreApplication.translate("widget", u"Commit", None))
    # retranslateUi
```

使用ui\_widget.py开发

```python
import sys
from PySide6 import QtWidgets
from PySide6.QtWidgets import QWidget
from ui_widget import Ui_widget

class Widget(QWidget, Ui_widget):
    def __init__(self):
        super().__init__()
        self.setupUi(self)
        self.setWindowTitle("user data")
        self.commit_button.clicked.connect(self.fun)
    
    def fun(self):
        print(f"{self.name_line_edit.text()} is a {self.job_line_edit.text()}")

app = QtWidgets.QApplication(sys.argv)

window = Widget()
window.show()

app.exec()
```

