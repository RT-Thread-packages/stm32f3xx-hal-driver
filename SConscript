from building import *
import os

cwd = GetCurrentDir()
path = [os.path.join(cwd, 'Inc')]
src_path = os.path.join(cwd, 'Src')

CPPDEFINES = ['USE_HAL_DRIVER']

src = [
os.path.join(src_path, 'stm32f3xx_hal.c'),
os.path.join(src_path, 'stm32f3xx_hal_cec.c'),
os.path.join(src_path, 'stm32f3xx_hal_cortex.c'),
os.path.join(src_path, 'stm32f3xx_hal_crc.c'),
os.path.join(src_path, 'stm32f3xx_hal_crc_ex.c'),
os.path.join(src_path, 'stm32f3xx_hal_exti.c'),
os.path.join(src_path, 'stm32f3xx_hal_dma.c'),
os.path.join(src_path, 'stm32f3xx_hal_pwr.c'),
os.path.join(src_path, 'stm32f3xx_hal_pwr_ex.c'),
os.path.join(src_path, 'stm32f3xx_hal_rcc.c'),
os.path.join(src_path, 'stm32f3xx_hal_rcc_ex.c'),
os.path.join(src_path, 'stm32f3xx_hal_sram.c'),
os.path.join(src_path, 'stm32f3xx_hal_gpio.c'),
]

if GetDepend(['RT_USING_SERIAL']) or GetDepend(['RT_USING_NANO', 'RT_USING_CONSOLE']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_uart.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_uart_ex.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_usart.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_usart_ex.c')]
    

if GetDepend(['RT_USING_I2C']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_i2c.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_i2c_ex.c')]

if GetDepend(['RT_USING_SPI']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_spi.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_spi_ex.c')]

if GetDepend(['RT_USING_USB']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_pcd.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_pcd_ex.c')]
    src += [os.path.join(src_path, 'stm32f3xx_ll_usb.c')]

if GetDepend(['RT_USING_CAN']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_can.c')]

if GetDepend(['RT_USING_HWTIMER']) or GetDepend(['RT_USING_PWM']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_tim.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_tim_ex.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_hrtim.c')]

if GetDepend(['RT_USING_ADC']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_adc.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_adc_ex.c')]

if GetDepend(['RT_USING_RTC']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_rtc.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_rtc_ex.c')]

if GetDepend(['RT_USING_WDT']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_iwdg.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_wwdg.c')]

if GetDepend(['RT_USING_AUDIO']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_i2s.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_i2s_ex.c')]
 
if GetDepend(['RT_USING_MTD_NOR']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_nor.c')]

if GetDepend(['RT_USING_MTD_NAND']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_nand.c')]
    
if GetDepend(['BSP_USING_SDRAM']):
    src += [os.path.join(src_path, 'stm32f3xx_ll_fmc.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_sram.c')]
    
if GetDepend(['BSP_USING_ON_CHIP_FLASH']):
    src += [os.path.join(src_path, 'stm32f3xx_hal_flash.c')]
    src += [os.path.join(src_path, 'stm32f3xx_hal_flash_ex.c')]


group = DefineGroup('STM32F3-HAL', src, depend = ['PKG_USING_STM32F3_HAL_DRIVER'], CPPPATH = path, CPPDEFINES = CPPDEFINES)

Return('group')
