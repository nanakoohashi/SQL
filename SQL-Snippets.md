# Insert into MS Access WHERE NOT EXISTS 
## Purpose
The code below inserts entries into the database that do not already exist in the database.
## Code
```INSERT INTO CreditScoreBandsPOC (Relationship, ProductType, CreditProduct, AsOfDate, NumbFICOLessThan500, NumbFICO550to599, NumbFICO600to649, NumbFICO650to699, NumbFICO700to749, NumbFICO750to799, NumbFICO800Plus, DollFICOLessThan500, DollFICO500to549, DollFICO550to599, DollFICO600to649, DollFICO650to699, DollFICO700to749, DollFICO750to799, DollFICO800Plus)
SELECT Relationship, ProductType, CreditProduct, AsOfDate, NumbFICOLessThan500, NumbFICO550to599, NumbFICO600to649, NumbFICO650to699, NumbFICO700to749, NumbFICO750to799, NumbFICO800Plus, DollFICOLessThan500, DollFICO500to549, DollFICO550to599, DollFICO600to649, DollFICO650to699, DollFICO700to749, DollFICO750to799, DollFICO800Plus
FROM [text;HDR=Yes;FMT=Delimited(,);Database=C:\\Users\\no\\Automation\\Contract Services\\Risk Assessment].CleanedCreditScoreDistributions.csv AS t
WHERE NOT EXISTS (SELECT 1 FROM CreditScoreBandsPOC new WHERE new.Relationship = t.Relationship AND new.ProductType = t.ProductType AND new.CreditProduct = t.CreditProduct AND new.AsOfDate = t.AsOfDate)""")
```
