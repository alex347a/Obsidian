En **DC-motor (jævnstrømsmotor)** fungerer ved at omdanne **elektrisk energi (jævnstrøm)** til **mekanisk bevægelse** gennem vekselvirkningen mellem magnetfelter. Her er en gennemgang af, hvordan den virker **elektronisk**:

---

### **Vigtige elektroniske komponenter:**

1. **Stator** – Den stationære del, typisk en permanentmagnet eller elektromagnet, der skaber et fast magnetfelt.
    
2. **Rotor (Anker)** – Den roterende del, bestående af viklinger, der fører strøm.
    
3. **Kommutator** – En mekanisk kontakt (delt ring), der vender strømmens retning i rotorviklingerne.
    
4. **Børster** – Fører strøm fra strømkilden til kommutatoren (lavet af kul eller grafit).
    

---

### **Sådan virker den elektronisk:**

1. **Strøm tilføres**
    
    - Der tilføres en DC-spænding over børsterne, som fører den videre til kommutatoren.
        
    - Strøm løber gennem rotorviklingerne og skaber en **elektromagnet** med en nord- og sydpol.
        
2. **Magnetisk vekselvirkning**
    
    - Rotorens magnetfelt interagerer med statorens faste magnetfelt.
        
    - Modsat poler tiltrækker hinanden, og ens poler frastøder, hvilket får rotoren til at **rotere**.
        
3. **Kommutering (strøm-vending)**
    
    - Når rotoren drejer, vender kommutatoren **strømmens retning** i viklingerne på det rigtige tidspunkt.
        
    - Dette sikrer, at drejningsretningen forbliver ens, så motoren kan dreje kontinuerligt.
        
4. **Modspænding (Back EMF)**
    
    - Den roterende rotor inducerer en spænding (**modspænding**), der modvirker tilført spænding.
        
    - Dette begrænser motorens strømforbrug og regulerer hastigheden.
        

---

### **Elektronisk styring (hastighed & retning)**

- **Hastighedsregulering:**
    
    - Justering af **spændingen** (via PWM – pulsbreddemodulation) ændrer hastigheden.
        
    - Højere spænding → hurtigere rotation.
        
- **Retningskontrol:**
    
    - Hvis man vender **polariteten** af den tilførte spænding, skifter rotationsretningen.
        

---

### **Typer af DC-motorer:**

1. **Børstemor (traditionel DC-motor)** – Bruger børster og en kommutator (som beskrevet ovenfor).
    
2. **Børsteløs DC-motor (BLDC)** – Bruger elektronisk kommutering (Hall-sensorer og en controller i stedet for børster).
    

---

### **Opsummering:**

- **Strøm → Magnetfelt → Kraft (Lorentz-kraft) → Rotation.**
    
- **Kommutatoren** sikrer kontinuerlig rotation ved at vende strømmen.
    
- **Modspændingen** hjælper med at regulere hastighed og strøm.

## Lorentz-kraften
Lorentz-kraften er den kraft, der virker på en **elektrisk ladning** (f.eks. en elektron), når den bevæger sig gennem både et **magnetfelt** og et **elektrisk felt**. I en DC-motor er det denne kraft, der får rotoren til at rotere.

---

### **Formel for Lorentz-kraften**

Den samlede Lorentz-kraft (**F**) på en ladning (**q**) er givet ved:

F⃗=q⋅(E⃗+v⃗×B⃗)F=q⋅(E+v×B)

Hvor:

- **F** = Kraften (Newton)
    
- **q** = Elektrisk ladning (Coulomb)
    
- **E** = Elektrisk felt (Volt/meter)
    
- **v** = Hastigheden af ladningen (m/s)
    
- **B** = Magnetfeltet (Tesla)
    
- **×** = Krydsprodukt (bestemmer kraftens retning)
    

I en **DC-motor** er det primært **magnetfelt-delen** (v⃗×B⃗v×B) der skaber rotation.

---

### **Hvordan virker Lorentz-kraften i en DC-motor?**

1. **Strøm i viklingerne**
    
    - Når strøm løber gennem rotorens viklinger, skaber det et **magnetfelt** omkring lederne.
        
    - Elektroner bevæger sig gennem lederen og påvirkes af statorens **permanentmagnetfelt (B)**.
        
2. **Kraft på elektronerne (og dermed lederen)**
    
    - Ifølge Lorentz-kraften vil en ladet partikel i et magnetfelt føle en kraft vinkelret på både **strømretningen (v)** og **magnetfeltet (B)**.
        
    - Dette giver en **mekanisk kraft** på hele lederen, som får rotoren til at dreje.
        
3. **Højrehåndsreglen for retningen**
    
    - **Tommelfinger:** Strømretningen (I)
        
    - **Pegelfinger:** Magnetfeltet (B)
        
    - **Langefinger:** Kraftretningen (F)
        
    - I en DC-motor betyder dette, at kraften skubber rotoren rundt.
        

---

### **Eksempel i en DC-motor**

- **Stator:** Permanentmagneter skaber et fast **B-felt**.
    
- **Rotor:** Strøm (I) løber gennem viklinger.
    
- **Lorentz-kraften (F⃗=I⋅L⃗×B⃗F=I⋅L×B)** virker på hver leder i rotoren og skaber **drejningsmoment (τ)**.
	Hvor I er strømstyrken, L er længden af lederen og B er magnetfeltet.
- Drejningsmomentet er givet ved: $\tau = F \cdot r = (I \cdot L \cdot B) \cdot r$ kraft gange arm.
    
- **Resultat:** Rotoren drejer, og kommutatoren vender strømmen for at holde rotationen i gang.
    

---

### **Hvorfor er Lorentz-kraften vigtig?**

- Den forklarer, **hvorfor en motor drejer** (kraft på ladede partikler i et magnetfelt).
    
- Den bestemmer **motorens drejeretning** (afhænger af strøm- og magnetfeltretning).
    
- Den bruges også i andre elektromagnetiske enheder (f.eks. **generatorer, partikelacceleratorer**).