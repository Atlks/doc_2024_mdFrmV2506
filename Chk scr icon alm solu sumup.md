Chk scr icon alm solu sumup

Skuli not easy dbg


Use python+opencv more easy


import time
from time import sleep

from PIL import ImageGrab
import cv2
import numpy as np



# pip install playsound==1.2.2
# skuli not take effk
# pip install
#  pip install Pillow
#//  pip install opencv-python
# pip install playsound

# pip install screeninfo

from playsound import playsound

# 播放音乐文件
#playsound(r"C:\db\海鸣威-老人与海.mp3")
#playsound("C:\\db\\laor.mp3")


from PIL import Image
import mss

def getSecScr():
    # 获取显示器信息
    with mss.mss() as sct:
        # 获取所有屏幕的信息
        monitors = sct.monitors
        if len(monitors) < 2:
            raise Exception("没有找到第二个显示器。")

        # 打印所有显示器的信息
        for i, monitor in enumerate(monitors):
            print(f"Monitor {i}: {monitor['width']}x{monitor['height']} at {monitor['left']},{monitor['top']}")

        # 假设第二个屏幕是第二个显示器（索引为1）
        second_monitor = monitors[2]  # mss 中的 monitors 从 1 开始计数
        bbox = (second_monitor['left'], second_monitor['top'],
                second_monitor['left'] + second_monitor['width'],
                second_monitor['top'] + second_monitor['height'])

        # 截取第二个屏幕的内容
        img = sct.grab(bbox)

        # 转换为 PIL 图像并保存
        img_pil = Image.frombytes("RGB", img.size, img.bgra, "raw", "BGRX")
        img_pil.save("second_screen.png")  # 保存截屏

    print("第二个屏幕的截图已保存为 'second_screen.png'")

def foreachx():
    # 截屏
    getSecScr()
    #screenshot = ImageGrab.grab()
    # screenshot.save("screenshot.png")

    # 查找图标
    screenshot = cv2.imread("second_screen.png")
    icon = cv2.imread("C:/db/ggl.jpg")
    result = cv2.matchTemplate(screenshot, icon, cv2.TM_CCOEFF_NORMED)
    #print("matchTemplate#result:"+result)
   # print(f"matchTemplate#result: {result.tolist()}")  # 转换为列表再打印
    #print("matchTemplate#result: " + str(result))
    # 检测匹配度
    threshold = 0.4
    locations = np.where(result >= threshold)

    if locations[0].size > 0:
        print("图标找到，位置：", locations)
        from playsound import playsound

        # 播放音乐文件
        playsound("C:\\db\\laor.mp3")  # 替换为你的音乐文件路径
    else:
        print("图标未找到。")


while True:
    print("这是一个无限循环，每 5 秒打印一次。")
   # time.sleep(5)  # 暂停 5 秒
    foreachx()
    # 等待 5 秒
    sleep(5)

