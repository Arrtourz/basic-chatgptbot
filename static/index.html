import os
import openai
from fastapi import FastAPI, Request, HTTPException
from fastapi.responses import HTMLResponse
from fastapi.staticfiles import StaticFiles
from pydantic import BaseModel
from dotenv import load_dotenv

load_dotenv()
OPENAI_API_KEY = os.getenv("OPENAI_API_KEY")
openai.api_key = OPENAI_API_KEY

app = FastAPI()

app.mount("/static", StaticFiles(directory="static"), name="static")

class ChatInput(BaseModel):
    message: str

@app.get("/", response_class=HTMLResponse)
async def serve_index(request: Request):
    with open("static/index.html", "r") as f:
        content = f.read()
    return HTMLResponse(content)

@app.post("/chat")
async def chat_with_gpt(chat_input: ChatInput):
    data = {
        "model": "gpt-3.5-turbo",
        "messages": [{"role": "system", "content": "我是ibianbot，一个由ibian训练的大型语言模型."},
                     {"role": "user", "content": chat_input.message}],
        "max_tokens": 1000,
        "temperature": 0.8
    }

    try:
        response = openai.ChatCompletion.create(**data)
        generated_text = response.choices[0].message['content'].strip()
        return {"response": generated_text}
    except Exception as e:
        raise HTTPException(status_code=500, detail=str(e))

if __name__ == "__main__":
    import uvicorn
    uvicorn.run(app, host="127.0.0.1", port=8000)
