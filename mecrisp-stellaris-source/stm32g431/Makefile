# STM32G431

ARMGNU?=arm-none-eabi

COPS = -Wall  -Os -nostdlib -nostartfiles -ffreestanding -save-temps
AOPS = --warn --fatal-warnings

all : mecrisp-stellaris-stm32g431.bin 

mecrisp-stellaris-stm32g431.o : mecrisp-stellaris-stm32g431.s
	$(ARMGNU)-as mecrisp-stellaris-stm32g431.s -g -o mecrisp-stellaris-stm32g431.o

mecrisp-stellaris-stm32g431.bin : memmap mecrisp-stellaris-stm32g431.o
	$(ARMGNU)-ld -g -o mecrisp-stellaris-stm32g431.elf -T memmap mecrisp-stellaris-stm32g431.o
	$(ARMGNU)-objdump -D mecrisp-stellaris-stm32g431.elf > mecrisp-stellaris-stm32g431.list
	$(ARMGNU)-objcopy mecrisp-stellaris-stm32g431.elf mecrisp-stellaris-stm32g431.bin -O binary

clean:
	rm -f *.bin
	rm -f *.o
	rm -f *.elf
	rm -f *.list
