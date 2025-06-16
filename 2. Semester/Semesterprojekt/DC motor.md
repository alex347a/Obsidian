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