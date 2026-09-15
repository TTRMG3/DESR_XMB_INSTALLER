# DESR XMB Installer v1.2 — Stable

**by Teo Tormo**

## English

**DESR XMB Installer v1.2 Stable** creates PSX DESR XMB entries directly on the console. It installs ELF homebrew applications, turns HDL games already on the internal HDD into XMB launchers, and installs owned ISO images from USB or MX4SIO in HDL format. No Ethernet-connected PC, NBD driver or manual APA-header editing is required.

## Features

- Install any ELF in `DESR_XMB_Installer/APPS` as an XMB application.
- Bundled installable apps: PicoDrive, FCEUMM, wLaunchELF R3Z, uLaunchELF 2TB, OPL, HDL Game Installer and DESR XMB Installer.
- Install owned ISO images from USB or MX4SIO to the internal HDD in HDL format.
- Create XMB launchers for games installed from ISO or previously with HDL Game Installer. The launcher uses OPL and prepares `+OPL` automatically when required.
- Choose from 8 GAME icons and 8 application icons: HOME/BREW, EMU, HD TOOL and LAUNCH, including light variants.
- Ignore `.DS_Store` and other macOS hidden files while scanning ELF and ISO folders.
- Spanish/English UI.
- Separate **Delete installed applications** and **Delete installed games** operations.
- ISO copy progress, with **SELECT** to cancel: the destination is closed, HDL is unmounted and the incomplete installation is removed when possible.

## First run

1. Use a Free McBoot memory card prepared for PSX DESR.
2. Copy `DESR_XMB_Installer.ELF` and the `DESR_XMB_Installer` folder to the root of a compatible USB device.
3. Start **wLaunchELF R3Z** from the card and run `mass:/DESR_XMB_Installer.ELF`.
4. Select a language. Use the D-pad to move, `X` to confirm and `Triangle` to go back.

Keep **uLaunchELF 2TB Edition** available for partition inspection or recovery. Do not use R3Z for delicate operations on hidden `__.` partitions.

## Install an ELF application

Place an ELF in `DESR_XMB_Installer/APPS`, choose **Install ELF application**, select the ELF and one of the eight application icons. Restart the DESR when complete to see the XMB entry. `APPS/DESR_XMB_Installer.elf` is this same version, so the installer itself can be installed in the XMB.

## Install an ISO to HDD

Place an owned ISO in `DESR_XMB_Installer/ISO` on USB or MX4SIO. Choose **Install ISO to HDD**, the source device, the ISO and a GAME icon. The installer creates the HDL installation, copies the ISO, prepares `+OPL`, hides the game and creates its XMB launcher. That launcher opens OPL and starts the matching game.

Press **SELECT** during copy to cancel safely. Keep power stable and do not remove USB/MX4SIO while copying. Performance and game compatibility depend on storage, OPL and the individual title.

## Install HDD HDL games in XMB as executables

For a game already installed with HDL Game Installer, choose **Install HDD HDL games in XMB as executables**, select a visible game and a GAME icon. The installer hides its HDL partition and creates an OPL-backed XMB launcher.

## Delete installed content

- **Delete installed applications** lists XMB applications and removes the selected one.
- **Delete installed games** lists linked games by their XMB title rather than only by product code.

### Known limitation: HDL game deletion

On the tested DESR systems, deleting a game can remove the normal launcher and game but leave a temporary `PP.DEL-…` partition visible in XMB as **Corrupted Data**. If this happens, select that Corrupted Data icon in XMB and confirm deletion to complete cleanup. It can also be inspected with uLaunchELF 2TB Edition. This does not affect deletion of XMB applications.

## USB layout

```text
DESR_XMB_Installer.ELF
DESR_XMB_Installer/
  APPS/                 ← your ELF files and bundled apps
  ISO/                  ← owned ISO images to install
  EXECUTE.KELF          ← generated while installing
  OPL-LAUNCHER.ELF
  OPL-RUNTIME.ELF
```

## Hardware testing

This stable version was tested on real hardware with the same functional results on:

| Model | Firmware |
| --- | --- |
| PSX DESR 7500 | 2.11 |
| PSX DESR 5100S | 1.31 |

Both systems were used to test application installation, icons, HDL/OPL game launchers, ISO installation from external storage and the game-deletion behavior described above. These are practical tests, not a full compatibility guarantee for every firmware, drive, USB device, MX4SIO device or game.

## Notes and credits

Required keys are integrated into this executable; do not distribute keys separately. The package contains no games, ISO images or BIOS. Use only dumps of games you own and back up the internal HDD before experimenting with partitions.

Built with appreciation for **ps2dev / PS2SDK**, **Open PS2 Loader**, **HDLGameInstaller**, **wLaunchELF R3Z**, **uLaunchELF 2TB Edition**, **PicoDrive**, **FCEUMM**, **psx-osdsys**, PSX-Place and everyone preserving and testing PS2/DESR hardware. Hugs, love and long live homebrew.

---

## Español

DESR XMB Installer crea entradas para el XMB de PSX DESR desde la propia consola. Instala aplicaciones homebrew ELF, convierte juegos HDL ya presentes en el disco interno en accesos ejecutables del XMB e instala ISO propias desde USB o MX4SIO en formato HDL. No requiere un PC conectado por Ethernet, NBD ni editar a mano cabeceras APA.

## Funciones

