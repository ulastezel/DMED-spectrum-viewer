# DMED Spectrum Viewer

A browser viewer for an in-silico LC-MS/MS library of DMED-derivatized lipid acids. It was built to help identify the biological origin of lipid residues in archaeological pottery.

ARChaeometry Research Center, Boğaziçi University funded by BAP 25A04P4.

## What it does

- Browse 5,131 DMED (N,N-dimethylethylenediamine) amides of carboxylic acids and 5,481 predicted MS/MS spectra ([M+H]+, and [M+2H]2+ for di- and tri-acids).
- Search by name, abbreviation, formula, LIPID MAPS ID or precursor m/z.
- Filter by lipid class, archaeological source category, evidence level and organism group.
- Show the 2D structure of the DMED derivative or the free acid.
- Classification panel: archaeological marker interpretation with evidence level and caveats, and organism groups reported in LIPID MAPS.
- Switch between a beam-type CID model (QTrap EPI, Q-TOF, HCD) and an ion-trap CID model.
- Paste a measured spectrum to get a mirror plot and a similarity score, or search the whole library.
- Open any other MSP library file in the same viewer.

Everything runs in the browser. There is no server and nothing is uploaded.

## Use

Open `index.html` in a browser, or use the GitHub Pages site of this repository.

## How the library was made

1. Lipids listed in our lab list were taken from the LIPID MAPS Structure Database.
2. Each structure was hydrolysed in silico: native free acids, base hydrolysis (KOH saponification of esters, lactones and thioesters) and acid hydrolysis (also glycosides and epoxides).
3. Every free carboxyl was tagged with DMED (+70.0895 Da per COOH).
4. MS/MS spectra were predicted with rules calibrated on the authentic DMED-FAHFA spectra of Ding et al. (2020): dimethylamine loss (NL 45.0578) as the base peak, NL 63.0684 for hydroxy acids, and ester cleavage ions for FAHFAs.
5. Organism groups come from the NCBI taxonomy links in LIPID MAPS. Archaeological marker tags come from published biomarker rules.

## Limitations

- Spectra are predicted, not measured. Intensities are approximate.
- The reporter ions at m/z 72.08, 58.07 and 46.07 are not validated on standards.
- Isomers (double bond, hydroxyl or branch position, stereochemistry) have the same spectrum. Use retention time or standards to separate them.
- LIPID MAPS organism records are sparse and biased toward biomedical and model organisms. Treat them as hints.
- Dairy vs carcass fat and marine vs freshwater cannot be separated by LC-MS. They need compound-specific d13C analysis.

## References

- Ding J, Kind T, Zhu Q-F, Wang Y, Yan J-W, Fiehn O, Feng Y-Q (2020). In-silico-generated library for sensitive detection of 2-dimethylaminoethylamine derivatized FAHFA lipids using high-resolution tandem mass spectrometry. Analytical Chemistry 92, 5960-5968.
- LIPID MAPS Structure Database (LMSD), lipidmaps.org, CC BY 4.0.
- Regert M (2011). Analytical strategies for discriminating archeological fatty substances from animal origin. Mass Spectrometry Reviews 30, 177-220.

Third-party code and data notices are in `THIRD_PARTY_NOTICES.md`.
