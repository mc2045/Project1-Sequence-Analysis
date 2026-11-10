# Project 1 - Sequence-Analysis
Gene sequencing analysis to identify gene differentiation

## Title & Purpose:

This program analyses all reads, identifying DNA mismatches against a reference and compares mismatch patterns between genotoxic-agent-treated and untreated S. pombe samples, as well as recording any errors and identifying top mismatch positions.

## How to run the program:

1. File -> Open Notebook in Colab 
2. Runtime -> Run all
3. The setup cells download the required data

## Inputs and outputs:

**Inputs** - _reference.txt_ (200-nt reference) and _reads.csv_ (6000 reads across 6 samples).
**Outputs** - dictionaries providing range of information about the list of reads e.g. - sample summaries, substitution counts, top mismatch positions and statistical comparisons.

## Code-design:

**Choice:** Used seperate helpers for counting reads, events, substitutions and positions. Reason: Made it easier to understand and test each calculation as opposed to one large summary function.

**Choice:** Checked whether a sample appeared under multiple group labels. Reason: To detect any inconsistant metadata before producing potentially misleading summaries.

**Choice:** Stored test inputs and expected outputs in a list of dictionaries, processed using a loop rather than separate test blocks. Reason: Let me add test cases without repeating the test code.

## Testing:

**Lower case input:** Converted to uppercase and accepted when otherwise valid.

**Multiple validation errors:** "_ATN_" returned both "_wrong_length_" and "_invalid_characters_" in the required order.

**Mismatches at sequence boundaries:** "_GTGA_" against "_ATGC_" returned mismatches at position **1** and **4**, checking both ends and numbering from **1**.

**Summarise samples (Step 4):** Specifically tested with Edge cases of empty data and data that would generate "_None_" outputs. Also tested with 7 readings across 2 groups with a variety of substitution mutations.

**All four tests passed.**

# Git hub repository
https://github.com/mc2045/Project1-Sequence-Analysis
