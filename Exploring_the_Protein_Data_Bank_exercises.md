<i>Exercises created by Joost Van Durme</i>

> Part of [Protein Structure Analysis
> training](Protein_Structure_Analysis_training "wikilink")

## Search for a structure

  - Via [UniProt](http://www.uniprot.org/)

The way of searching for a specific protein structure depends on the
data you already have. You might already have the PDB ID (a unique
identifier), that's an easy one. But mostly you have the protein name or
you just have a sequence. In the last cases I recommend to start from
the UniProt website at <http://www.uniprot.org>, which is the best
annotated protein database in the world. Our first model protein will be
the molecular chaperone DnaK from *E. coli*.

Below is an image of the UniProt search box where you can start your
search for proteins.

![Uniprotsearchbox.png](Uniprotsearchbox.png "Uniprotsearchbox.png")

    Go to the UniProt website and search for the DnaK protein

The UniProt search engine returns a list of DnaK protein sequences from
a variety of organisms. An entry with accession code **P0A6Y8** and
entry name **DNAK_ECOLI** should be near the top of this list. Click on
the *accession code* (column Entry) to view the protein page of this
DnaK from the model organism *Escherichia coli*. Click on *Structure* in
the left-side menu and then look at the *3D structure databases*
    table.

    Which structures (give the 4-character PDB ID) of the C-terminal domain of DnaK should preferentially be use for analysis and why?

Select 'RCSB PDB' on the left side of the table and then click on the
first interesting candidate in the list e.g. 1DKX. This should open the
structure page on the RCSB website.

  - Via the Protein Data Bank by PDB ID

You can find structural information directly at the PDB database. The
web site of the PDB consortium is located at <http://www.wwpdb.org>.
This web site provides links to all members of the PDB (left side). It
is a question of taste which resource you start off with. For X-ray
structures, it is currently PDBe, RCSB PDB, PDBj. For NMR structres, you
find the BMRB. In today's course, we focus on the PDB resources only.

Below is an image of the RCSB search box
(http://www.rcsb.org/pdb/home/home.do) where you can start your search
for structures.

![Pdbsearchbox_RCSB.png](Pdbsearchbox_RCSB.png "Pdbsearchbox_RCSB.png")

The PDB file with ID **1DKX** contains the atomic coordinates of the
molecular chaperone (DnaK) from *E. coli*.

    Go to the PDB website and type 1DKX in the search box

This will lead you to the same page we got earlier through UniProt.

  - Via the Protein Data Bank by sequence

In lots of cases we only have a sequence of which we would like to find
out if there is structural information. The PDB can be searched using a
sequence as input. Here is the sequence of the C-terminal substrate
binding domain of DnaK:

    DVKDVLLLDVTPLSLGIETMGGVMTTLIAKNTTIPTKHSQVFSTAEDNQSAVTIHVLQGE
    RKRAADNKSLGQFNLDGINPAPRGMPQIEVTFDIDADGILHVSAKDKNSGKEQKITIKAS
    SGLNEDEIQKMVRDAEANAEADRKFEELVQTRNQGDHLLHSTRKQVEEAGDKLPADDKTA
    IESALTALETALKGEDKAAIEAKMQELAQVSQKLMEIAQQQHAQQQTAGADASANNAKDD
    DVVDAEFEEVKDKK

The PDB allows sequence searches through the same search box we used
before.
![Pdbsearchbox_RCSB.png](Pdbsearchbox_RCSB.png "Pdbsearchbox_RCSB.png")

There is also an Advanced Search section, with a Blast/Fasta option in
the Sequence Features section. Please select 'Sequence BLAST/PSI-BLAST'
in the Query type drop down. This method allows you to change some
parameters for the search.

![Blastpdb.png](Blastpdb.png
    "Blastpdb.png")

    Copy and paste the sequence in the ''Sequence'' field and press ''Submit query''.
    You should see the same structures popping up as you saw in the UniProt page of DnaK.

## The PDB file

  - Introduction

A PDB (Protein Data Bank) file is a plain text file that contains the
atom coordinates of a solved 3D structure of a protein or even DNA. Such
coordinate files can be obtained at the Protein Data Bank at
<http://www.rcsb.org/pdb>. Each PDB file has a unique identifier (ID)
consisting of 4 characters, the first one is always a number. Note: It
has been announced that the 4 character code will change in the future
(https://www.wwpdb.org/news/news?year=2017\#5910c8d8d3b1d333029d4ea8).

The PDB file with ID **1DKX** contains the atomic coordinates of the
molecular chaperone (DnaK) from *E
    coli*.

    Go to the PDB website at http://www.rcsb.org/pdb and type 1DKX in the search box and answer these questions mainly by investigating the main page
    and the sequence page of the 1DKX entry.

| How many molecules were solved in this PDB file? What kind of molecules are these (proteins, peptides, DNA, ...)?                   |
| :---------------------------------------------------------------------------------------------------------------------------------- |
| \* Two, called polymers or chains: they are polypeptides (see *Type*) [<file:mol_desc_1DKX.png>](file:mol_desc_1DKX.png "wikilink") |

<table>
<thead>
<tr class="header">
<th style="text-align: left;"><p>Does the structure represent the full protein? If not, how many residues are missing?<br />
<em>Hint: Click on the UniProt KB link in the Sequence tab to see the full sequence.</em></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"><p>* You can go the sequence tab at the top<br />
<a href="file:pdb_seqtab.png" title="wikilink">800px</a></p></td>
</tr>
<tr class="even">
<td style="text-align: left;"><p>* On this page, we can switch between SEQRES view and UniProt view<br />
<a href="file:pdf_uniprotview_button.png" title="wikilink">800px</a></p></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><p>* Investigating the displayed sequence reveals that the first N-terminal 387 residues are missing from the structure.<br />
<a href="file:pdb_firstresiduesmissing_1dkx.png" title="wikilink"><a href="file:pdb_firstresiduesmissing_1dkx.png" class="uri">file:pdb_firstresiduesmissing_1dkx.png</a></a></p></td>
</tr>
<tr class="even">
<td style="text-align: left;"><p>* For further comparison, we need to go to the corresponding uniprot entry and compare with the C-terminal residues.<br />
<a href="file:uniprotlink_from_pdb.png" title="wikilink"><a href="file:uniprotlink_from_pdb.png" class="uri">file:uniprotlink_from_pdb.png</a></a></p></td>
</tr>
<tr class="odd">
<td style="text-align: left;"><p>* Summary: a large chunk of the N-terminus is missing from the structure, the C-terminus is virtually complete.</p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th style="text-align: left;"><p>Was this structure solved by X-Ray or NMR?</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"><p>* X-RAY diffraction, as shown by Experimental Details:<br />
<a href="file:pdb_xraydiffraction_1dkx.png" title="wikilink"><a href="file:pdb_xraydiffraction_1dkx.png" class="uri">file:pdb_xraydiffraction_1dkx.png</a></a></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th style="text-align: left;"><p>What is the atomic resolution and R-factor?</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td style="text-align: left;"><p>* Atomic resolution: 2.00 Ångstrom and R-factor of 0.206.<br />
<a href="file:pdb_expdetails_1dkx.png" title="wikilink"><a href="file:pdb_expdetails_1dkx.png" class="uri">file:pdb_expdetails_1dkx.png</a></a></p></td>
</tr>
</tbody>
</table>


;Downloading the structure The file that holds the 3D coordinates can be
downloaded by clicking on *Download files* in the top right corner and
then choosing *PDB file (text)*. For convenience, save this file on your
Desktop. The filename is the 4-character unique PDB ID.

![Pdbdownloadfile1.png](Pdbdownloadfile1.png
    "Pdbdownloadfile1.png")

    Open this file with a text editor, e.g. WordPad is an excellent tool for that.
    Do you see the different sections in the PDB file? Analyse some ATOM lines and try to explain what kind of data is in each column.

Additional exercises on searching PDB can be found on [the basic
bioinformatics exercises
page](http://wiki.bits.vib.be/index.php/Exercises_on_Protein_Structure).