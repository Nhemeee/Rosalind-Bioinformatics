# 🧬 Genomic Data Science Notebook

Welcome to my bioinformatics learning journal! I am tracking my progress solving computational biology problems on Rosalind, specifically focusing on core concepts applied to **Yeast Synthetic Biology & Metabolic Engineering**.

---

## 🏆 Completed Challenges

### 1. Counting DNA Nucleotides (DNA)
* **What it does:** Reads a raw DNA string and counts exactly how many times Adenine (`A`), Cytosine (`C`), Guanine (`G`), and Thymine (`T`) appear.
* **SynBio Relevance:** Essential for calculating **GC-content**, which dictates DNA stability and PCR melting temperatures for synthetic promoters.

```python
with open("C:/Users/HP/Downloads/rosalind_dna.txt", "r") as f:
    dna_string = f.read().strip().upper()

for base in ["A", "C", "G", "T"]:
    print(dna_string.count(base), end=" ")

2. Transcribing DNA into RNA (RNA)
What it does: Simulates biological transcription by converting a coding DNA strand into its messenger RNA (mRNA) sequence by replacing every Thymine (T) with Uracil (U).

SynBio Relevance: Mimics the first step of gene expression. When engineering a metabolic pathway, the host yeast cell must copy our synthetic DNA into mRNA before translating it into functional enzymes.

Python
with open("C:/Users/HP/Downloads/rosalind_rna.txt", "r") as f:
    dna_string = f.read().strip().upper()

rna_string = dna_string.replace('T', 'U')
print(rna_string)

3. Reverse Complement of DNA (REVC)What it does: Reverses the DNA strand backwards and pairs every letter with its molecular partner ($A \leftrightarrow T$, $C \leftrightarrow G$).SynBio Relevance: Crucial for PCR Primer Design. Because DNA is double-stranded and anti-parallel, we must synthesize the reverse complement sequence to create primers that bind perfectly to our target genes.Pythonwith open("C:/Users/HP/Downloads/rosalind_revc.txt", "r") as f:
    dna_string = f.read().strip().upper()

reversed_dna = dna_string[::-1]
base_pairs = str.maketrans("ATCG", "TAGC")
reverse_complement = reversed_dna.translate(base_pairs)

print(reverse_complement)

💡: The output text reads entirely backwards first. The letters at the front of the output string actually correspond to the very end of the original raw dataset!
