################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
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
logic_analyizer.lss \

FLASH_IMAGE += \
logic_analyizer.hex \

EEPROM_IMAGE += \
logic_analyizer.eep \

SIZEDUMMY += \
sizedummy \


# All Target
all: logic_analyizer.elf secondary-outputs

# Tool invocations
logic_analyizer.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,logic_analyizer.map -mmcu=atmega16 -o "logic_analyizer.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

logic_analyizer.lss: logic_analyizer.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S logic_analyizer.elf  >"logic_analyizer.lss"
	@echo 'Finished building: $@'
	@echo ' '

logic_analyizer.hex: logic_analyizer.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex logic_analyizer.elf  "logic_analyizer.hex"
	@echo 'Finished building: $@'
	@echo ' '

logic_analyizer.eep: logic_analyizer.elf
	@echo 'Create eeprom image (ihex format)'
	-avr-objcopy -j .eeprom --no-change-warnings --change-section-lma .eeprom=0 -O ihex logic_analyizer.elf  "logic_analyizer.eep"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: logic_analyizer.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega16 logic_analyizer.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(EEPROM_IMAGE)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) logic_analyizer.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(EEPROM_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents

-include ../makefile.targets
