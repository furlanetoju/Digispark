# Digispark


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
 DigiKeyboardPtBr.println("Olá Mundo");
```

**Para usarmos um delay em cada comando, usamos:**
```
DigiKeyboardPtBr.delay(1000);
```
**Ex:**
```
void loop() { 
DigiKeyboardPtBr.println("Olá Mundo");  
DigiKeyboardPtBr.delay(1000); 
DigiKeyboardPtBr.println("HelloWord"); 
DigiKeyboardPtBr.delay(1000);
```
**Para digitar teclas, como enter por exemplo:**
```
DigiKeyboardPtBr.sendKeyStroke(KEY_ENTER);
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
