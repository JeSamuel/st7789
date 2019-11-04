
from building import *
Import('rtconfig')
src   = []
cwd   = GetCurrentDir()

if GetDepend('PKG_USING_ST7789'):
    src += Glob('src/drv_st7789_lcd.c')

path  = [cwd + '/inc']

group = DefineGroup('st7789', src, depend = ['PKG_USING_ST7789'], CPPPATH = path)

Return('group')
