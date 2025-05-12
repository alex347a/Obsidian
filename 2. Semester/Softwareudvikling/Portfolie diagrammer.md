Portfolie usecase
Brugsmønstre:
![[Brugsmønstre.docx]]
![[Portfolie usecase.png]]

Portfolie domænemodel (første iteration ikke helt gennemført)
![[Portfolie domænemodel.png]]
Portfolie domænemodel første iteration
![[Domænemodel.drawio.png]]

sequenceDiagram
    participant Spiller
    participant GameManager
    participant Hero

    Spiller->>GameManager: vælg hero
    GameManager->>Hero: opret Hero (kopi af predefineret)
    GameManager-->>GameManager: aktivHero = ny Hero


sequenceDiagram
    participant Spiller
    participant GameManager
    participant Hero
    participant Fjende

    Spiller->>GameManager: vælg fjende
    GameManager->>Fjende: hent fjende

    loop Så længe begge er i live
        Spiller->>GameManager: tryk ENTER
        GameManager->>Fjende: fjende.tagSkade(helt.hentStyrke())
        Fjende-->>GameManager: nyt HP

        alt Fjende stadig i live
            GameManager->>Hero: helt.tagSkade(fjende.hentStyrke())
        end
    end

    alt Helt vinder
        GameManager->>Hero: givXP()
        GameManager->>Hero: levelOp()
        GameManager->>Hero: givFuldHP()
    else Fjende vinder
        GameManager-->>Spiller: Helt døde
    end

Portfolie klassediagram: (første iteration, ikke helt gennemført)
![[Portfolie klassediagram 1. iteration (ikke færdig).png]]

Portfolie klassediagram: Første iteration:
![[Portfolie klassediagram 1. iteration.png]]