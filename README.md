# VCF positions for precise SV calls

Status: In progress

## Overview

This is guide to clarify the usage of positions for POS, END, and MATE_POS fields for structural variants inferred at basepair resolution and rendered to VCF 4.1 (or higher). The VCF spec leaves many clues on this topic but there is considerable room for off-by-one errors at VCF generation and parse stages.

## Conventions used in this guide

### 'Left' and 'Right'

All discussions below are based on the forward DNA strand, with "left" used to denote positions with a lower reference coordinate relative to "right" positions.

### Breakend Homology

Most SVs will have some amount of breakpoint homology, its representation is reasonably well defined in the VCF spec already. The guide below follows the NGS community convention of standarizing variants by describing the local breakend standardized to the left-most position within its homology range.

### Examples

All examples are drawn from public Platinum Genomes data for NA12878

## Exact VCF position examples for common SV types:

### Deletions (using VCF symbolic \<DEL\> allele)

#### Left end

POS indicates right-most position before crossing the left-shifted deletion left breakend:

![image](https://cloud.githubusercontent.com/assets/1349103/8995880/33972236-36c9-11e5-8408-ab1daf04cd66.png)

#### Right end
END indicates right-most position before crossing the left-shifted deletion right breakend

![image](https://cloud.githubusercontent.com/assets/1349103/8995887/3d969636-36c9-11e5-95a3-be0700efb5d9.png)

