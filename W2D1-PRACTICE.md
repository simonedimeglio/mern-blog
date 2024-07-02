# Pratica W2D1

Elenco delle query richieste per l'esercizio: 

1. Trova tutte le risorse con il dato isActive corrispondente a true
2. Trova tutte le risorse con il dato age maggiore di 26
3. Trova tutte le risorse con il dato age maggiore di 26 e minore a 30
4. Trova tutte le risorse con il dato eyes che sia brown o blue
5. Trova tutte le risorse che non presentano il dato eyes uguale a green 
6. Trova tutte le risorse che non presentano il dato eyes uguale a green e neanche ablue 
7. Trova tutte le risorse con il dato company uguale a "FITCORE" e ritorna solo l'email

## Soluzioni: 

1. Trova tutte le risorse con il dato isActive corrispondente a true:

```javascript
Query: { isActive: true }
```
> Questa query cerca tutti i documenti dove il campo "isActive" è impostato su true.

2. Trova tutte le risorse con il dato age maggiore di 26:

```javascript
Query: { age: { $gt: 26 } } 
```
> $gt significa "greater than" (maggiore di). Questa query trova tutti i documenti dove l'età è superiore a 26.

3. Trova tutte le risorse con il dato age maggiore di 26 e minore a 30:
```javascript
Query: { age: { $gt: 26, $lt: 30 } }
```
> $lt significa "less than" (minore di). Questa query combina due condizioni per trovare le età tra 26 e 30 (esclusi).


4. Trova tutte le risorse con il dato eyes che sia brown o blue:
```javascript
Query: { eyeColor: { $in: ["brown", "blue"] } }
```
> $in cerca valori che corrispondono a quelli nell'array specificato. Questa query trova documenti dove eyeColor è "brown" o "blue".


5. Trova tutte le risorse che non presentano il dato eyes uguale a green:
```javascript
Query: { eyeColor: { $ne: "green" } }
```
> $ne significa "not equal" (non uguale). Questa query trova documenti dove eyeColor non è "green".


6. Trova tutte le risorse che non presentano il dato eyes uguale a green e neanche a blue:
```javascript
Query: { eyeColor: { $nin: ["green", "blue"] } }
```
> $nin significa "not in" (non in). Questa query trova documenti dove eyeColor non è né "green" né "blue".


7. Trova tutte le risorse con il dato company uguale a "FITCORE" e ritorna solo l'email:
```javascript
Query: { company: "FITCORE" } Project: { email: 1, _id: 0 }
```
> La prima parte trova i documenti con company "FITCORE". La seconda parte (projection) specifica di mostrare solo il campo email (1) e di escludere l'_id (0).

## TIPS/ISTRUZIONI MONGODB COMPASS 
- Connettiti al tuo database.
- Seleziona la collezione corretta.
- Vai alla scheda "Query".
- Inserisci la query nel campo "Filter".
- Per l'ultima query, usa anche il campo "Project" per specificare i campi da visualizzare.
- Clicca su "Find" per eseguire la query.
