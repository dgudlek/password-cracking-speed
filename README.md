# password-cracking-speed

Comparison of password cracking with hashcat GPU, hashcat CPU and python CPU velocity

## Example information
 Password example: zzzz
 
 Attack mode: Brute-force
 
 Hash mode: sha512crypt $6$, SHA512 (Unix) 
 * Linux uses salted iterated hashing with 5000 iterations

## Results
* Hashcat GPU - 16394 Hashes per second
* Hashcat CPU - 324 Hashes per second
* Python CPU - 355 Hashes per second

GPU is ~50x faster than CPU.

## Run
* [Open hashcat GPU in colab](https://colab.research.google.com/github/dgudlek/password-cracking-velocity/blob/main/hashcat_gpu.ipynb)
* [Open hashcat CPU in colab](https://colab.research.google.com/github/dgudlek/password-cracking-velocity/blob/main/hashcat_cpu.ipynb)
* [Open python CPU in colab](https://colab.research.google.com/github/dgudlek/password-cracking-velocity/blob/main/hashcat_cpu.ipynb)

## Motivation
Implemented as part of my Masters's project.
