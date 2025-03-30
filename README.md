Ecco il testo finale in GitHub Flavored Markdown:

---

# Random Tester64 by Luigi Origa

I created this tool for personal use to generate and analyze random numbers produced by various algorithms. This is not your typical program that simply uses numbers generated by an LCG; instead, it offers several functionalities. Among the most useful features are:

- The ability to search for a specific byte sequence using a given seed.
- The capability to iterate through all seeds to find one that produces a matching sequence.
- The option to verify after how many generated numbers the same values recur.

## Command-Line Options

- **-type _nn_**  
  Selects the algorithm type to be used.

- **-seed _nn_**  
  Sets the initial seed.

- **-seed_size _nn_**  
  Specifies the seed size in bits.

- **-data_size _nn_**  
  Sets the size in bits of the generated numbers.

- **-output_shift_right _nn_**  
  Number of bits to shift right before printing the result (range: 0–63).

- **-output_shift_left _nn_**  
  Number of bits to shift left before printing the result (range: 0–63).

- **-output_size _nn_**  
  Number of bits to display from the result.

- **-create _nn_**  
  Generates _nn_ numbers using the specified settings.

- **-search first_sequence**  
  Searches for the initial sequence to determine after how many numbers the sequence repeats. Options include:
  - **first_seed** – tests all seeds until `sequence(seed)` equals `sequence(first_seed)`.
  - **sequence n n n...** – searches for a sequence such that `sequence == sequence(seed)`.
  - **bf_seed** – performs a brute-force search on the seed until `sequence(seed)` equals `sequence(0...nn)`.

- **-pattern_length 1-32**  
  Determines the length of the pattern to search for.

## Usage Examples

- **Generate 10 numbers using type 9 and seed 1:**

  ```bash
  RandomTester64.exe -type 9 -seed 1 -create 10
  ```

- **Search for the recurrence of a byte sequence using 8-bit generated numbers:**

  ```bash
  RandomTester64.exe -type 9 -seed 1 -search first_seed -data_size 8
  ```

- **Search for a specific byte sequence:**

  ```bash
  RandomTester64.exe -type 9 -seed 1 -search sequence 0x4a 0xe1 0x3d 0x6c -data_size 8
  ```

- **Search for the recurrence of a byte sequence using the full bit width of the generator:**

  ```bash
  RandomTester64.exe -type 9 -seed 1 -search first_seed
  ```

---

Puoi copiare e incollare questo testo nel file README.md del tuo repository GitHub. Se hai ulteriori richieste o modifiche, fammi sapere!
