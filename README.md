# RT_ds18b20

## Description:

This library is used to control one or more DS18B20 digital thermometers
with STM32 HAL.

## Basic example:

```
float temp;
uint8_t dirb [8] = {0};

DS18B20_Reset_CMD(DS_GPIO_Port, DS_Pin);
DS18B20_ReadROM_CMD(DS_GPIO_Port, DS_Pin, dirb);
DS18B20_Reset_CMD(DS_GPIO_Port, DS_Pin);
DS18B20_SetResolution(DS_GPIO_Port, DS_Pin, dirb, DS18B20_RESOLUTION_10);

DS18B20_All_Convert(DS_GPIO_Port, DS_Pin);
temp = DS18B20_Read_Temp(DS_GPIO_Port, DS_Pin, dirb);
```

## Warning:
Before sending each command (ending in _CMD()), use the ```DS18B20_Reset_CMD()``` function.

The GPIO used must be OUTPUT OPEN DRAIN and HIGH OUTPUT SPEED.

Configure the delayMicros() function in your main.c or in RT_ds18b20.c


Copyright (C) 2021 Rubén Torres Bermúdez