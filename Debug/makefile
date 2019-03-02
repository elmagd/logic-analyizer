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

sizedummy: logic_analyizer.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega16 logic_analyizer.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(ELFS)$(OBJS)$(ASM_DEPS)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) logic_analyizer.elf
	-@echo ' '

secondary-outputs: $(LSS) $(SIZEDUMMY)

.PHONY: all clean dependents

-include ../makefile.targets
