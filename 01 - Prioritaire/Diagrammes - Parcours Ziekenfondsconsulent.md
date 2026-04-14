# Diagrammes - Parcours Ziekenfondsconsulent

> [!info] Note vidée
> Les diagrammes utiles sont maintenant intégrés directement dans les procédures. Cette note peut être ignorée pendant la révision.


> [!info] Compatibilité Obsidian
> Ces schémas utilisent **Mermaid**, lisible nativement dans Obsidian en mode lecture ou live preview.

## Diagramme - traitement complet d'une demande (version originale)
```mermaid
flowchart TD
    A([Début]) --> B[Accueillir le membre]
    B --> C[Clarifier la demande]
    C --> D{La demande est-elle claire ?}
    D -- Non --> E[Poser des questions complémentaires]
    E --> C
    D -- Oui --> F[Identifier le type de cas]
    F --> G{Quel cas ?}
    G -- Grossesse / naissance --> H[Analyser le cas grossesse / naissance]
    G -- Incapacité --> I[Analyser l'incapacité de travail]
    G -- Hospitalisation --> J[Analyser l'hospitalisation]
    G -- Administratif --> K[Analyser le dossier membre]
    G -- Voyage --> L[Analyser la situation à l'étranger]
    G -- Aide à domicile --> M[Analyser le besoin d'aide]
    G -- Dentaire --> N[Analyser le besoin dentaire]
    G -- Enfants / famille --> O[Analyser le besoin famille]
    G -- Remboursement / assurance --> P[Analyser les droits et produits]
    H --> Q[Expliquer droits, démarches, documents et services]
    I --> Q
    J --> Q
    K --> Q
    L --> Q
    M --> Q
    N --> Q
    O --> Q
    P --> Q
    Q --> R{Traitement direct possible ?}
    R -- Oui --> S[Traiter ou guider immédiatement]
    R -- Non --> T[Orienter vers le bon service]
    S --> U[Proposer les services complémentaires utiles]
    T --> U
    U --> V[Résumer les prochaines étapes]
    V --> W([Fin])
```

## Diagramme - traitement complet d'une demande (version refactorisée)
```mermaid
flowchart TD
    A([Début]) --> B[Accueillir]
    B --> C[Clarifier la demande]
    C --> D{Demande claire ?}
    D -- Non --> E[Poser 1 ou 2 questions]
    E --> C
    D -- Oui --> F[Classer le cas]
    F --> G{Catégorie}
    G -- Fréquent --> H[Bloc 1]
    G -- Services --> I[Bloc 2]
    G -- Admin --> J[Bloc 3]
    H --> K[Expliquer droits et démarches]
    I --> K
    J --> K
    K --> L{Traitement direct ?}
    L -- Oui --> M[Traiter / guider]
    L -- Non --> N[Orienter]
    M --> O[Proposer services utiles]
    N --> O
    O --> P[Résumer étapes]
    P --> Q([Fin])
```

## Pourquoi la version refactorisée s'affiche mieux
- moins de branches en même temps
- libellés plus courts
- regroupement en 3 blocs au lieu d'ouvrir tous les cas d'un coup
- lecture plus naturelle dans Obsidian

## Diagramme - cas grossesse / naissance détaillé
```mermaid
flowchart TD
    A([Début]) --> B[Identifier grossesse, naissance ou adoption]
    B --> C[Clarifier la demande principale]
    C --> D{Quel besoin ?}
    D -- Démarches --> E[Expliquer les étapes administratives]
    D -- Avantages --> F[Présenter cadeaux, remboursements et aides]
    D -- Documents --> G[Préciser les pièces utiles]
    D -- Accompagnement --> H[Présenter kraamzorg, doula, zwangerschapsconsulent]
    E --> I{Enfant déjà inscrit ?}
    F --> I
    G --> I
    H --> I
    I -- Non --> J[Expliquer inscription au dossier]
    I -- Oui --> K[Passer au suivi du cas]
    J --> K
    K --> L[Orienter vers eMut, contact ou rendez-vous]
    L --> M([Fin])
```

## Diagramme - incapacité de travail détaillé
```mermaid
flowchart TD
    A([Début]) --> B[Identifier maladie ou accident]
    B --> C[Demander date de début]
    C --> D{Certificat déjà transmis ?}
    D -- Non --> E[Expliquer comment transmettre le getuigschrift]
    D -- Oui --> F[Vérifier l'état du dossier]
    E --> G{Quel besoin ?}
    F --> G
    G -- Déclaration --> H[Expliquer la procédure]
    G -- Indemnité --> I[Expliquer le suivi de l'uitkering]
    G -- Reprise --> J[Orienter vers terug naar werk]
    H --> K[Résumer prochaines étapes]
    I --> K
    J --> K
    K --> L([Fin])
```

## Diagramme - hospitalisation détaillé
```mermaid
flowchart TD
    A([Début]) --> B[Déterminer si l'hospitalisation est prévue ou en cours]
    B --> C{Quel besoin ?}
    C -- Coût --> D[Expliquer les éléments de coût]
    C -- Assurance --> E[Présenter hospitalisatieverzekering]
    C -- Transport --> F[Expliquer les options de vervoer]
    C -- Suite des soins --> G[Orienter vers revalidatie ou coordination]
    D --> H[Préciser la prochaine étape]
    E --> H
    F --> H
    G --> H
    H --> I([Fin])
```

## Diagramme - changement administratif
```mermaid
flowchart TD
    A([Début]) --> B[Identifier le changement]
    B --> C{Quel type ?}
    C -- Adresse --> D[Mettre à jour ou expliquer la procédure]
    C -- Banque --> E[Mettre à jour ou demander la preuve utile]
    C -- Coordonnées --> F[Mettre à jour le dossier]
    C -- Mariage / cohabitation --> G[Expliquer impacts et dossier]
    C -- Divorce --> H[Expliquer impacts et adaptations]
    C -- Roze klevers --> I[Expliquer la demande]
    C -- Nouveau membre --> J[Expliquer l'affiliation]
    D --> K[Résumer les étapes]
    E --> K
    F --> K
    G --> K
    H --> K
    I --> K
    J --> K
    K --> L([Fin])
```

## Diagramme - voyage et étranger
```mermaid
flowchart TD
    A([Début]) --> B[Identifier destination et période]
    B --> C{Quel besoin ?}
    C -- Documents --> D[Expliquer reisdocumenten]
    C -- Assistance --> E[Présenter Mutas / reisbijstand]
    C -- Soins à l'étranger --> F[Expliquer la marche à suivre]
    C -- Vaccins --> G[Orienter vers reisvaccins]
    D --> H[Résumer les prochaines étapes]
    E --> H
    F --> H
    G --> H
    H --> I([Fin])
```

## Diagramme - orientation vers le bon service
```mermaid
flowchart TD
    A([Début]) --> B[Le cas peut-il être traité directement ?]
    B -- Oui --> C[Traiter la demande]
    B -- Non --> D{Vers quel service ?}
    D -- Social --> E[DMW]
    D -- Grossesse --> F[Zwangerschapsconsulent]
    D -- Retour au travail --> G[Terug-naar-werk-coördinator]
    D -- Aide à domicile --> H[Thuiszorg / Gezinszorg]
    D -- Matériel --> I[Zorgwinkel]
    D -- Rendez-vous --> J[Maak een afspraak]
    E --> K[Expliquer pourquoi et comment]
    F --> K
    G --> K
    H --> K
    I --> K
    J --> K
    C --> L([Fin])
    K --> L
```
