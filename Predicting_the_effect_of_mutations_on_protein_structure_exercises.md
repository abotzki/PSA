<i>Exercises created by Joost Van Durme</i>

> Part of [Protein Structure Analysis
> training](Protein_Structure_Analysis_training "wikilink")

## Introduction

Mutations in proteins can have various origins. Natural occurring
mutations are random and can have any kind of effect on the protein
structure and/or function. Mutations can have no effect at all, be
stabilizing of destabilizing. In the last two cases, these can lead to
diseases.

But we can also make mutations in the wet lab to study the effect of a
single residue position on protein stability, interaction with a peptide
ligand etc ... Such site-directed mutagenesis in the wet lab is hard
labour and costs money, I don't have to explain that to you. So wouldn't
it be easier, cheaper and more rational if you could predict the effect
of some mutations first with bioinformatics and then test the really
interesting ones in the lab?

FoldX is a molecular modeling tool that can quantitatively predict the
change in free energy (kcal/mol) upon mutation. These values approach
experimental determined values. FoldX is a non-interactive command line
program. In other words, not user friendly. But the bright news is that
I recently developed a YASARA plugin for FoldX, so that all predictions
are just a few clicks away. And the nice thing is, it's all free\!

## Our protein

In this section we will let the FoldX plugin loose on some real world
examples and give you step-by-step instructions on how to proceed and
analyze the results. We will use the P53 tumor suppressor protein as our
example molecule. In a first exercise you will make a point mutation
with FoldX and determine if the mutation is stabilizing or destabilizing
for the P53 structure. In a second exercise you will design a mutation
in the P53 structure at the DNA binding interface and determine how the
mutation affects the interaction energy of P53 with the DNA strand.

## FoldX energies

Before we start, some basic information about FoldX energies is
necessary.

First of all, FoldX energies are expressed in kcal/mol.

The main focus of FoldX is the prediction of free energy **changes**,
e.g. what happens to the free energy of the protein when we mutate an
Asp to a Tyr? FoldX will then calculate the free energy of the wild type
(WT) and the mutant (MT) and make the difference:

<div style="background:#FFDDFF;border:1px solid #FFC0CB;">

ddG(change) = dG(MT) - dG(WT)

</div>

FoldX is trained to make ddG(change) approach experimental values. It is
important to realize that dG(WT) and dG(MT) are meaningless numbers as
such. These do not correlate with experimental values. Only ddG(change)
does.

As a rule of thumb we use:

<div style="background:#FFDDFF;border:1px solid #FFC0CB;">

ddG(change) \> 0 : the mutation is destabilizing

ddG(change) \< 0 : the mutation is stabilizing

</div>

The error margin of FoldX is approximately 0.5 kcal/mol, so changes in
that range are insignificant.

## Minimizing the structure

FoldX assumes that the starting structure has been energy minimized.
Although crystal structures with high resolution represent the form with
a low energy, FoldX performs best when we minimize it just before we do
the predictions. This FoldX procedure is called **RepairPDB** and should
be done on each structure you want to perform calculations on.

Download and open the YASARA scene [2AC0.sce](Media:2AC0.sce "wikilink")
in YASARA. This is a part of a tetrameric complex of the transcription
factor P53 bound to DNA. I removed 3 of the 4 P53 structures for
simplicity and visualized some nice features.

Load the scene with:

    File > Load > YASARA Scene

![training_1.png](training_1.png "training_1.png")

To Repair (or minimize) the structure with FoldX go to:

    Analyze > FoldX > Repair object

![training_2.png](training_2.png "training_2.png")

And select the only object in the list.

When the Repair is finished, the Repaired Object is placed in Object 2
(see top right corner) and superposed with the original Object 1. Take a
look at the sidechains and see what FoldX has done while Repairing.

If you feel the repair takes too long (more than 10 minutes) due to a
slow computer, download and open [this YASARA Scene with the Repaired
Object](Media:2AC0_Repaired.sce "wikilink").

    File > Load > YASARA Scene