- Instala cualquier ELF de `DESR_XMB_Installer/APPS` como aplicación XMB.
- Incluye PicoDrive, FCEUMM, wLaunchELF R3Z, uLaunchELF 2TB, OPL, HDL Game Installer y DESR XMB Installer para instalarlos directamente desde la consola.
- Instala ISO propias desde USB o MX4SIO al HDD en formato HDL.
- Crea una entrada XMB para juegos instalados desde ISO o previamente con HDL Game Installer. El lanzador usa OPL y prepara `+OPL` automáticamente cuando hace falta.
- Permite escoger entre 8 iconos GAME y 8 iconos de aplicaciones: HOME/BREW, EMU, HD TOOL y LAUNCH, con variantes claras.
- Ignora `.DS_Store` y otros archivos ocultos de macOS al buscar ELF e ISO.
- Ofrece interfaz bilingüe en español e inglés.
- Incluye **Borrar aplicaciones instaladas** y **Borrar juegos instalados**.
- Muestra el progreso durante la copia de ISO. Pulsa **SELECT** para cancelarla: cierra el destino, desmonta HDL e intenta eliminar la instalación incompleta.

## Primera ejecución

1. Usa una tarjeta Free McBoot preparada para PSX DESR.
2. Copia `DESR_XMB_Installer.ELF` y la carpeta `DESR_XMB_Installer` a la raíz de un USB compatible.
3. Arranca **wLaunchELF R3Z** desde la tarjeta y ejecuta `mass:/DESR_XMB_Installer.ELF`.
4. Elige idioma. Usa cruceta para mover, `X` para confirmar y `Triángulo` para volver.

También conviene disponer de **uLaunchELF 2TB Edition** para revisar o recuperar particiones. No uses R3Z para operaciones delicadas con particiones ocultas `__.`.

## Instalar una aplicación ELF

1. Copia el ELF en `DESR_XMB_Installer/APPS`.
2. Elige **Instalar aplicación ELF**.
3. Selecciona el ELF y uno de los ocho iconos de aplicación.
4. Al terminar, `Círculo` vuelve al menú y `Triángulo` cierra la aplicación.
5. Reinicia la DESR para ver la entrada en el XMB.

`APPS/DESR_XMB_Installer.elf` contiene esta misma versión y permite instalar DESR XMB Installer en el XMB. El USB seguirá siendo necesario para entregar nuevos ELF o ISO a la consola.

## Instalar una ISO al HDD

1. Crea `DESR_XMB_Installer/ISO` en USB o MX4SIO.
2. Copia una ISO procedente de un juego que poseas.
3. Elige **Instalar ISO al HDD**, el dispositivo, la ISO y un icono GAME.
4. La aplicación crea la instalación HDL, copia la ISO, prepara `+OPL`, oculta el juego y crea el acceso del XMB.
5. El acceso abre OPL y ejecuta el juego correspondiente.

Durante la copia puedes pulsar **SELECT** para cancelarla con seguridad. Mantén alimentación estable y no retires USB/MX4SIO durante una copia. La velocidad y la compatibilidad dependen del medio, OPL y cada juego.

## Instalar en XMB como ejecutables juegos de HDL en disco

1. Instala el juego con HDL Game Installer.
2. Elige **Instalar en XMB como ejecutables juegos de HDL en disco**.
3. Elige el juego visible y un icono GAME.
4. El instalador oculta la partición HDL y crea el acceso XMB que abre OPL directamente para ese juego.

## Borrar contenido instalado

- **Borrar aplicaciones instaladas** lista las aplicaciones XMB y elimina la seleccionada.
- **Borrar juegos instalados** lista juegos enlazados por su título del XMB, no solo por el código de producto.

### Limitación conocida: borrado de juegos HDL

En las DESR probadas, el borrado de un juego puede eliminar la entrada normal y el juego pero dejar una partición temporal `PP.DEL-…` visible en el XMB como **Datos dañados**. Si ocurre, termina el borrado seleccionando ese icono de datos dañados en el XMB y confirmando la eliminación. También puedes revisarlo con uLaunchELF 2TB Edition. La función de borrar aplicaciones XMB no está afectada.

## Estructura del USB

```text
DESR_XMB_Installer.ELF
DESR_XMB_Installer/
  APPS/                 ← ELF propios y los incluidos
  ISO/                  ← ISO propias que quieras instalar
  EXECUTE.KELF          ← generado durante la instalación
  OPL-LAUNCHER.ELF
  OPL-RUNTIME.ELF
```

## Pruebas de hardware

Esta versión se ha probado en hardware real con los mismos resultados funcionales en:

| Modelo | Firmware |
| --- | --- |
| PSX DESR 7500 | 2.11 |
| PSX DESR 5100S | 1.31 |

En ambos equipos se han comprobado la instalación de aplicaciones, los iconos, los lanzadores XMB para juegos HDL/OPL, la instalación de ISO desde almacenamiento externo y el comportamiento descrito del borrado de juegos. Son pruebas prácticas, no una garantía de compatibilidad total con todos los firmwares, discos, USB, MX4SIO o títulos.

## Notas

- Las claves necesarias están integradas en el ejecutable de esta distribución; no copies ni publiques claves por separado.
- La herramienta no incluye juegos, ISO ni BIOS.
- Utiliza únicamente copias de juegos que poseas.
- Haz copia de seguridad de tu disco interno antes de experimentar con particiones.

## Agradecimientos

Gracias a **ps2dev / PS2SDK**, **Open PS2 Loader**, **HDLGameInstaller**, **wLaunchELF R3Z**, **uLaunchELF 2TB Edition**, **PicoDrive**, **FCEUMM**, **psx-osdsys**, PSX-Place y a todas las personas que preservan, prueban y documentan hardware PS2 y DESR. Besos, abrazos y larga vida al homebrew.
