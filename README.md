# Fast-API-s

from fastapi import FastAPI

app=FastAPI()

food_items={
    'indian':["Ricebath","Idly","Biriyani"],
    'mexicon':["Pizza"],
    'southindian':["Kebab","legpice"]
}

@app.get("/get_items/{lohith}")
async def get_item(lohith ):
    return food_items.get(lohith)


=================================================================================================================================================================================


from fastapi import FastAPI
from enum import Enum



app=FastAPI()

class AvailableLohith(str, Enum):
    indian="indian"
    mexicone="mexicone"
    southindian="southindian"


food_items={
    'indian':["Ricebath","Idly","Biriyani"],
    'mexicon':["Pizza"],
    'southindian':["Kebab","legpice"]
}

valid_lohith=food_items.keys()
@app.get("/get_items/{lohith}")
async def get_item(lohith: AvailableLohith):
    return food_items.get(lohith)
