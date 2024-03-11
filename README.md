# Renaming-spades-assembled-file-for-prokka-
```
#!/usr/bin/env python3

input_file = "contigs.fasta"
output_file = "renamed_contigs.fasta"

with open(input_file, 'r') as f:
    contigs = f.read().split('>')[1:]

with open(output_file, 'w') as f:
    for i, contig in enumerate(contigs, 1):
        lines = contig.split('\n')
        header = lines[0]
        sequence = '\n'.join(lines[1:])
        f.write(f'>contig{i}\n{sequence}\n')

print("Contigs renamed successfully.")
```
