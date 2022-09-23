# TypeScript

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- l'intéret de TypeScript dans l'IDE ✔️
Repérage rapide des erreurs, auto-complétion
- les types de bases ✔️
number/string/array/tuple/unknown/any
- comment et pourquoi étendre une interface ✔️
interface C extends A, B {
   // codes..
} 
Sert à étendre les propriétés du parent à l'enfant
- les classes et les decorators ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

###création d'une interface pour typer la fonction Wilder

interface WilderProps {
  wilder: IWilder
  setWilders: Dispatch<SetStateAction<IWilder[]>>
}

const Wilder = ({ wilder: { id, name, skills = [] }, setWilders }: WilderProps) => {
  const handleDelete = async () => {
    try {
      setWilders((oldList) => oldList.filter((wilder) => wilder.id !== id));
      await deleteWilder(id);
    } catch (err) {
      console.error(err);
    };
  };


### Utilisation dans un projet ❌ / ✔️

[lien github](...)

Description :

### Utilisation en production si applicable❌ / ✔️

[lien du projet](...)

Description :

### Utilisation en environement professionnel ❌ / ✔️

Description :

## 🌐 J'utilise des ressources

### Titre

- lien
- description

## 🚧 Je franchis les obstacles

### Point de blocage ❌ / ✔️

Description:

Plan d'action : (à valider par le formateur)

- action 1 ❌ / ✔️
- action 2 ❌ / ✔️
- ...

Résolution :

## 📽️ J'en fais la démonstration

- J'ai ecrit un [tutoriel](...) ❌ / ✔️
- J'ai fait une [présentation](...) ❌ / ✔️
