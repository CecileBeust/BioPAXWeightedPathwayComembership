## Weighted pathway co-membership networks from BioPAX pathways 

This repository contains code to abstract BioPAX pathways into weighted pathway co-membership networks.
This work has been pre-published as a prepring on bioRxiv at [https://doi.org/10.64898/2026.09.30.755656]

Required Python libraries : 
- pandas
- networkx
- numpy
- matplotlib
- sklearn
- subprocess
- SPARQLwrapper
- multixrank

Data files to download: 
- BioPAX ontology: https://www.biopax.org/release/biopax-level3.owl
- Reactome BioPAX export (here the version 96 is used, but use the following link to download the latest version): https://download.reactome.org/version/biopax.zip

1 - We start by generating a pathway-centered abstraction on BioPAX pathways that extracts the compositional hierarchy and sequences of pathways from the BioPAX export. The scripts to generate this abstraction are located in the `Scripts/01_PathwayAbstraction` folder. Generated pathway-cenetered abstractions of the 29 Reactome top-level pathways (version 96) are located in the `Results/PathwayAbstraction/01_TopPathways` folder. The pathway-centered abstraction of the whole Reactome knowledge base (version 96) is located in the `Results/PathwayAbstraction/02_Reactome96Global` folder.

2 - Then we use our pathway-centered abstraction to weight protein co-memberhsip interactions. The scripts to generate weighted pathway co-membership networks are located in the `Scripts/02_PathwayComembershipAbstraction` folder. Weighted co-membership networks of the 29 Reactome top-level pathways (version 96) are located in the `Results/PathwayComembership/02_WeightedComembershipCliques` folder. The weighted co-membership clique of the entire Reactome pathway knowledge base (version 96) is located in the `Results/PathwayComembership/06_ScalingReactome` folder.
 
3 - Our weighted pathway co-membership abstraction method is validated using a gene prioritization experiment on cancer hallmarks gene sets (from https://cancerhallmarks.com/) using random walk with restart. Associated scripts are located in the `Scripts/03_RWRComembership` folder. RWR results are located in the `Results/ValidationRWROutput` folder.

### References

- Demir E, Cary MP, Paley S, Fukuda K, Lemer C, Vastrik I, Wu G, D'Eustachio P, Schaefer C, Luciano J, Schacherer F, Martinez-Flores I, Hu Z, Jimenez-Jacinto V, Joshi-Tope G, Kandasamy K, Lopez-Fuentes AC, Mi H, Pichler E, Rodchenkov I, Splendiani A, Tkachev S, Zucker J, Gopinath G, Rajasimha H, Ramakrishnan R, Shah I, Syed M, Anwar N, Babur O, Blinov M, Brauner E, Corwin D, Donaldson S, Gibbons F, Goldberg R, Hornbeck P, Luna A, Murray-Rust P, Neumann E, Ruebenacker O, Samwald M, van Iersel M, Wimalaratne S, Allen K, Braun B, Whirl-Carrillo M, Cheung KH, Dahlquist K, Finney A, Gillespie M, Glass E, Gong L, Haw R, Honig M, Hubaut O, Kane D, Krupa S, Kutmon M, Leonard J, Marks D, Merberg D, Petri V, Pico A, Ravenscroft D, Ren L, Shah N, Sunshine M, Tang R, Whaley R, Letovksy S, Buetow KH, Rzhetsky A, Schachter V, Sobral BS, Dogrusoz U, McWeeney S, Aladjem M, Birney E, Collado-Vides J, Goto S, Hucka M, Le Novère N, Maltsev N, Pandey A, Thomas P, Wingender E, Karp PD, Sander C, Bader GD. **The BioPAX community standard for pathway data sharing**. Nat Biotechnol. 2010 Sep;28(9):935-42. doi: 10.1038/nbt.1666. Epub 2010 Sep 9. Erratum in: Nat Biotechnol. 2010 Dec;28(12):1308. Erratum in: Nat Biotechnol. 2012 Apr;30(4):365. Reubenacker, Oliver [corrected to Ruebenacker, Oliver]. PMID: 20829833; PMCID: PMC3001121.

- Ragueneau E, Gong C, Sinquin P, Sevilla C, Beavers D, Grentner A, Griss J, Hogue GFJ, Li NT, Matthews L, May B, Milacic M, Mohammadi H, Petryszak R, Rothfels K, Shamovsky V, Stephan R, Tiwari K, Weiser J, Wright A, Gillespie M, Wu G, Stein L, Hermjakob H, D'Eustachio P. **The Reactome Knowledgebase 2026**. Nucleic Acids Res. 2026 Jan 6;54(D1):D673-D681. doi: 10.1093/nar/gkaf1223. PMID: 41251150; PMCID: PMC12807730.

- Otília Menyhart, William Jayasekara Kothalawala, Balázs Győrffy, **A gene set enrichment analysis for cancer hallmarks**,
Journal of Pharmaceutical Analysis, Volume 15, Issue 5, 2025, 101065, ISSN 2095-1779, https://doi.org/10.1016/j.jpha.2024.101065.
