# LCD Driver 

## Introduction

This project is designed to control an LCD using an AVR microcontroller. The provided code initializes the LCD, sends commands, writes data, and manipulates the cursor position to display text. The main goal is to demonstrate the interaction between the microcontroller and the LCD via the Digital Input/Output (DIO) pins.

## File Structure

- `LCD_prog.c`: Contains the implementation of the functions to interact with the LCD.
- `LCD_int.h`: Header file for the LCD driver, defining the public interface for the LCD functions.
- `DIO_prog.c`: Implementation of the DIO functions to control the microcontroller pins.
- `DIO_int.h`: Header file for the DIO functions, defining the public interface for the DIO operations.
- `registers.h`: Contains the definitions of the microcontroller registers.
- `util.h`: Utility macros for bit manipulation.
- `types.h`: Definition of data types.
- `main.c`: Main program that demonstrates the usage of the LCD driver functions.

## Files and Their Descriptions

### LCD_prog.c

Contains functions to interact with the LCD:
- `LCD_vidWriteData(u8 Copy_Data)`: Writes data to the LCD.
- `LCD_vidSendCommand(u8 Copy_Command)`: Sends a command to the LCD.
- `LCD_vidWriteString(u8 * Copy_String)`: Writes a string to the LCD.
- `LCD_vidInit()`: Initializes the LCD.
- `LCD_vidGoTo(u8 Copy_Row, u8 Copy_Column)`: Sets the cursor to a specified row and column.

### LCD_int.h

Defines the public interface for the LCD functions:
- `#define LCD_u8CLEAR_DISPLAY 0x01`
- `#define LCD_u8RETURN_HOME 0x02`
- Function prototypes for the LCD functions.

### DIO_prog.c

Implementation of the DIO functions:
- `DIO_u8GetPin(u8 Copy_PortX, u8 Copy_PinX)`: Gets the value of a specific pin.
- `DIO_vidSetPinVal(u8 Copy_PortX,u8 Copy_PinX, u8 Copy_Value)`: Sets the value of a specific pin.
- `DIO_vidSetPinDirection(u8 Copy_PortX,u8 Copy_PinX, u8 Copy_Direction)`: Sets the direction of a specific pin.
- `DIO_vidTogglePinVal(u8 Copy_PortX, u8 Copy_PinX)`: Toggles the value of a specific pin.
- `DIO_vidSetPortDirection(u8 Copy_PortX, u8 Copy_Direction)`: Sets the direction of a port.
- `DIO_vidSetPortVal(u8 Copy_PortX, u8 Copy_Value)`: Sets the value of a port.

### DIO_int.h

Defines the public interface for the DIO functions:
- Defines for ports and pins.
- Defines for input and output.
- Function prototypes for the DIO functions.

### registers.h

Contains the definitions of the microcontroller registers:
- `#define DDRA_REG *((volatile u8* )0x3A)`
- `#define PORTA_REG *((volatile u8* )0x3B)`
- ... and other register definitions.

### util.h

Utility macros for bit manipulation:
- `#define SET_BIT(var,bitpos) var=var |(1<<bitpos)`
- `#define CLR_BIT(var,bitpos) var =var &~(1<<bitpos)`
- ... and other utility macros.

### types.h

Definition of data types:
- `typedef unsigned char u8;`
- `typedef signed char  s8;`
- ... and other type definitions.

### main.c

Main program demonstrating the usage of the LCD driver functions:
- Initializes the LCD.
- Loops through rows and columns to display the string "pola" at different positions on the LCD with a delay.

## Usage

1. **Initialization**: Call `LCD_vidInit()` to initialize the LCD.
2. **Writing Data**: Use `LCD_vidWriteData(u8 Copy_Data)` to write data to the LCD.
3. **Sending Commands**: Use `LCD_vidSendCommand(u8 Copy_Command)` to send commands to the LCD.
4. **Writing Strings**: Use `LCD_vidWriteString(u8 * Copy_String)` to write strings to the LCD.
5. **Setting Cursor Position**: Use `LCD_vidGoTo(u8 Copy_Row, u8 Copy_Column)` to set the cursor position on the LCD.

## Conclusion

This project demonstrates how to interface an AVR microcontroller with an LCD, providing functions for initialization, command sending, data writing, and cursor manipulation. The modular design allows for easy integration and reuse in other projects.
