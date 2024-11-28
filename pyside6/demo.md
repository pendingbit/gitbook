# Demo

<pre class="language-python"><code class="lang-python"><strong>#main.py
</strong><strong>
</strong><strong>#import the componetes we need
</strong>from PySide6.QtWidgets import QApplication, QWidget

#the sys module is responsible for processing command line argurments
import sys

#start the qt application and input the command line argurments
app = QApplication(sys.argv)

#create a window
window = QWidget()

#display the window
window.show()

#start the event loop
app.exec()
</code></pre>



在命令行输入`python main.py`运行程序

<figure><img src=".gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

