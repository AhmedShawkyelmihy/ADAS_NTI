################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include MCAL/Timer/subdir.mk
-include MCAL/EXTINT/subdir.mk
-include MCAL/DIO/subdir.mk
-include MCAL/ADC/subdir.mk
-include HAL/PushButton/subdir.mk
-include HAL/LED/subdir.mk
-include HAL/LCD/subdir.mk
-include HAL/Keypad/subdir.mk
-include HAL/Buzzer/subdir.mk
-include APP/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
ADAS_V3.lss \

FLASH_IMAGE += \
ADAS_V3.hex \

SIZEDUMMY += \
sizedummy \


# All Target
all: ADAS_V3.elf secondary-outputs

# Tool invocations
ADAS_V3.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,ADAS_V3.map -mmcu=atmega32 -o "ADAS_V3.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

ADAS_V3.lss: ADAS_V3.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S ADAS_V3.elf  >"ADAS_V3.lss"
	@echo 'Finished building: $@'
	@echo ' '

ADAS_V3.hex: ADAS_V3.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex ADAS_V3.elf  "ADAS_V3.hex"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: ADAS_V3.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega32 ADAS_V3.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) ADAS_V3.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
