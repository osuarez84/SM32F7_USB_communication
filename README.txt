***********************
NOTAS sobre el programa		=> ESTE PROGRAMA FUNCIONA CORRECTAMENTE.
***********************
AUTOR : Omar Suárez
FECHA : 2017.03.16

=> El fichero "usb_test.ioc" contiene el proyecto generado en STM32CubeMX para
trabajar con:
	=> USB OTG HS
	=> HSI a 16MHz => HCLK a 168MHz
	=> Configuration >> Connectivity >> VBUS >> Enable

http://microtechnics.ru/en/stm32cube-and-usb-virtual-com-port-2/
http://stackoverflow.com/questions/33549084/stm32cubemx-usb-cdc-vcp


=> Es necesario instalar el driver para el micro:
	=> D:\01_Omar\02_CEMITEC\01_ARM\02_STM32F7\05_ST_vCOM_driver\en.stsw-stm32102


=> Me surgio un problema al conetar el USB al PC:
	En el Administrador de Dispositivos me aparecía el COM perteneciente
	a la tarjeta Discovery junto a una señal de exclamación amarilla indicando
	que no funcionaba bien.
	Tras buscar en varios foros encontré una posible solución al problema:
		=> Aumentar el Stack_Size y el Heap_Size en el fichero de startup.
			(Stack_Size = 0x00004000 y Heap_Size = 0x00002000)
		Después de esto ha funcionado correctamente el dispositivo, pero ahora 
		mismo no tengo muy claro que implica cambiar esos valores.

https://community.st.com/thread/26387
https://community.st.com/thread/36742-stm32f4-usb-virtual-com-port-weird-problemsettings-solved