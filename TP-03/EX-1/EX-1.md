## EX-01

### I/ AWS CLI

#### 1. Identifier la commande AWS CLI à utiliser

```
users:~/environment $ aws iam list-users

[...]

[
  {
            "Path": "/users/ynov/",
            "UserName": "epeyrataud",
            "UserId": "AIDAR6SW7FM74MP5TLLY2",
            "Arn": "arn:aws:iam::134400125759:user/users/ynov/epeyrataud",
            "CreateDate": "2025-02-02T18:07:53+00:00",
            "PasswordLastUsed": "2025-02-06T08:58:08+00:00"
        },
        {
            "Path": "/automation/",
            "UserName": "gitlab-ci",
            "UserId": "AIDAR6SW7FM7VEQUJCUAJ",
            "Arn": "arn:aws:iam::134400125759:user/automation/gitlab-ci",
            "CreateDate": "2021-03-31T16:03:55+00:00"
        },
        {
            "Path": "/users/ynov/",
            "UserName": "groux",
            "UserId": "AIDAR6SW7FM7WCAEZ2BEH",
            "Arn": "arn:aws:iam::134400125759:user/users/ynov/groux",
            "CreateDate": "2025-02-02T18:07:52+00:00",
            "PasswordLastUsed": "2025-02-06T08:59:38+00:00"
    }
]
```

#### 2. Filtrer les résultats

```

users:~/environment $ aws --profile formation-infra-cloud iam list-users --path-prefix "/users/ynov/" --output json


[
    {
        "Path": "/users/ynov/",
        "UserName": "epeyrataud",
        "UserId": "AIDAR6SW7FM74MP5TLLY2",
        "Arn": "arn:aws:iam::134400125759:user/users/ynov/epeyrataud",
        "CreateDate": "2025-02-02T18:07:53+00:00",
        "PasswordLastUsed": "2025-02-06T08:58:08+00:00"
    },
    {
        "Path": "/users/ynov/",
        "UserName": "groux",
        "UserId": "AIDAR6SW7FM7WCAEZ2BEH",
        "Arn": "arn:aws:iam::134400125759:user/users/ynov/groux",
        "CreateDate": "2025-02-02T18:07:52+00:00",
        "PasswordLastUsed": "2025-02-06T08:59:38+00:00"
    }
]
```

#### 3. Afficher uniquement les noms des utilisateurs

```
users:~/environment $ aws --profile formation-infra-cloud iam list-users --path-prefix "/users/ynov/" --query "Users[].UserName" --output json
[

"epeyrataud"
"groux"
"gwattel"
"iotamendi"
"jbats"
"jpaillusseau"
"kschaffner"
"lhusson"
"mberguella"
"mlegrand"
"mtardio"
"rmarchais"
"rmartin"
"sperrin"
"tcurmi"
"tfourcade"
"tquesnoy"
"ymontagnier"

]
```
