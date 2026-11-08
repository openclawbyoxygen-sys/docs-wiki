# DUE Drug & Pathogen Mapping

## Data_Jan26 Column Structure

| ข้อมูล | Column Range | Header Row |
|--------|--------------|------------|
| Drug indicators | 87-102 | 3 |
| Vials | 148-163 | 3 |
| Sale prices | 164-179 | 2 (price), 3 (name) |
| Pathogens | 117-146 | 3 |
| เหมาะสม | 185 | - |
| ไม่เหมาะสม | 186 | - |
| ประเมินไม่ได้ | 187 | - |

## Drug Mappings

### DUE Summary (Template → Data)

| Template (Jan26) | Data (Data_Jan26) |
|------------------|-------------------|
| Sulperazone 1 GM | Cefoperazone/Sulbactam 1.5 g |
| Sulperazone 1.5 GM | Cefoperazone/Sulbactam 1.5 g |
| Astaz-P | Piperacillin/Tazobactam |
| Biapenem | Biapenem |
| Colistin | Colistin |
| Fosfomycin | Fosfomycin ORAL |
| Fosfomycin (space) | Fosfomycin INJ. |
| Ertapenem (O) | Ertapenem (O) |
| Ertapenem (L) | Ertapenem (L) |
| Imipenem | Imipenem |
| Meropenem | Meropenem |
| Vancomycin (O) | Vancomycin (O) |
| Vancomycin (L) | Vancomycin (L) |
| Unasyn 1.5 GM | Ampicillin/Sulbactam |
| Doripenem | Doripenem |
| TYGACIL | Tigecycline |
| Linezolid | Linezolid |

### สรุปเชื้อก่อโรค (Jan_26 → Data)

| Jan_26 Drug | Data Drug |
|-------------|-----------|
| Ampicillin/Sulbactam | Ampicillin/Sulbactam |
| Piperacillin/Tazobactam | Piperacillin/Tazobactam |
| Cefoperazole/Sulbactam | Cefoperazone/Sulbactam 1.5 g |
| Imipenem/Cilastatin | Imipenem |
| Meropenem | Meropenem |
| Ertapenem (O) | Ertapenem (O) |
| Ertapenem (L) | Ertapenem (L) |
| Doripenem | Doripenem |
| Biapenem | Biapenem |
| Vancomycin(O) | Vancomycin (O) |
| Vancomycin(L) | Vancomycin (L) |
| Colistin | Colistin |
| Fosfomycin ORAL | Fosfomycin ORAL |
| Fosfomycin INJ | Fosfomycin INJ. |
| Linezolid | Linezolid |
| Tigecycline | Tigecycline |

### สิทธิ์การรักษา (Brand → Generic → Cost)

| Brand (Data) | Generic (Data) | Cost Table Name |
|--------------|----------------|-----------------|
| Meropenem | Meropenem | Meropenem |
| Astaz-P | Piperacillin/Tazobactam | Astaz-P |
| Sulperazone 1 GM | Cefoperazone/Sulbactam 1.5 g | Sulperazone 1g |
| Sulperazone 1.5 GM | Cefoperazone/Sulbactam 1.5 g | Sulperazone 1.5g |
| Piperacillin/Tazobactam | Piperacillin/Tazobactam | Astaz-P |
| Ampicillin/Sulbactam | Ampicillin/Sulbactam | Unasyn |
| Imipenem | Imipenem | Imipenem |
| Ertapenem (O) | Ertapenem (O) | Ertapenem (O) |
| Ertapenem (L) | Ertapenem (L) | Ertapenem (L) |
| Biapenem | Biapenem | Biapenem |
| Vancomycin (O) | Vancomycin (O) | Vancomycin (O) |
| Vancomycin (L) | Vancomycin (L) | Vancomycin (L) |
| Colistin | Colistin | Colistin |
| Fosfomycin ORAL | Fosfomycin ORAL | Fosfomycin Oral |
| Fosfomycin INJ. | Fosfomycin INJ. | Fosfomycin inj. |
| Linezolid | Linezolid | Linezolid |
| Tigecycline | Tigecycline | Tigecycline (O) |

## Pathogen Mappings

| Jan_26 | Data_Jan26 |
|--------|------------|
| Acinetobactor spp. | Acinetobacter spp. |
| Acinetobactor spp. (MDR, XDR) | Acinetobacter spp. (MDR, XDR) |
| Bacillus Spp. | Bacillus Spp. |
| Burkholderia spp. | Burkholderia spp. |
| Clostridium difficile | Clostridium difficile |
| Citrobacter spp. | Citrobacter spp. |
| Enterobacter spp. | Enterobacter spp. |
| Enterobacter spp. (MDR) | Enterobacter spp. (MDR) |
| Enterococcus spp. | Enterococcus spp. |
| Enterococcus spp. (MDR) | Enterococcus spp. (MDR) |
| Escherichia coli | Escherichia coli |
| Escherichia coli (ESBL) | Escherichia coli (ESBL) |
| Haemophilus influenzae | Haemophilus influenzae |
| Klebsiella spp. | Klebsiella spp. |
| Klebsiella spp. (ESBL) | Klebsiella spp. (ESBL) |
| Proteus spp. | Proteus spp. |
| Pseudomonas aeruginosa | Pseudomonas aeruginosa |
| Pseudomonas aeruginosa (MDR) | Pseudomonas aeruginosa (MDR) |
| Salmonella spp. | Salmonella spp. |
| Serratia marcescens | Serratia marcescens |
| Staphylococcus spp. | Staphylococcus spp. |
| Staphylococcus aureus (MSSA) | Staphylococcus aureus (MSSA) |
| Staphylococcus aureus (MRSA) | Staphylococcus aureus (MRSA) |
| Streptococcus pneumoniae | Streptococcus pneumoniae |
| Streptococcus spp. (Group A,B,C,G) | Streptococcus spp. (Group A,B,C,G) |
| Stenotrophomonas maltophilia | Stenotrophomonas maltophilia |
| Fungus | Fungus |
| No Growth | No Growth |
