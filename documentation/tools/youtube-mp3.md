---
description: Renvoie le lien google video de la vidéo pour pouvoir la télécharger en mp3
---

# 🎵 Youtube mp3



### Paramètres :&#x20;



| Nom     | Description                         | Valeur par défaut |
| ------- | ----------------------------------- | ----------------- |
| url     | L'url de la vidéo youtube           | None              |
| quality | La qualité de l'audio (lowest/best) | best              |

### Exemple d'utilisation dans du code python qui utilise requests :

```python
import requests

# URL de l'API avec les paramètres
url = "https://api-delta-omega.vercel.app/youtube/mp3"
params = {
    "url": "https://youtu.be/WO2b03Zdu4Q?si=RRBKEu-Gy-M5E4tN",
    "quality": "lowest"
}

# Envoie de la requête GET à l'API
response = requests.get(url, params=params)

# Vérifie si la requête a réussi (code d'état 200)
if response.status_code == 200:
    # Affiche la réponse JSON dans la catégorie 'url'
    response_json = response.json()
    print(response_json['googleAudioLink'])
else:
    # Affiche un message d'erreur si la requête a échoué
    print("La requête a échoué avec le code d'état :", response.status_code)
```

### Sortie :

{% code overflow="wrap" %}
```
https://rr4---sn-p5qs7nzy.googlevideo.com/videoplayback?expire=<LIEN COUPÉ>
```
{% endcode %}

### Utilisation directement dans le lien :

{% code overflow="wrap" %}
```
https://api-delta-omega.vercel.app/youtube/mp3?url=https://youtu.be/WO2b03Zdu4Q?si=RRBKEu-Gy-M5E4tN&quality=lowest
```
{% endcode %}

### Json renvoyé par le lien :

{% code overflow="wrap" %}
```json
{
    "googleAudioLink": "https://rr4---sn-p5qs7nzy.googlevideo.com/videoplayback?expire=<LIEN COUPÉ>"
}
```
{% endcode %}
