# From-Reads-to-Paired-Composition-k-d--mers


# Description

This script generates a list of (k,d)-mers from a given DNA string. Each (k,d)-mer consists of a pair of k-length substrings separated by a fixed distance d. These paired k-mers serve as the basis for genome assembly from paired-end reads in bioinformatics. 

# Usage
Example 
```
def paired_composition(k, d, text):
    kdmers = list()
    for i in range(len(text) - 2*k - d + 1):
        kdmers.append((text[i:i+k], text[i+k+d:i+2*k+d]))
    return sorted(kdmers)

def display_kdmers(kdmers):
    return ' '.join(map(lambda x: f'({x[0]}|{x[1]})', kdmers))

kdmers = paired_composition(3, 2, 'TAATGCCATGGGATGTT')
print(display_kdmers(kdmers))
```

Output 

(AAT|CAT) (ATG|ATG) (ATG|ATG) (CAT|GAT) (CCA|GGA) (GCC|GGG) (GGG|GTT) (TAA|CCA) (TGC|TGG) (TGG|TGT)

# Function Descriptions
* paired_composition(k, d, text)

Generates all (k,d)-mers from a given string text, where each pair consists of two k-length substrings separated by distance d.
* display_kdmers(kdmers)

Formats the list of (k,d)-mers as a readable string for output or visualization.

# Applications
* Paired-read genome assembly
* Bioinformatics education and algorithm development
* Preprocessing for construction of de Bruijn graphs from paired reads

# License

This project is licensed under the MIT License.





