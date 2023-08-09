# Digispark

**Download da IDE**
```
https://www.arduino.cc/en/software
```

**Download IDE direto pelo MEGA**
```
https://mega.nz/file/I4t0AZ6S#4Wqt9__Ego76koQGS8CWSz56VJhM6eQUZ4DrOrJaSQE
```

**Primeiro passo é importamos o Digispark para dentro da IDE**

```
https://raw.githubusercontent.com/digistump/arduino-boards-index/master/package_digistump_index.json
```

**Link para baixar os drivers**

```
https://github.com/digistump/DigistumpArduino/releases/download/1.6.7/Digistump.Drivers.zip
```


**Para escrevermos na ide usamos:**

```
 DigiKeyboard.println("Olá Mundo");
```

**Para usarmos um delay em cada comando, usamos:**
```
DigiKeyboard.delay(1000);
```
**Ex:**
```
void loop() { 
DigiKeyboard.println("Ola Mundo");  
DigiKeyboard.delay(1000); 
DigiKeyboard.println("HelloWord"); 
DigiKeyboard.delay(1000);
```
**Para digitar teclas, como enter por exemplo:**
```
DigiKeyboard.sendKeyStroke(KEY_ENTER);
```
**Quando for enviar teclas especiais como enter, ctrl, alt, temos uma tabela para as respectivas teclas:**

<img src='https://i.imgur.com/U01ltn6.png' width="450">

**Por esse motivo usei a palavra "KEY_ENTER".**

**Exemplo para abrir o notepad**
```
  DigiKeyboard.sendKeyStroke(KEY_R, MOD_GUI_LEFT); 
  DigiKeyboard.delay(500); 
  DigiKeyboard.println("notepad");
  DigiKeyboard.delay(500); 
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
```
--------------------------------
<h1>Exemplo de códigos</h1>

Como trocar o papel de parede do windows
```
#include "DigiKeyboardPtBr.h"
#include "DigiKeyboard.h"
void setup() {
  //empty
}
void loop() {
  DigiKeyboard.sendKeyStroke(0);
  DigiKeyboard.sendKeyStroke(KEY_D, MOD_GUI_LEFT);
  DigiKeyboard.delay(1000);
  DigiKeyboard.sendKeyStroke(KEY_R, MOD_GUI_LEFT);
  DigiKeyboard.delay(1000);
  DigiKeyboard.print("powershell");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(1000);
  DigiKeyboardPtBr.print("$client = new-object System.Net.WebClient");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(1000);
  DigiKeyboardPtBr.print("$client.DownloadFile(\"https://w0.peakpx.com/wallpaper/29/611/HD-wallpaper-star-wars-warrior-lightsaber-sith-star-wars.jpg\" , \"doge.jpg\")");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(1000);
  DigiKeyboardPtBr.print("reg add \"HKCU\\Control Panel\\Desktop\" /v WallPaper /d \"%USERPROFILE%\\doge.jpg\" /f");
  DigiKeyboard.delay(1000);
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(1000);
  DigiKeyboardPtBr.print("RUNDLL32.EXE USER32.DLL,UpdatePerUserSystemParameters ,1 ,True");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  DigiKeyboard.delay(1000);
  DigiKeyboard.print("exit");
  DigiKeyboard.sendKeyStroke(KEY_ENTER);
  for(;;){ /*empty*/ }
}
```
**Precisamos passar o link da imagem na linha $client.DownloadFile, Depois só dar reboot e o wallpaper vai estar alterado**
