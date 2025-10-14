### 3 Måder at optimere en MIC processor
1. Chip størrelse:
	- Stor og kompleks chip er dyr men hurtig
	- Lille og simpel chip er billig men langsom.
2. Mikrokode optimering ved at reducere antallet af cykluser pr. IJVM-instruktion

3. Modificering af data-path reducerer antallet af cykluser pr. IJVM-instruktion.
	Man kan bruge pipelining til at eksekvere flere instruktioner samtidigt ved at aktivere alle forskellige stadier i en processor.
Der er nogle risici ved at lave pipelining:
### Strukturelle risici
- Når hardwaren ikke understøtter bestemte kombinationer af instruktioner samtidigt
![[Pasted image 20251013201624.png]]
![[Pasted image 20251013201647.png]]

### Data-risici
- Når der skal ventes på at dataet er klar til at blive læst
![[Pasted image 20251013201702.png]]
![[Pasted image 20251013201712.png]]
![[Pasted image 20251013201724.png]]
![[Pasted image 20251013201742.png]]
### Kontrol-risici
- Når der er forgreninger der ændrer pipelinen.
![[Pasted image 20251013201754.png]]

### Cache
![[Pasted image 20251013201812.png]]
![[Pasted image 20251013202005.png]]
#### Cache: Tilgangstid
![[Pasted image 20251013202022.png]]
![[Pasted image 20251013202044.png]]
![[Pasted image 20251013203710.png]]
![[Pasted image 20251013203720.png]]
![[Pasted image 20251013203729.png]]
![[Pasted image 20251013203739.png]]

Den første opgave ligger i excelarket: Opgaver6
Den anden opgave er et pythonscript der hedder: Opgave6.py

Konklusion fra Pythonopgaven:

| Entries | LineSize | Pattern    | HitRate (%) |
|----------|-----------|------------|-------------|
| 4        | 4         | Sequential | 0.00        |
| 4        | 4         | Random     | 9.38        |
| 4        | 8         | Sequential | 50.00       |
| 4        | 8         | Random     | 17.19       |
| 4        | 16        | Sequential | 75.00       |
| 4        | 16        | Random     | 34.38       |
| 8        | 4         | Sequential | 0.00        |
| 8        | 4         | Random     | 17.19       |
| 8        | 8         | Sequential | 50.00       |
| 8        | 8         | Random     | 31.25       |
| 8        | 16        | Sequential | 75.00       |
| 8        | 16        | Random     | 46.88       |
| 16       | 4         | Sequential | 0.00        |
| 16       | 4         | Random     | 29.69       |
| 16       | 8         | Sequential | 50.00       |
| 16       | 8         | Random     | 42.19       |
| 16       | 16        | Sequential | 75.00       |
| 16       | 16        | Random     | 75.00       |

Sequential access patterns achieve higher hit rates due to spatial locality. Increasing line size generally increases hit rate for the sequential pattern but has little effect for random patterns. Increasing the number of entries also improves hit rate by reducing conflict misses.