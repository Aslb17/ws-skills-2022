# GraphQL

> ❌ A travailler

> ✔️ Auto validation par l'étudiant

## 🎓 J'ai compris et je peux expliquer

- la différence entre REST et GraphQL  ✔️

REST (Representational State Transfer) est un style d'architecture basé sur les données qui sont manipulées via des requêtes HTTP standard. Les ressources sont représentées par des URL, et les opérations sur ces données sont effectuées à l'aide de méthodes HTTP telles que GET, POST, PUT, DELETE, etc. REST est simple et facile à comprendre, mais peut entraîner une surcharge de données, car les clients doivent souvent récupérer des données redondantes et inutiles.

GraphQL, d'autre part, est une architecture qui permet aux clients de demander exactement les données dont ils ont besoin et rien de plus. Les clients peuvent définir la structure de la réponse en fonction de leurs besoins. Cela signifie que GraphQL permet une récupération plus efficace et plus rapide des données. Cependant, GraphQL est plus complexe à comprendre et à mettre en œuvre que REST.

- les besoins auxquels répond GraphQL ✔️

Récupération de données spécifiques : GraphQL permet aux clients de demander exactement les données dont ils ont besoin et rien de plus, ce qui réduit la surcharge de données et permet une récupération plus efficace et plus rapide des données.

Évolutivité : GraphQL permet aux clients d'ajouter ou de supprimer des champs dans leur requête sans que cela n'affecte l'API ou la base de données sous-jacente.

Flexibilité : GraphQL permet aux clients de définir la structure de la réponse en fonction de leurs besoins. Les clients peuvent récupérer des données de différentes ressources dans une seule requête.

Performance : GraphQL permet de réduire le nombre de requêtes nécessaires pour récupérer les données, ce qui peut améliorer les performances de l'application : les clients peuvent récupérer toutes les données dont ils ont besoin en une seule requête.

Documentation : GraphQL fournit une documentation automatique pour l'API, ce qui facilite la compréhension et l'utilisation de l'API par les développeurs. La documentation est générée automatiquement à partir du schéma de l'API.


- la définition d'un schéma ✔️

Un schéma liste toutes les données que les clients peuvent demander par l'intermédiaire de ce service. Il est constitué de types d'objets, qui définissent le genre d'objet qu'il est possible de demander et les champs qu'il contient.
Lorsque les requêtes arrivent, GraphQL les compare au schéma, puis exécute celles qui ont été validées.


- Query ✔️

Une query en GraphQL est une opération permettant aux clients de récupérer des données. Les clients peuvent spécifier les champs qu'ils souhaitent récupérer, ainsi que la structure de la réponse.

query {
  field1
  field2
  ...
}

Dans cet exemple, field1, field2, etc. représentent les champs spécifiques que le client souhaite récupérer. Les champs peuvent être imbriqués pour récupérer des données à partir de plusieurs ressources.

- Mutation ✔️

Une mutation est une opération permettant de modifier ou de créer des données sur le serveur. Par exemple, cela peut être la création d'un nouvel utilisateur, la modification d'un article ou la suppression d'un commentaire. 

Les mutations sont définies à l'aide d'une syntaxe spécifique, qui comprend des actions à effectuer (par exemple, la création d'un utilisateur) et les champs qui doivent être renvoyés en réponse à l'action. Le résultat renvoyé par une mutation est un objet JSON qui correspond exactement à la forme de la requête effectuée par le client.


- Subscription ❌ / ✔️

## 💻 J'utilise

### Un exemple personnel commenté ✔️

@Resolver(User)
export class UserResolver {
  @Query(() => [User])
  async users(): Promise<User[]> {
    const users = await DataSource.getRepository(User).find({
      relations: { friends: true, eventOfUser: true },
    });
    return users;
  }


  @Mutation(() => User)
  async createUser(@Arg("data") data: UserInput): Promise<User> {
    const exisitingUser = await DataSource.getRepository(User).findOne({
      where: { nickName: data.nickName },
    });

    if (exisitingUser !== null) throw new ApolloError("USER_ALREADY_EXISTS");

    const hashedPassword: string = await hashPassword(data.password);
    const user = { ...data, hashedPassword, friends: [], eventOfUser: [] };

    return await DataSource.getRepository(User).save(user);
  }

}

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
