Portfolie usecase
Brugsmønstre:
![[Brugsmønstre.docx]]
![[Portfolie usecase.png]]

Portfolie domænemodel første iteration
![[Domænemodel.drawio.png]]
Portfolie domænemodel anden iteration:


Portfolie domænemodel tredje iteration:
![[3. Iteration domænemodel.drawio.png]]

Udvalgt sekvensdiagram (1. iteration) (load en eksisterende hero)
![[Udvalgt sekvensdiagram (load en eksisterende hero).png]]
Kode
	sequenceDiagram
	    participant Spiller
	    participant GameManager
	    participant Hero
	
	    Spiller->>GameManager: vælg hero
	    GameManager->>Hero: opret Hero (kopi af predefineret)
	    GameManager-->>GameManager: aktivHero = ny Hero


Udvalgt sekvensdiagram (1. iteration) (Hero kæmper mod fjende)
![[Udvalgt sekvensdiagram (Hero kæmper mod fjende).png]]
Kode
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

Sekvensdiagram over kamp i grotte med våben.

![[3. Iteration Sekvensdiagram.png]]

Portfolie klassediagram: Første iteration:
![[Portfolie klassediagram 1. iteration.png]]
Portfolie klassediagram: Anden iteration:
![[2. iteration klassediagram.png]]
Portfolie klassediagram: Tredje iteration:
![[3. Iteration klassediagram.png]]