Mikroarkitekturen implementerer ISA der ligger ovenover og designet bliver valgt ud fra hvor hurtig chippen skal være, og hvor dyr. Man bruger fetch-decode-execute cyklus af ISA-instrukser.
Den er generelt opbygget ved at du:
1. inkrememterer det trin du er nået til
2. laver noget opkode, 
3. finder noget data (medmindre man ikke skal det)
4. fetcher data 
5. eksekverer instruktionen.

