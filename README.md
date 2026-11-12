# Translations

The samples below show how I adapt tone, style, and terminology across genres while still preserving the original intent.

---

## 1. Fiction / Video Game
**Style:** Dynamic equivalence

### 🇷🇺 Original
По личному поручению руководителя аналитик ФБР Грейс Эшкрофт отправляется в отель «Ренвуд» – место, где восемь лет назад была убита ее мать. Однако там ей уже подготовили ловушку: практически сразу по прибытии Грейс берут в плен.

Агент DSO Леон Кеннеди, получив сообщение о пропаже полицейского, тоже прибывает в этот отель. В последний момент он успевает узнать о похищении Грейс – и довольно быстро понимает, что за всем этим стоит нечто большее, чем банальное исчезновение случайного человека.

Теперь, чтобы разобраться, что здесь вообще происходит, обоим героям придется окунуться в прошлое и раскрыть правду об инциденте почти тридцатилетней давности в Раккун-Сити – том самом, что когда-то изменил весь мир.

### 🇬🇧 Translation
FBI intelligence analyst Grace Ashcroft receives a personal assignment from her supervisor and heads to the Renwood Hotel – the same place where her mother was killed eight years ago. However, the hotel holds more than memories: the moment Grace sets foot inside, the doors seal shut behind her, the lights cut out, and she understands that she was just lured here.

DSO Agent Leon Kennedy receives a report of a missing police officer and likewise arrives at the hotel. At the very last moment he learns of Grace's abduction – and quickly realizes that something far bigger is behind this than the ordinary kidnapping of a random person.

Now, to figure out what is really going on, both of them must delve into the past and uncover the truth about an incident nearly thirty years ago in Raccoon City – the very incident that once changed the world.

---

## 2. Medical / Aesthetic
**Style:** Formal equivalence

### 🇷🇺 Original
Микроигольчатый RF-лифтинг – аппаратная методика ремоделирования кожи, основанная на сочетании контролируемых микроповреждений и радиочастотного воздействия. Процедура стимулирует синтез коллагеновых и эластиновых волокон, что обеспечивает повышение плотности и упругости кожи, выраженный лифтинг-эффект и улучшение ее общего вида.

### 🇬🇧 Translation
Fractional RF Microneedling is an energy-based procedure for skin rejuvenation that combines controlled micro-injuries with focused radiofrequency energy. This stimulates both collagen and elastin synthesis, leading to increased firmness, tightening, and a more even complexion.

---

## 3. Legal / Administrative
**Style:** Functional equivalence

### 🇷🇺 Original
Апостиль – сертификат, который подтверждает подлинность документа и позволяет использовать его за пределами страны, где он был изначально оформлен. Он нужен, чтобы документ, выданный в одном государстве, был признан в другом.

Чаще всего апостиль требуется при поступлении в иностранные учебные заведения, трудоустройстве за рубежом или подаче документов в государственные органы другой страны.

Например, если выпускник школы планирует поступать в зарубежный университет, из документов у него обязательно запросят школьный аттестат. Однако во многих странах в исходном виде его не примут: документ нужно предварительно легализовать – собственно, апостилировать.

### 🇬🇧 Translation
An apostille is an official certificate that authenticates the signature and seal on a public document, thus allowing it to be recognized outside the country where it was originally issued.

An apostille is typically required when a document has to be used for study, work, or other official purposes abroad. Take a high school graduate applying to a university abroad: they will almost always be required to provide a secondary school diploma. Yet in the vast majority of countries, such a document is not accepted as is – it must first be authenticated for international use. In most cases, this is done by obtaining an apostille.

<br>
<br>
<br>

# Originals

The samples above demonstrate my translation work, but I do also write original content in English. Below are a few examples across different niches.

---

## Sample 1 – Installing Python, Running FastAPI, and Serving on Port 8888

**Topic and style:** Technical writing | Web development / API setup

### Step 1. Installing Python

In this guide, we'll build a FastAPI server. To get started, you'll need to install Python. The process is as follows:

1. Download the installer from [python.org/downloads](https://www.python.org/downloads/).
2. Open the downloaded file.
3. Make sure the **Add Python to PATH** checkbox is selected. Otherwise, you won't be able to run the `python` command.
4. Click **Install Now** and wait for the installation to complete.

#### Verify the Installation

To confirm Python is installed correctly, enter the following in your terminal:

```powershell
python --version
```

If the output shows `Python 3.x`, move on to the next step.

---

### Step 2. Setting Up the Project

Create a project folder to store all files related to your server. Then, navigate into it so that all subsequent commands run within this directory. To do so, execute these two commands:

```powershell
mkdir my_server
cd my_server
```

- `mkdir my_server`: Creates a directory named `my_server`.
- `cd my_server`: Changes into that folder. From now on, the terminal treats it as your current working directory, and all subsequent commands apply to the files inside.

Now for the dependencies. First, install FastAPI:

```powershell
pip install fastapi
```

- `pip`: Python's built-in package manager for installing external libraries.
- `fastapi`: The framework responsible for routing, parsing, and response serialization.

Next, install the ASGI server that will power the application:

```powershell
pip install uvicorn
```

- `uvicorn`: A fast and lightweight server that loads your app and accepts all the incoming requests.

To confirm everything is in place, run:

```powershell
pip show fastapi
```

---

### Step 3. Creating the Server

Create `main.py` in `my_server`. The exact filename is important because we'll reference it when starting the server. **With that in place**, copy the following into it:

```python
from datetime import datetime

from fastapi import FastAPI

app = FastAPI()


@app.get("/")
def hello():
    return {"message": "Hello world!", "time": datetime.now().strftime("%Y-%m-%d %H:%M:%S")}
```

- `FastAPI()`: Creates the main application object. The `app` variable serves as the entry point – it receives requests and manages the server's behavior.
- `@app.get("/")`: Registers a route for the root path and tells FastAPI to call the decorated function when that path is accessed.
- `hello`: Handles the response logic: it returns a dictionary that FastAPI then sends back to the client.
- `datetime.now()`: Returns the current date and time as a `datetime` object. `strftime()` then formats that very object into a readable string with the `%Y-%m-%d %H:%M:%S` pattern.

---

### Step 4. Starting the Server

Make sure you're still inside the `my_server` directory from Step 2, then run:

```powershell
uvicorn main:app --host 0.0.0.0 --port 8888
```

- `main:app`: Tells Uvicorn where to find the application — that is, the module name (filename without extension) and the variable name, separated by a colon.
- `--host 0.0.0.0`: The address the server listens on. `0.0.0.0` literally means "all network interfaces." In other words, so the application can be reached not only from your local machine, but also from any other device on the same network.
- `--port 8888`: The port number that incoming requests will be sent to.

If everything was set up correctly, you'll see the following output in your console:

```
INFO:     Uvicorn running on http://0.0.0.0:8888
```

---

### Step 5. Testing the Endpoint

Open your browser and navigate to `http://127.0.0.1:8888`. You should see a JSON response like this:

```json
{"message":"Hello world!","time":"YYYY-MM-DD HH:MM:SS"}
```

### Stopping the server

To stop the server, press `Ctrl+C` in the terminal.
