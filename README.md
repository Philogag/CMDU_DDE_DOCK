# CMDU_DDE_DOCK
深度 Linux 系统网速任务栏插件，鼠标悬浮显示开机时间、CPU使用率、内存使用率、下载字节、上传字节。  

![alt](preview.png)  
内存占用大于90%时显示为红色以示警告，注意减少内存预防死机。  
![alt](preview90.png)  

改进：网速全统计，不再有为 0 的情况。  
安装：终端 ./install.sh  
卸载：终端 ./uninstall.sh  


## Build

#### Env
```
$ sudo apt-get install -y dde-dock-dev qt5-default qtbase5-dev-tools pkg-config cmake g++
```

#### Build command & Output for build successfully
```
$ qmake cmdu.pro
$ make
g++ -c -m64 -pipe -O2 -std=gnu++11 -Wall -W -D_REENTRANT -fPIC -DQT_NO_DEBUG -DQT_PLUGIN -DQT_WIDGETS_LIB -DQT_GUI_LIB -DQT_CORE_LIB -I. -isystem /usr/include/x86_64-linux-gnu/qt5 -isystem /usr/include/x86_64-linux-gnu/qt5/QtWidgets -isystem /usr/include/x86_64-linux-gnu/qt5/QtGui -isystem /usr/include/x86_64-linux-gnu/qt5/QtCore -I. -I/usr/lib/x86_64-linux-gnu/qt5/mkspecs/linux-g++-64 -o cmduplugin.o cmduplugin.cpp
g++ -c -m64 -pipe -O2 -std=gnu++11 -Wall -W -D_REENTRANT -fPIC -DQT_NO_DEBUG -DQT_PLUGIN -DQT_WIDGETS_LIB -DQT_GUI_LIB -DQT_CORE_LIB -I. -isystem /usr/include/x86_64-linux-gnu/qt5 -isystem /usr/include/x86_64-linux-gnu/qt5/QtWidgets -isystem /usr/include/x86_64-linux-gnu/qt5/QtGui -isystem /usr/include/x86_64-linux-gnu/qt5/QtCore -I. -I/usr/lib/x86_64-linux-gnu/qt5/mkspecs/linux-g++-64 -o cmduwidget.o cmduwidget.cpp
/usr/lib/x86_64-linux-gnu/qt5/bin/rcc -name res res.qrc -o qrc_res.cpp
g++ -c -m64 -pipe -O2 -std=gnu++11 -Wall -W -D_REENTRANT -fPIC -DQT_NO_DEBUG -DQT_PLUGIN -DQT_WIDGETS_LIB -DQT_GUI_LIB -DQT_CORE_LIB -I. -isystem /usr/include/x86_64-linux-gnu/qt5 -isystem /usr/include/x86_64-linux-gnu/qt5/QtWidgets -isystem /usr/include/x86_64-linux-gnu/qt5/QtGui -isystem /usr/include/x86_64-linux-gnu/qt5/QtCore -I. -I/usr/lib/x86_64-linux-gnu/qt5/mkspecs/linux-g++-64 -o qrc_res.o qrc_res.cpp
/usr/lib/x86_64-linux-gnu/qt5/bin/moc -DQT_NO_DEBUG -DQT_PLUGIN -DQT_WIDGETS_LIB -DQT_GUI_LIB -DQT_CORE_LIB -I/usr/lib/x86_64-linux-gnu/qt5/mkspecs/linux-g++-64 -I/home/philogag/Desktop/CMDU_DDE_DOCK -I/usr/include/x86_64-linux-gnu/qt5 -I/usr/include/x86_64-linux-gnu/qt5/QtWidgets -I/usr/include/x86_64-linux-gnu/qt5/QtGui -I/usr/include/x86_64-linux-gnu/qt5/QtCore -I/usr/include -I/usr/local/include cmduplugin.h -o moc_cmduplugin.cpp
g++ -c -m64 -pipe -O2 -std=gnu++11 -Wall -W -D_REENTRANT -fPIC -DQT_NO_DEBUG -DQT_PLUGIN -DQT_WIDGETS_LIB -DQT_GUI_LIB -DQT_CORE_LIB -I. -isystem /usr/include/x86_64-linux-gnu/qt5 -isystem /usr/include/x86_64-linux-gnu/qt5/QtWidgets -isystem /usr/include/x86_64-linux-gnu/qt5/QtGui -isystem /usr/include/x86_64-linux-gnu/qt5/QtCore -I. -I/usr/lib/x86_64-linux-gnu/qt5/mkspecs/linux-g++-64 -o moc_cmduplugin.o moc_cmduplugin.cpp
/usr/lib/x86_64-linux-gnu/qt5/bin/moc -DQT_NO_DEBUG -DQT_PLUGIN -DQT_WIDGETS_LIB -DQT_GUI_LIB -DQT_CORE_LIB -I/usr/lib/x86_64-linux-gnu/qt5/mkspecs/linux-g++-64 -I/home/philogag/Desktop/CMDU_DDE_DOCK -I/usr/include/x86_64-linux-gnu/qt5 -I/usr/include/x86_64-linux-gnu/qt5/QtWidgets -I/usr/include/x86_64-linux-gnu/qt5/QtGui -I/usr/include/x86_64-linux-gnu/qt5/QtCore -I/usr/include -I/usr/local/include cmduwidget.h -o moc_cmduwidget.cpp
g++ -c -m64 -pipe -O2 -std=gnu++11 -Wall -W -D_REENTRANT -fPIC -DQT_NO_DEBUG -DQT_PLUGIN -DQT_WIDGETS_LIB -DQT_GUI_LIB -DQT_CORE_LIB -I. -isystem /usr/include/x86_64-linux-gnu/qt5 -isystem /usr/include/x86_64-linux-gnu/qt5/QtWidgets -isystem /usr/include/x86_64-linux-gnu/qt5/QtGui -isystem /usr/include/x86_64-linux-gnu/qt5/QtCore -I. -I/usr/lib/x86_64-linux-gnu/qt5/mkspecs/linux-g++-64 -o moc_cmduwidget.o moc_cmduwidget.cpp
rm -f libHTYCMDU.so
g++ -m64 -Wl,-O1 -shared -o libHTYCMDU.so cmduplugin.o cmduwidget.o qrc_res.o moc_cmduplugin.o moc_cmduwidget.o  -L/usr/X11R6/lib64 -L/usr/lib/x86_64-linux-gnu -lQt5Widgets -lQt5Gui -lQt5Core -lGL -lpthread
```
