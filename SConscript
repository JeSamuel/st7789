
from building import *

cwd     = GetCurrentDir()
src     = Glob('*.c') + Glob('*.cpp')
path    = [cwd]

group = DefineGroup('st7789', src, depend = ['PKG_USING_ST7789'], CPPPATH = path)

Return('group')
