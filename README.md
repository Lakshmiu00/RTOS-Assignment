The three tasks task1(), task2(), and task3() represent our  tasks. By turning the matching motor pins on and off, each task simulates a spinning motor that spins at a particular speed. The contextSwitch() function handles context switching, saving the current task's context and loading the context of the following task.


The relevant pins are assigned as outputs for the motor control by the initializePorts() function. The CTC mode is set for a 1ms interrupt on Timer0 via the initializeTimers() method. Every 1ms, the ISR(TIMER0_COMPA_vect) interrupt service routine is activated, and it calls the function of the active task.

Note that this example uses the avr/io.h and avr/interrupt.h headers for AVR-specific registers and interrupts. Make sure you have the necessary AVR toolchain and libraries set up to compile and upload the code to the ATmega328P microcontroller

