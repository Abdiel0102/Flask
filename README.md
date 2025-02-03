# Flask
from flask import Flask
import random

app = Flask(__name__)
facts_list = ["Elon Musk afirma que las redes sociales están diseñadas para mantenernos dentro de la plataforma, de modo que pasemos el mayor tiempo posible viendo contenidos.", 
            "Según un estudio realizado en 2018, más del 50% de las personas de entre 18 y 34 años se consideran dependientes de sus smartphones.", 
            "Las redes sociales tienen aspectos positivos y negativos, y debemos ser conscientes de ambos cuando utilicemos estas plataformas.", 
            "El estudio de la adicción tecnológica es una de las áreas más relevantes de la investigación científica moderna."]
caracters = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z", ]


@app route("/")
def pag_principal():
    return f'<h1>Hola, en esta página puedes aprender un par de cosas interesantes sobre las dependencias tecnológicas.</h1><a href="/random_fact">¡Ver un hecho al azar!</a>'

@app.route("/random_fact")
def random_fact():
    return f'<p>{random.choice(facts_list)}</p>'

@app.route("/password")
def password_generate( ):
    return f'<p>{random.choice(facts_list)}</p>'

app.run(debug=True)
