'''# -*- coding:utf-8 -*-

    import ctypes

    import os

    from PyQt5.QtWidgets import QApplication

    def capture():

        clipboard=QApplication.clipboard()

        try:

            dll = ctypes.cdll.LoadLibrary('PrScrn.dll')

            dataImage = clipboard.pixmap()

            dataImage.save('Grab.png')

        except Exception:

            print("Dll load error!")

            return

        else:

            try:

                dll.PrScrn(0)

                dataImage = clipboard.pixmap()

                dataImage.save('Grab.png')

            except Exception:

                print("Sth wrong in capture!")

                return
'''
主要是使用剪贴板传递图片并保存


