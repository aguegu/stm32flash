stm32flash:W
================================

*origin from https://code.google.com/p/stm32flash/*

add "-s" argument to enable software flow control, in which data is is sent one by one and with extra delay.

In my experiment, USB to RS232 chips vary in function.

FT232, PL2303 work fine even in baudrate 115200 and without RTS/CTS connection for hardware flow control.

CH340 is not functional without RTS/CTS connection (it would return 

	read_byte: Success
	stm32flash: stm32.c:90: stm32_read_byte: Assertion `0' failed. 
	Aborted (core dumped)

), unless "-s" is specificed.

develop & test on Ubuntu

