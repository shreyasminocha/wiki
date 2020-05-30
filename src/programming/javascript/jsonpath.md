# JSONPath

JSONPath is a syntax to query json structures.

## Examples

An incomplete set of examples of using JSON path follows.

Example Data:

```javascript
{
    "name": "Super hero squad",
    "homeTown": "Metro City",
    "formed": 2016,
    "secretBase": "Super tower",
    "active": true,
    "members": [
        {
            "name": "Molecule Man",
            "age": 29,
            "secretIdentity": "Dan Jukes",
            "powers": [
                "Radiation resistance", "Turning tiny", "Radiation blast"
            ]
        },
        {
            "name": "Madame Uppercut",
            "age": 39,
            "secretIdentity": "Jane Wilson",
            "powers": [
                "Million tonne punch", "Damage resistance", "Superhuman reflexes"
            ]
        },
        {
            "name": "Eternal Flame",
            "age": 1000000,
            "secretIdentity": "Unknown",
            "powers": [
                "Immortality", "Heat Immunity", "Inferno", "Teleportation", "Interdimensional travel"
            ]
        }
    ]
}
```

### `$.members`

```javascript
[
    [
        {
            name: "Molecule Man",
            age: 29,
            secretIdentity: "Dan Jukes",
            powers: ["Radiation resistance", "Turning tiny", "Radiation blast"],
        },
        {
            name: "Madame Uppercut",
            age: 39,
            secretIdentity: "Jane Wilson",
            powers: [
                "Million tonne punch",
                "Damage resistance",
                "Superhuman reflexes",
            ],
        },
        {
            name: "Eternal Flame",
            age: 1000000,
            secretIdentity: "Unknown",
            powers: [
                "Immortality",
                "Heat Immunity",
                "Inferno",
                "Teleportation",
                "Interdimensional travel",
            ],
        },
    ],
];
```

### `$.members.*`

```javascript
[
    {
        name: "Molecule Man",
        age: 29,
        secretIdentity: "Dan Jukes",
        powers: ["Radiation resistance", "Turning tiny", "Radiation blast"],
    },
    {
        name: "Madame Uppercut",
        age: 39,
        secretIdentity: "Jane Wilson",
        powers: [
            "Million tonne punch",
            "Damage resistance",
            "Superhuman reflexes",
        ],
    },
    {
        name: "Eternal Flame",
        age: 1000000,
        secretIdentity: "Unknown",
        powers: [
            "Immortality",
            "Heat Immunity",
            "Inferno",
            "Teleportation",
            "Interdimensional travel",
        ],
    },
];
```

### `$..name`

Values of all keys `name`. `..` is called the recursive descendant operator.

```javascript
["Super Hero Squad", "Molecule Man", "Madame Uppercut", "Eternal Flame"];
```

### `$.members[*].name`

Values of the name key of all `members`

```javascript
["Molecule Man", "Madame Uppercut", "Eternal Flame"];
```

### `$.members[2].*`

Element at index `2` of the array `members`.

```javascript
{
    "name": "Eternal Flame",
    "age": 1000000,
    "secretIdentity": "Unknown",
    "powers": [
        "Immortality", "Heat Immunity", "Inferno", "Teleportation",
        "Interdimensional travel"
    ]
}
```

Also valid:

-   `$.members[:2]`: First two elements of `members`
-   `$.members[0,2]`: Elements at indices `0` and `2`

### `$..*`

\[all values of the JSON structure\]

## Formal syntax

From [https://www.npmjs.com/package/jsonpath\#jsonpath-syntax](https://www.npmjs.com/package/jsonpath#jsonpath-syntax).

| JSONPath           | Description                                                          |
| :----------------- | :------------------------------------------------------------------- |
| `$`                | The root object/element                                              |
| `@`                | The current object/element                                           |
| `.`                | Child member operator                                                |
| `..`               | Recursive descendant operator; JSONPath borrows this syntax from E4X |
| `*`                | Wildcard matching all objects/elements regardless their names        |
| `[]`               | Subscript operator                                                   |
| `[,]`              | Union operator for alternate names or array indices as a set         |
| `[start:end:step]` | Array slice operator borrowed from ES4 / Python                      |
| `?()`              | Applies a filter \(script\) expression via static evaluation         |
| `()`               | Script expression via static evaluation                              |
