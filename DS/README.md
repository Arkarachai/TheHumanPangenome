# Building haplotypes and graphs from full *de novo* assemblies

The goal of our team is to establish pipelines to build graph genomes from *de novo* assembly level data, as well as define a new coordinate system that will be retro-compatible with GRCh38 to enhance interoperability.

![panApe](https://github.com/NCBI-Hackathons/TheHumanPangenome/blob/master/DS/ds-vis1.png?raw=true "Title")

**The path of GRCh38 through a graph! For details check the DS folder!**


## Projects
### 1) define the best strategy to build genome graphs from *de novo* assemblies.

Blurb

Running the 3 pipelines

1- 
2- 
3- 

To explore the best strategy to build genome graphs from *de novo* assembled genomes, we designed two experiments. The first one is a simple proof of concept graph build using the Japanese genome assembly jg1 and GRCh38, and the second graph is a great-Apes graph using GRCh38, the Chimp (Clint), and Orangutan (Susie). We are comparing the graphs built using three different strategies: 

1) [Sequish](https://github.com/ekg/seqwish) [in progress]
We created a graph based on sequences from chromosome 21 from GRCh38 (CM000683.2), Clint the Chimpanzee (CM009259.2), Susie the Sumatran orangutan (CM009283.2), and CHM1 (AC244111.3, AC244144.2, AC244518.2, AC245051.3, AC245314.2, AC246819.2, AC255431.1, AC256301.1, AC277730.1, AC277802.1, AC277887.1).  We used first used minimap2 (v2.16-r922) with the parameter preset asm5 to do an all-vs-all alignment of the sequences. Next, we used seqwish (6e4fe705) to induce a graph in GFAv1 format.

We use vg view and index to convert the GFAv1 graph into vg format and build the different required indexes (Fig. 1).

(Insert pipeline here)

2) [SibeliaZ](https://github.com/medvedevgroup/SibeliaZ) [in progress]
We are creating a graph using chromosome 1 of the Japanese *de novo* assembly jg1 and GRCh38. We use SibeliaZ to build a locally-colinear blocks construction graph output in a MAF format. We build a MAF to vg converter, and used vg index to build the required indexes.

3) [Cactus](https://github.com/ComparativeGenomicsToolkit/cactus). [in progress]

Following the conversion we loaded the graph onto Bandage for visualisation (Fig. 2).

### 2) define a graph coordinate system that will be retro-compatible with GRCh38.

blurb

pseudo-code + figure


Slides: https://docs.google.com/presentation/d/1mocR6xLbRdgga79rXrkVModWd7YZiVCvTMXyQHhlBqU/edit?usp=sharing

TODOs:

- Write code to browse the graph and compute summary statistics.

- Finish Cactus runs.

ISSUES: 
- Seqwish doesn't output correct CIGAR strings.


## Contributors
|Name         |Email        |
| ----------- | ----------- |
| Benedict Paten | bpaten@ucsc.edu |
| Arkarachai Fungtammasan | arkarachai.af@gmail.com |
| Medhat Mahmoud | helmy.medhat@gmail.com |
| Jana Ebler |jebler@mpi-inf.mpg.de |
| Yassine Souilmi | yassine.souilmi@adelaide.edu.au |
| Valerie Schneider | schneiva@ncbi.nlm.nih.gov |
| Zev Kronenberg | zkronenberg@pacificbiosciences.com |
| Allison Regier | aregier@wustl.edu |
| Ilia Minkin | ivminkin@gmail.com |
