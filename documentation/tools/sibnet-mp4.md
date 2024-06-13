---
description: Renvoie le lien source de la vidéo pour pouvoir la télécharger en mp4
---

# 🍥 Sibnet mp4



### Paramètres :

| Nom | Description              | Valeur par défaut |
| --- | ------------------------ | ----------------- |
| url | L'url de la vidéo sibnet | None              |

### Exemple d'utilisation dans du code python qui utilise requests :

```python
import requests

# URL de l'API avec les paramètres
url = "https://api-delta-omega.vercel.app/sibnet"
params = {
    "url": "https://video.sibnet.ru/shell.php?videoid=3566463"
}

# Envoie de la requête GET à l'API
response = requests.get(url, params=params)

# Vérifie si la requête a réussi (code d'état 200)
if response.status_code == 200:
    # Affiche la réponse JSON dans la catégorie 'url'
    response_json = response.json()
    print(response_json['locationUrl'])
else:
    # Affiche un message d'erreur si la requête a échoué
    print("La requête a échoué avec le code d'état :", response.status_code)
```

### Sortie :

{% code overflow="wrap" %}
```
https://cvs13-2.sibnet.ru/33/12/83/3312838.mp4?st=9LtfpGNckjkqHJaUtaT5FA&e=1718330000&stor=6&noip=1
```
{% endcode %}

{% hint style="danger" %}
Les liens renvoyés par l'api sont temporaires
{% endhint %}

### Utilisation directement dans le lien :

{% code overflow="wrap" %}
```
https://api-delta-omega.vercel.app/sibnet?url=https://video.sibnet.ru/shell.php?videoid=3566463
```
{% endcode %}

### Json renvoyé par le lien :

{% code overflow="wrap" %}
```json
{
    "locationUrl": "https://cvs13-2.sibnet.ru/33/12/83/3312838.mp4?st=9LtfpGNckjkqHJaUtaT5FA&e=1718330000&stor=6&noip=1",
    "thumbnailUrl": "https://st.sibnet.ru/upload/cover/video_3566463_0.jpg"
}
```
{% endcode %}
