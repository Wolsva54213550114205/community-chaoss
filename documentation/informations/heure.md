---
description: Renvoie l'heure exacte de n'importe quel pays
---

# 🕐 Heure



### Paramètres ([deuxième type de paramètre](../../utilisation/exemple-dutilisation.md#il-existe-un-deuxieme-type-de-parametre))&#x20;

| Nom     | Description               | Valeur par défaut |
| ------- | ------------------------- | ----------------- |
| country | Le nom du pays en anglais | None              |

### Exemple d'utilisation dans du code python qui utilise requests :

```python
import requests

# URL de l'API avec les paramètres
url = "https://api-delta-omega.vercel.app/time"
country = "france"

# Envoie de la requête GET à l'API
response = requests.get(url + f"/{country}")

# Vérifie si la requête a réussi (code d'état 200)
if response.status_code == 200:
    # Affiche la réponse JSON dans la catégorie 'date_fr' + 'time'
    response_json = response.json()
    if 'date' in response_json and 'time' in response_json:
        date_info = response_json['date']
        time_info = response_json['time']

        # Accédez aux sous-clés pour obtenir les informations de date et d'heure
        date_fr = date_info['date_fr']
        time = time_info['time']

        print("Jour et heure : " + date_fr + " " + time)
    else:
        print("Les clés 'date' et/ou 'time' ne sont pas présentes dans la réponse JSON.")
else:
    print("La requête a échoué avec le code d'état :", response.status_code)
```

### Sortie :&#x20;

```
Jour et heure : 09 juin 2024 19:57:29
```

### Utilisation directement dans le lien :

```
https://api-delta-omega.vercel.app/time/<NOM DU PAYS EN ANGLAIS>
```

### Json renvoyé par le lien :

```json
{
    "country": "france",
    "date": {
        "date_fr": "09 juin 2024",
        "date_en": "June 09 2024",
        "day_number": "09",
        "day_name_fr": "dimanche",
        "day_name_en": "Sunday",
        "month_number": "06",
        "month_name_fr": "juin",
        "month_name_en": "June",
        "year": "2024"
    },
    "time": {
        "hour": "19",
        "minute": "57",
        "second": "16",
        "time": "19:57:16"
    }
}
```