Because we will continue working with this Repaired Object, we can now
hide the entire Object 1 by toggling the **Vis**ibility column in the
top right corner head-up display (HUD).

## In silico mutagenesis

Turn on all the atoms in the DNA chain. These are chains/molecules G and
H.

    View > Show atoms in > Molecule > Name > G and H

Show the sidechain of Ala159 in the core of P53 by searching for it in
the sequence selector (in Object 2\!), right-click on it and go to:

    Show atoms > Residue sidechain and CA

![training_3.png](training_3.png "training_3.png")
![training_4.png](training_4.png
    "training_4.png")

    Zoom in on the Ala159 by keeping the CTRL button pressed and at the same time left click on it in the sequence selector.

We are going to mutate this residue to the largest natural amino acid,
tryptophan (W).

Right-click again on Ala159 in Object 2 in the sequence selector and go
to:

    FoldX > Mutate residue

![training_5.png](training_5.png "training_5.png")

A number of menus is now presented and here is what you need to do in
each menu:

1.  Only select **Calculate stability change**
2.  Select Trp
3.  'Move neighbours' and 'Show VdW clashes in WT and mutant'
4.  Don't change any numerical options in the last menu

![training_6.png](training_6.png "training_6.png")

## Analyze the mutation

FoldX has mutated the Ala to Trp and the structure with the Trp mutation
has been loaded in the next Object (3) and is superposed with the wild
type (WT, Object 2). We selected an option to show the VdW clashes in WT
and mutant. The atoms that give rise to steric clashes are colored in
<span style="color:red">**red**</span>. Toggle the **Vis**ibility of
Object 2 (WT) and Object 3 (mutant) and see how many clashes we
introduced by mutating the Ala to Trp.
![training_7.png](training_7.png "training_7.png")
![training_8.png](training_8.png
    "training_8.png")

    Van der Waals clashes are red colored atoms. Do you see a difference around the mutation site between WT and mutant? Toggle the Visibility of WT and
    mutant to see the differences.

Open the Console by pressing the spacebar twice and see the free energy
change of the mutation. Anything above a change of +0.5kcal/mol is
already assumed to be destabilizing.

    Is the Ala195Trp mutation destabilizing or stabilizing?

![training_9.png](training_9.png "training_9.png")

## Another mutation

Hide Object 3 by toggling its **Vis**ibility so that only Object 2 (the
repaired WT) is visible.
First turn on all atoms in the molecules G and H (DNA) again as you did
previously, because the FoldX run has hidden it (it rearranged the view
to show the VdW clashes).

Show the sidechain of Arg273 of Object 2 by searching for it in the
sequence selector, then right-click on it and go to:

    Show atoms > Sidechain and CA

    Zoom in on Arg273

**Notice how the positively charged Arginine is making an electrostatic
interaction with the negative phosphate from the DNA backbone.**

![training_10.png](training_10.png "training_10.png")

Let's see what would happen to the interaction energy between the DNA
and P53 when we mutate this Arginine to Alanine.

Right-click on this Arg273 in the sequence selector and go to:

    FoldX > Mutate residue

A number of menus is now presented and here is what you need to do in
each menu:

1.  Select **Calculate interaction energy change**
2.  Select Ala
3.  'Move neighbours' and 'Show disrupted and new hydrogen bonds'
4.  Don't change any numerical options in the last menu

![training_11.png](training_11.png "training_11.png")

Toggle the **Vis**ibility between this mutant and the WT structure and
see how the hydrogen bonding
    changes.

    Check the output in the Console to see what the change in interaction energy is between P53 and DNA chain G upon mutation.

![training_12.png](training_12.png
    "training_12.png")

    Why doesn't the mutation affect the interaction with DNA chain H?

    Instead of DNA-protein, FoldX can of course also calculate interaction energy changes in protein-protein or peptide-protein complexes.