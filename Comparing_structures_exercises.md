<i>Exercises created by Joost Van Durme</i>

> Part of [Protein Structure Analysis
> training](Protein_Structure_Analysis_training "wikilink")

## Structural comparison and RMSD

We compare structures by superposing (or structurally align) them on top
of each other. That is, we superpose structurally equivalent atoms. For
now, we will only superpose CA atoms, so backbones. But Yasara also can
superpose on any type of atom you want. You always need to specify:

  - source object(s): the structure(s) that needs to be rotated and
    translated to superpose on another structure
  - target object: the structure to superpose on

An optimal superposition is found when the root-mean-square deviation
(RMSD) is at a minimum. The RMSD is given as:

![RMSD.gif](RMSD.gif "RMSD.gif")

Where *R* is the distance between two structurally equivalent atom pairs
(CA in our case) and *n* is the total number of atom pairs.

## Exercise

Download the five files containing each a different crystal structure of
the chaperone DnaK: [1DKX_1.pdb](Media:1DKX_1.pdb "wikilink"),
[1DKY_1.pdb](Media:1DKY_1.pdb "wikilink"),
[1DKZ_1.pdb](Media:1DKZ_1.pdb "wikilink"),
[3DPO_1.pdb](Media:3DPO_1.pdb "wikilink"),
[3DPP_1.pdb](Media:3DPP_1.pdb "wikilink").

Now load all of them in YASARA:

    File > Load > PDB File

and select the CA (C-alpha) view (F4) and superpose with the MUSTANG
algorithm:

    Analyze > Align > Objects with MUSTANG

In the first window you have to select the source objects that will be
repositioned. Select Objects 2 till 5. In the second window you select
the target Object to superpose on. That would then be the first object.

Notice that YASARA prints the RMSD of every superposition in the lower
Console. Open the Console by pressing the *spacebar* once or twice to
extend it.

Color the atoms by their
    B-factor:

    View > Color > Atom > Belongs to or has > All

    Then choose BFactor in the next window and press 'Apply unique color'.

High BFactors are yellow, low BFactors are
    blue.

    Do you see a correlation between the BFactors and the variability in the structure?