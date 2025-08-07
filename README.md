
# 📚 Revisão: Módulo de Automações com Python

## 1. 🖱️ PyAutoGUI – Automação com Teclado e Mouse

### ✅ Funções básicas:
- `pyautogui.write("texto")`: Digita como se fosse no teclado.
- `pyautogui.press("enter")`: Pressiona uma tecla.
- `pyautogui.click(x, y)`: Clica em uma coordenada da tela.
- `pyautogui.hotkey("ctrl", "c")`: Combinação de teclas.

### 💡 Exemplo de exercício simples:
```python
import pyautogui
import time

time.sleep(2)
pyautogui.press("Win")
pyautogui.write("Olá, mundo!")
```

---

## 2. 🌐 Requests, BeautifulSoup, HTML/CSS

### ✅ Conceitos:
- `requests.get(URL)`: Faz uma requisição HTTP.
- `BeautifulSoup(html, "html.parser")`: Interpreta o HTML.
- HTML = estrutura do site.
- CSS = estilo visual.

### 💡 Exemplo de exercício simples:
```python
import requests
from bs4 import BeautifulSoup

resposta = requests.get("https://books.toscrape.com")
site = BeautifulSoup(resposta.text, "html.parser")
titulo = site.find("h1").text

print("Título do site:", titulo)
```

---

## 3. 📄 CSV e JSON

### ✅ Comandos CSV:
- `csv.reader()`, `csv.writer()`
- `delimiter=','`, `lineterminator='\n'`

### ✅ Comandos JSON:
- `json.dumps()`, `json.loads()`

### 💡 Exemplo de exercício simples:
```python
import csv

with open("alunos.csv", "w", newline="") as arquivo:
    escritor = csv.writer(arquivo, delimiter=",", lineterminator="\n")
    escritor.writerow(["Nome", "Nota"])
    escritor.writerow(["Lucas", 8.5])
    escritor.writerow(["Ana", 9.0])
```

```python
import json

dados = {"nome": "João", "idade": 16}
texto_json = json.dumps(dados)
print(texto_json)
```

---

## 4. 💻 OS e Selenium

### ✅ Funções OS:
- `os.listdir()`
- `os.rename()`
- `os.remove()`

### 💡 Exemplo OS:
```python
import os

os.mkdir("Projetos")
os.rename("Projetos", "MeusProjetos")
print("Pastas:", os.listdir())
```

### ✅ Selenium (automação web):
- `webdriver.Chrome()`
- `find_element()`, `send_keys()`, `click()`

### 💡 Exemplo Selenium:
```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys

navegador = webdriver.Chrome()
navegador.get("https://www.google.com")
caixa = navegador.find_element(By.NAME, "q")
caixa.send_keys("Python", Keys.ENTER)
```

---

# 🧠 Desafio Final: Automatizar tudo junto!

## ✨ Descrição:
Faça um programa que:
1. Crie uma pasta "Relatorios" usando `os`.
2. Busque o título de https://books.toscrape.com usando `requests` e `bs4`.
3. Salve o título em um arquivo CSV.
4. Leia esse CSV e envie o texto para um campo de formulário usando `selenium`.
5. Digite no campo com `pyautogui` um "Relatório enviado!" após isso.

---

### ✅ Resolução:
```python
import os
import csv
import requests
from bs4 import BeautifulSoup
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import pyautogui
import time

# 1. Criar pasta
...

# 2. Coletar título do site
...

# 3. Salvar em CSV
...

# 4. Ler do CSV e enviar para formulário
...

# 5. Aviso com pyautogui
...
```

---

✅ **Parabéns!** Agora você já sabe usar cada biblioteca para automatizar tarefas reais!

---
