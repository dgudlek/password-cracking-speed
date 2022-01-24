# password-cracking-speed

This repository demonstrates a way to attempt recovering a Linux password given its hash using offline password guessing.

We also compare the guessing speed achieved by CPU and GPU implementations.

## Background

Offline password guessing attacks can be slowed down using iterated hashing and salting.

Linux (Debian buster) is using salted SHA512 hashing with 5000 iterations.

The file with password hashes is located in `/etc/shadow`.

[Hashcat](https://hashcat.net/hashcat/) was used to run the offline password guessing on CPU and GPU.

Additional implementation in Python was tested that uses `crypt` library to compute hashes.

## Experiment setup

* Password: zzzz
* Attack mode: Brute-force
* Hash mode: sha512crypt $6$, SHA512 (Unix)
* CPU: Intel(R) Xeon(R) CPU @ 2.20GHz, 2 cores
* GPU: Tesla T4, 40 CORES
 
## Results

* Hashcat GPU - 16394 Hashes per second
* Hashcat CPU - 324 Hashes per second
* Python crypt - 355 Hashes per second

Takeaways:
* GPU is ~50x faster than CPU.
* Hashcat on CPU doesn't offer any hash computation speed improvements over Python crypt implementation

## How to re-run

* [Open hashcat GPU in colab](https://colab.research.google.com/github/dgudlek/password-cracking-speed/blob/main/hashcat_gpu.ipynb)
* [Open hashcat CPU in colab](https://colab.research.google.com/github/dgudlek/password-cracking-speed/blob/main/hashcat_cpu.ipynb)
* [Open python crypt in colab](https://colab.research.google.com/github/dgudlek/password-cracking-speed/blob/main/python_crypt.ipynb)

## Motivation

Implemented as part of my Masters's project.
