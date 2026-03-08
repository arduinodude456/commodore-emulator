# commodore-emulator
A software to emulate old commodore Computers like C64, Amiga with an ESP32 and FabGL
## In a nutshell
A modified version of @sl001 's TinyBASIC-Interpreter is used to run the OS, which contains of BASIC Programs saved in Flash (SPIFFS). The Software was developed originally for ESP-WROOM-32.
## Possibilities
### List of devices possible to emulate
Actual in version 0.1 supported devices are
**Commodore 64**
**Amiga A1000 with OS V1.3**
**AD-5364** (F.O. IBM PC)
## How to select a device
To select a device, you have to define / undef the ones you want.
```
#undef MULTIPLATFORM

#define EM_C64
#undef EM_A1000
#undef ADOS
```
You also have to set up the free memory and stuff l. this:
```
#define RAM_SIZE 64 //maximal 64K, minimal 16K is needed by OS.
#define COLOR_DEPHT 32 //32 colours by default
/\* Software Interlace couldt save 30% of the RAM. \*/
#undef SOFTWARE_INTERLACE
/\* You know this from Amiga!!!\*/
#undef HOLD_AND MODIFY
/\*This feature is only needed for ADOS Device, it makes possible a multidimensional file storage (folders etc.)\*/
#define USE_MULTIDIM_FOLDERS
```
