# 🐍 Exemple d'utilisation



## Comprendre l'url :

#### L'url suivante :

```
https://api-delta-omega.vercel.app/exemple
```

#### Renvoi ceci :

```json
{
    "exemple": "Ceci est un exemple !"
}
```

### Nous pouvons ajouter des paramètres à l'url afin de détailler notre requête :

#### Dans l'url suivante :

```
https://api-delta-omega.vercel.app/exemple?paramètre=exemple
```

Le point d'interrogation (?) permet d'assigner une valeur à un paramètre. Pour assigner cete valeur je dois suivre ce format :

```
?<NOM DU PARAMÈTRE>
```

#### Avec notre url qui a comme paramètre \[ paramètre: "exemple" ], l'api va renvoyer :

```json
{
    "exemple": "Ceci est un exemple !",
    "paramètre": "exemple"
}
```

{% hint style="danger" %}
Le point d'interrogation doit être utilisé uniquement pour le premier paramètre !

Si l'url a plusieurs paramètres, les paramètres qui suivent le premier doivent avoir le signe & à la place du point d'interrogation (?).

Exemple :

```url
https://api-delta-omega.vercel.app/exemple?paramètre1=ex&paramètre2=ex2
```
{% endhint %}

### Il existe un deuxième type de paramètre :

#### Dans l'url suivante :

```
https://api-delta-omega.vercel.app/exemple/valeur-du-paramètre
```

Ce qui suit le slash sera la valeur d'un paramètre.

#### Avec notre url qui a comme paramètre \[ paramètre: "valeur-du-paramètre" ], l'api va renvoyer :

```json
{
    "exemple": "Ceci est un exemple !",
    "paramètre": "valeur-du-paramètre"
}
```

## Utilisation en python :

```python
import requests

url = "https://api-delta-omega.vercel.app/exemple"
params = {
    "paramètre": "exemple"
}
résultat = requests.get(url, params=params)
print(résultat.json)
```

#### Sortie :

```json5
{'exemple': 'Ceci est un exemple !', 'paramètre': 'exemple'}
```

## Utilisation en javascript (Node js) :

```javascript
const axios = require('axios');

axios.get('https://api-delta-omega.vercel.app/exemple', {
  params: {
    paramètre: 'exemple'
  }
})
.then(response => {
  console.log(response.data);
})
.catch(error => {
  console.error(error);
});
```

#### Sortie :

```json5
{ exemple: 'Ceci est un exemple !', 'paramètre': 'exemple' }
```

## Utilisation dans le terminal :

```bash
curl -G -d "paramètre=exemple" "https://api-delta-omega.vercel.app/exemple"
```

#### Sortie :

```json
{"exemple":"Ceci est un exemple !","paramètre":"exemple"}
```
