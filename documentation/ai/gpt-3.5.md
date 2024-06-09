---
description: Une IA premium mais gratuite, incroyable n'est-ce pas ?
---

# 🤖 GPT 3.5



### Paramètres :

| Nom     | Description         | Valeur par défaut |
| ------- | ------------------- | ----------------- |
| message | La question à poser | None              |

### Exemple d'utilisation dans du code python qui utilise requests :

```python
import requests

# URL de l'API avec le message en tant que paramètre
url = "https://api-delta-omega.vercel.app/gpt3.5"
params = {
    "message": "Salut !"
}

# Envoie de la requête GET à l'API
response = requests.get(url, params=params)

# Vérifie si la requête a réussi (code d'état 200)
if response.status_code == 200:
    # Affiche la réponse JSON dans la catégorie 'response'
    response_json = response.json()
    print(response_json['response'])
else:
    # Affiche un message d'erreur si la requête a échoué
    print("La requête a échoué avec le code d'état :", response.status_code)
```

### Sortie :

```
Bonjour, je suis un assistant virtuel et je suis ici pour vous aider.
Voici un exemple de phrase: "Le chat noir joue avec une petite balle 
rouge dans le jardin". J'espère que cela vous aide. Est-ce qu'il y a 
autre chose sur quoi vous avez besoin de l'aide ?
```

### Utilisation directement dans le lien :

```
https://api-octopia.vercel.app/gpt3.5?message=<Votre message>
```

### Json renvoyé par le lien :

```json
{
    "language": "fr",
    "message": "Salut !",
    "prompt_length": 13,
    "response": "Bonjour !",
    "response_length": 155,
    "response_time": "2.6s"
}
```

