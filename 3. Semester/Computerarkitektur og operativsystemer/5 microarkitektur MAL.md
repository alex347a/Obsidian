## Micro Assembly Language (MAL)
### Syntaks
Kommutativt, man kan skrive koden med forskellige rækkefølge og så gør den det samme, så H + SP kan også skrives SP + H.
Man må ikke skrive minus foran noget der ikke må subtraheres.
H = H - MDR, kan ikke udføres, da H skal være subtrahend dvs. minus skal stå foran H og ikke MDR.

### Betinget forgrening (Conditional branch)
Hvis resultatet af ALU'en er 0 så bliver Z bittet højt, mens hvis resultatet af ALU'en bliver negativt så bliver N-bittet højt.

L1 skal være 256 fra L2 i JAMZ altså 0x100.

