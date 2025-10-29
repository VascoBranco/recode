**ANNOTATION GUIDELINES WITH INCEPTION**

# 1. INTRODUCTION 

First let's have a brief introduction about the entities that are involved in tagging any scientific journal or publication for the purpose of identifying useful trait information about a species. The annotations are based on measurements of trait information of a species and its secondary information. These bits of information in every measurement can be classified in following categories:
-   **ETS-Term** The Ecological Traitdata.
-   **NER Tags** The corresponding Tag applied in the document.
-   **IOB Tags** The generated tags according to Conll structure.
The ETS-fields are annotated using NER-Tags that are listed in Table1

**TABLE 1: ANNOTATION ENTITY TAGS AND DEFINITIONS**
 <table>
  <tr>
    <th>ETS-Term</th>
    <th>NER Tags</th>
    <th>IOB Tags</th>
    <th>DEFINITION<br>(See: https://terminologies.gfbio.org/terms/ets/pages/)</th>
    <th>EXAMPLES</th>
  </tr>
  <tr>
    <td>verbatimScientificName</td>
    <td>Species</td>
    <td>B-Taxon I-Taxon</td>
    <td>Original character string provided as species name or taxon identifier by the data provider.</td>
    <td>"<b>Silometopus ambiguus</b> (Figs 10-12): BELGIUM: West-Vlaanderen: Knokke, Zwin Nature Reserve (51.367°N,3.367°E, 2 m a.s.l.), 2 males, 6 females, pitfall traps in salt marsh, 2.–16. Jun. 2014, J. Van Keer leg., R. Bosmans coll.";<br>
     “Pan paniscus”; “Arachnida”;  “C. planirostris”; “L. brasiliense”</td>
  </tr>
  <tr>
    <td>verbatimLocality</td>
    <td>Loc</td>
    <td>B-Loc,I-Loc</td>
    <td>The specific description of a place.</td>
    <td>"Silometopus ambiguus (Figs 10-12): <b>BELGIUM: West-Vlaanderen: Knokke, Zwin Nature Reserve</b> (51.367°N,3.367°E, 2 m a.s.l.), 2 males, 6 females, pitfall traps in salt marsh, 2.–16. Jun. 2014, J. Van Keer leg., R. Bosmans coll."; <br> 
     “Florida”; “Germany”</td>
  </tr>
  <tr>
    <td></td>
    <td>LocDate</td>
    <td></td>
    <td>The date at which a Species was observed in a specific location (LOC)</td>
    <td>“Type material: Holotype: Male collected from banana agro-ecosystems near Raver (21.25 ° N, 76.03° E), Distt. Jalgaon, Maharashtra, India, <b>21-25 December 2012</b>, Seema Keswani, deposited at Arachnology Museum, Forest Training Institute, Chikhaldara, Maharashtra-India”; <br> “10.09.2009”; “3 March 2022”; “24.IV.2009” </td>
  </tr>
  <tr>
    <td>verbatimCoordinateSystem</td>
    <td>CoordSys</td>
    <td>B-CoordSys</td>
    <td>See: https://dwc.tdwg.org/terms/#dwc:verbatimCoordinateSystem & <br> http://wiki.gis.com/wiki/index.php/Datum_(geodesy)#List_of_Datums</td> 
    <td>decimal degrees, degrees decimal minutes, degrees minutes seconds, UTM, EPSG:4326, WGS84, NAD27, Campo Inchauspe, European 1950, Clarke 1866
</td>
  </tr>
  <tr>
    <td>verbatimCoordinates</td>
    <td>Coord</td>
    <td>B-Coord I-Coord</td>
    <td>See: https://dwc.tdwg.org/terms/#dwc:verbatimCoordinates<br><br>
Some papers will have coordinates provided by the authors with greater precision than checking a gazetteer for locations. Could be in several datums and coord systems.</td>
    <td>"Silometopus ambiguus (Figs 10-12): BELGIUM: West-Vlaanderen: Knokke, Zwin Nature Reserve (<b>51.367°N,3.367°E</b>, 2 m a.s.l.), 2 males, 6 females, pitfall traps in salt marsh, 2.–16. Jun. 2014, J. Van Keer leg., R. Bosmans coll."; <br>
     (39.8210N 2.7951E); (-41.0983, -121.1761); 17T 630084 4833438; 41 05 54S 121 05 34W; -77.508333, 164.754167; 77° 30.5' S, 164° 45.25' E; 77° 30' 29.9988" S, 164° 45' 15.0012"; E -1314485.732632, 358267.239976</td>
  </tr>
  <tr>
    <td>verbatimTraitName</td>
    <td>Trait</td>
    <td>B-Trait, I-Trait</td>
    <td>Original character string provided as trait label by the data provider. This may include abbreviations of trait names.</td>
    <td>“Tail length”, “greatest length of skull”, “GLS”</td>
  </tr>
  <tr>
    <td>verbatimTraitValue</td>
    <td>TraitVal</td>
    <td>B-TrVal, I-TrVal</td>
    <td>Measurement trait values: Trait Value can be a numerical measurement (56-57, 12). Describing the ranges of calculated data including min, max value and number of specimens. This is a very abstract form of an entity as measurement ranges can hold mean, SD, ranges (min, max) which cannot be separately tagged. So it should be tagged as a compound.</td>
    <td>"Description. Female (Type 1): Total length <b>4.85-5.29</b>b> (LG01-03, n=3). One specimen (LG01) measured: body length <b>5.20</b>b>; cephalothorax <b>2.21</b>b> long, <b>2.17</b>b> wide; abdomen <b>2.99</b>b> long, <b>2.48</b>b> wide (Fig. 1)." <br>
     33.57 (31.36-36.56, 50); 29.5-34.6; 6.5, 7.5; 12.7 ± 0.2</td>
  </tr>
  <tr>
    <td>verbatimTraitUnit</td>
    <td>Unit</td>
    <td>B-Unit</td>
    <td>The unit value of the measured trait. These values should only be tagged if they are describing the unit of the trait value measurement. Irrelevant data units should be avoided.</td>
    <td>"g"; "mm"; "cm"; "kg"; "inches"; "15 <b>in</b>b>"</td>
  </tr>
  <tr>
    <td>individualCount</td>
    <td>Count</td>
    <td>B-Count</td>
    <td>Number of specimens. It must be a numerical value either in number or textual form. It should be only tagged as mentioned separately in examples. If they are part of the range then do not tag them separately as (23-25,13) this is part of the range now.</td>
   <td>
   "Silometopus ambiguus (Figs 10-12): BELGIUM: West-Vlaanderen: Knokke, Zwin Nature Reserve (51.367°N,3.367°E, 2 m a.s.l.), 2 males, 6 females, pitfall traps in salt marsh, 2.–16. Jun. 2014, J. Van Keer leg., R. Bosmans coll."; <br>
"<b>15</b> males";  "<b>One</b> female, <b>three</b> of the specimens."; "<b>10</b> females."; "Specimen of <b>15</b> organisms"; "n = <b>16</b>"</td>
  </tr>
  <tr>
    <td>StatisticalMethod</td>
    <td>Stat</td>
    <td>B-Stat,I-Stat</td>
    <td>For aggregated measures, the method for data aggregation or averaging as well as the variation or range.</td>
    <td>"In Brazil (Vizotto and Taddei 1976), <b>means SD (mm; range, coefficient of variation)</b>b> for 15 males and 15 females, respectively."; <br>
"means (mm; ranges)"; "SD (mm; range, coefficient of variation)"</td>
  </tr>
    <tr>
    <td>sex</td>
    <td>Sex</td>
    <td>B-Sex</td>
    <td>The sex of the biological individual(s). This should imply sexes whose trait data is given. and can be either a noun or a gender symbol, ♂, ♀, ☿.</td>
    <td>“male”, “female”, “unknown”, “hermaphrodite”, “2 ♂♂”, “m”, “f”, “mf”, “mm”, “ff”</td>
  </tr>
    <tr>
    <td>lifeStage</td>
    <td>LStage</td>
    <td>B-LStage,I-Lstage
</td>
    <td>The age class or life stage of the biological individual(s).</td>
    <td>“juvenile”, “juv.”, “j.”, “jj.”, “subadult”, “adult”, “ad.”, “egg”, “larva”, “pupa”, “spiderling”, “instar”, “nymph”.</td>
  </tr>
    <tr>
    <td>measurementRemarks</td>
    <td>Ref</td>
    <td>B-Ref, I-Ref</td>
    <td>A citation that references the measurements of trait data. There can be many citations in the document. But only the ones that relate to providing trait information should be tagged.</td>
    <td><b>Gimenez and Giannini (2016)</b> provided means (mm; ranges) of craniodental measurements. <b>Peters et al. (2002)</b> reported the following means (mm; ranges) for six females and 12 males, respectively. In Brazil (<b>Vizotto and Taddei 1976</b>), means SD (mm; range, coefficient of variation) for 15 males and 15 females, respectively</td>
  </tr>
    <tr>
    <td>measurementDeterminedDate</td>
    <td>Date</td>
    <td>B-Date,I-Date</td>
    <td>The date on which the MeasurementOrFact was made.</td>
    <td>“1900”, “April 1900”, “12 Feb 1900”, “12.02.1900”, “02-12-1900”</td>
  </tr>
</table> 

**NOTE:**
You will need this table to confirm whether the annotations are correctly done or not. These tags are saved in the INCEpTION
project template which will be provided as a starter framework to annotate any document. By selecting the text and then selecting the
above mention tag the annotation will be done. Some of the tags may be pre-annotated and you can scrutinise them by deleting and updating
with the correct one, where required.

# 2. GUIDELINES FOR ANNOTATIONS
## 2.1 MATERIAL NEEDED
-   **Computer.** Most OS' should be fine. Needs to be able to run your choice of web browser.
-   **External mouse.** One bug in INCEpTION can only be bypassed if you have an external mouse with a mouse wheel.

## 2.2 HOW TO ANNOTATE IN INCEPTION

1.  **Locate relevant data**

Read the document. Identify only those sections where either trait measurement or occurrence of species are specified.
Measurements often included an animal's phenotype (head circumference, body length, weight, etc) and their secondary information (e.g: life stage, count of Individuals for those measurements, etc).

**Example of trait measurement from data:**

> In Brazil (Vizotto and Taddei 1976) , means + SD (mm; range,
> coefficient of variation) for 15 males and 15 females, respectively,
> were: head-body length, 55.7 + 0.5 (51.0-59.0 , 3.3) , 52.9 + 0.3 (
> 50.5-54.5 , 2.4) ;
>
> []{.mark}
>
> **[Extracted labels of above mentioned traits as described in]{.mark}
> [TABLE 1 ANNOTATION ENTITY TAGS AND DEFINITIONS]{.underline}.**

  **[Text]{.mark}**                  | **[Tag]{.mark}**
  -----------------------------------|-----------------------------------
  Vizotto and Taddei 1976            | [Ref]{.mark}
  means + SD                         | [Stat]{.mark}
  mm                                 | [Unit]{.mark}
  range                              | [Stat]{.mark}
  coefficient of variation           | [Stat]{.mark}
  15                                 | [Count]{.mark}
  males                              | [Sex]{.mark}
  15                                 | [Count]{.mark}
  females                            | [Sex]{.mark}
  head-body length                   | [Trait]{.mark}
  55.7 + 0.5                         | [TraitVal]{.mark}
  51.0-59.0                          | [TraitVal]{.mark}
  3.3                                | [TraitVal]{.mark}
  52.9 + 0.3                         | [TraitVal]{.mark}
  50.5-54.5                          | [TraitVal]{.mark}
  2.4                                | [TraitVal]{.mark}
  -----------------------------------------------------------------------

> []{.mark}

2.  **[Annotate an entity]{.mark}**

> []{.mark}

a.  [Select the text to be annotated with mouse-1. Only select the
    > relevant text.]{.mark} Do not include unnecessary blank or
    > whitespace, parenthesis, commas unless they are part of a tag.

b.  Keep the tag selected and then annotate the tag from the combo box
    > **value** given on the right side.

Example:

> Here in this example condylobasal length has been selected by the
> user. Only the tag name is highlighted, leaving the comma or any other
> space unselected. If the trait name is already highlighted then
> confirm that tag is correctly placed. If not in both cases switch to
> tag the specific genre.

Fig 1: Select Text

![Fig. 1](img/guidelines_1.jpg)

Fig 2: Select Text

![Fig. 2](img/guidelines_2.jpg)

Fig 3: Tag the Entity

![Fig. 3](img/guidelines_3.jpg)

**NOTE:**

> If you think you've made a mistake, you can delete any named entity or
> relation by selecting them and pressing **Delete.**

## 2.3 PREVIEW OF ANNOTATED DATA

An annotated measurement before and after annotation will look like
this:

> Ranges of skull measurements (mm; n) of specimens from Argentina
> (Barquez et al. 1999, 2011; Idoeta et al. 2012) were: greatest length
> of skull, 13.30-17.80 (13); condylobasal length, 14.78-16.74 (12);
> least interorbital breadth, 6.18-7.18 (13); zygomatic breadth,
> 10.56-11.58 (10); postorbital constriction, 3.91-4.60 (13); breadth of
> braincase, 7.68-8.30 (13); length of maxillary toothrow, 5.89-7.00
> (13); palatal length, 6.16-7.10 (13); mastoidal breadth, 9.68-11.50
> (10); length of mandibular toothrow, 6.30-7.50 (13); length of
> mandible, 11.69-13.58 (12); width across canines, 4.07-5.0 (13); width
> across molars 6.82-8.0 (13).

Fig4: Annotated in Inception

![Fig. 4](img/guidelines_4.jpg)

## 2.4 EXAMPLES & CAUTIONS FOR ANNOTATORS

> There are some rules and norms that have to be followed while
> annotating each entity. This is to make sure they are consistent for
> the follow-up analysis. There's quite a few but they're not complex.
> Repetition while handling multiple scenarios and data variances in
> publication formats will see you quickly become familiar with them..
> Here's a few of them as per each tag:

### 2.4.1 Stat (Statistical Method)

> Stat measures indicate the numerical or statistical method of
> measurement. This may include ranges, means with SD (Standard
> Deviation), Coefficient of variation etc. Each statistical method
> should be independently tagged as a 'Stat' method, only if there is a
> resultant value present.
>
> ***Example 1.* Ranges:** A range is the stat measure which is related
> to the range of any trait value. In the example below: only the ranges
> of the trait values are provided. The range values can be found later
> as 54-63, 24-30 etc. So the statistical measure as **ranges** is
> tagged.

![Fig. 5](img/guidelines_5.jpg)

Fig5: Range as Stat

> ***Example 2.* Means and Range:** In this example two statistical
> measures are provided with relevant data i-e **means** and **range**.
> Therefore they are separately tagged. Later their corresponding trait
> values will also be separately tagged.

**Fig6: Means and Range as Stat**

![Fig. 6](img/guidelines_6.jpg)

***Example 3.* Means+-SD, range and Coefficient of Variation:** In
this example three statistical measures can be identified.) **means**
is **coupled with SD** and is taken as one measurement. **Range** and
**coefficient of variation** are other two stat measure tags.

**Fig7: Means +-SD,range and Coefficient of Variation as Stat**

 ![Fig. 7](img/guidelines_7.jpg)

 ***Example 4.* means+-SD, range:** In this example two stat measures
 means+-SD and range are separately tagged.

**Fig8: Means +-SD,range as Stat**

![Fig. 8](img/guidelines_8.jpg)

### 2.4.2 Species (verbatimScientificName)

> A species' scientific name will almost always be written in two
> specific ways: as a binomial name of genus and specific name (e.g.
> *Macrothele calpeiana*) or as a binomial of genus abbreviation and
> specific name (*M. calpeiana*), the latter being used only after the
> non-abbreviated binomial has already been used in the paper. In some
> taxa some species might go further and have a sub-species name after
> the binomial (e.g: *Panthera tigris sumatrae, P. tigris tigris*).

Example

**Fig9 : Species Tag**

![Fig. 9](img/guidelines_9.jpg)

### 2.4.3 Trait and TraitVal (verbatimTraitName & verbatimTraitVal)

The trait names and their values are the most important named entities
to annotate and as such if you have annotated a trait value you MUST
annotate a species name and a trait name. Secondly, if a TraitName is
not explicit in text - for example, if you have a measurement of a
tail but what measurement it is (i.e: circumference, length, etc.) is
not specified - then you must annotate it anyway to be interpreted in
posteriority.

Example

The Trait Names tagged as **Trait** should have their respective
TraitValues as TraitVal in the measurement. Consider this example,
where the trait names include a whole expression including "length
of", "breadth of", "height of", etc. These components are essential
information comprising the traitname.

**Fig10: Trait as Tag**
![Fig. 10](img/guidelines_10.jpg)

The trait names in the above fig are boxed green. You can see that the
whole trait with its measured terms are included for tag.

***Example 1.*** Next we are interested in Trait Values which could be
measured by stated stat values as means, ranges etc. In this example
the Trait Values are based on Stat values means and ranges already
mentioned as Stat tags. The Trait Values are tagged accordingly.
Additionally, consider that occasionally the trait name might be
separated. In these situations annotate the rightmost term, to be
interpreted in posteriority.

Fig11: TraitVal as Tag

![Fig. 11](img/guidelines_11.jpg)

> ***Example 2.*** In this example, the authors have chosen to organise
> their measurements by body segment, creating sentences starting with a
> segment like "prosoma" and then specifying the measurement. Both
> "long" and "wide" refer to a measurement of the prosoma and could be
> rewritten as "length of prosoma" and "width of prosoma", for example.

Fig12: TraitVal as Tag

![Fig. 12](img/guidelines_12.jpg)

### 2.4.4 Ref (References)

> When annotating, do not include parenthesis in the tagging except if
> they're part of the reference's year. E.g: tagging an in-text citation
> as "Author (2020)" is correct, tagging "(Author A 2020, Author B 2021,
> Author C 2022)" as three separate instances of "(Author A 2020" ,
> "Author B 2021" and "Author C 2022)" is incorrect as they should be
> annotated as "Author A 2020", "Author B 2021" and "Author C 2022".

### 2.4.5 Loc (LocationofTaxon)

> Sometimes a trait value or species is attributed to a location that is
> in fact a continuous string of location organisational units, such as
> "Portugal, Lisbon, Campo Grande", which are country, district and
> parish, respectively. In these situations the entire string should be
> annotated as a single location.

Fig13: Loc as Tag

![Fig. 13](img/guidelines_13.jpg)

### 2.4.6 Count (individualCount)

> ***Example 1.*** Counts are the integer numbers of individuals
> associated with a given value **only** and do not include the common
> mathematical notation of "n =" denoting sample size.

Fig14: Count as Tag

![Fig. 14](img/guidelines_14.jpg)

# 3. RELATIONS ANNOTATION GUIDELINES

> Relations establish how the named entities relate to each other. Most
> are made particularly via TraitValue. A trait value is the core
> measurement value that is linked to the rest of its dependent
> attributes. A trait value describes one measurement with a complete
> set of values linked through it. Relations are annotated when a
> complete annotation process is done on the document or after a
> particular set of annotations are completed that can constitute
> relations. However, you should always consult Tables 2 and 3 at the
> **end of this section**.
>
> When you create a relation, select the annotated term. Keep it
> selected. Drag the mouse button, an arc will emerge. Drop the arc to
> the entity you want to link with, e.g Trait. **WARNING**: in the
> current version of INCEpTION there is a graphical bug that may stop
> you from creating relations between two terms very distant between
> each other in the text. The "arrow" it creates will disappear but if
> you scroll down you'll still be able to create the relation. However,
> this only works with external mice, it will not work with laptop
> trackpads!
>
Fig 15 : Create Relation between TraitVal and Trait.

![Fig. 15](img/guidelines_15.jpg)

> Once the link is established, on the right side the information will
> be displayed. Confirm the relations are correctly done. **From** and
> **To** tabs will show the values i-e TraitVal and Trait in this case.
> From the meas_prop drop down select the appropriate relation
> meas_trait in this case. As TraitVal is linked to Trait its meas_trait
> is selected.
>
 Fig 16 : Relation Values between TraitVal and Trait.

![Fig. 16](img/guidelines_16.jpg)

> The relation **meas_trait** will be shown between the entities.

Fig 17 : Relation between TraitVal and Trait.

![Fig. 17](img/guidelines_17.jpg)

Likewise, create relations between one particular TraitVal with all its
value. In Fig15 TraitVal (15.9) has to be linked with its attributes :
  Label                              | Term
  -----------------------------------|-----------------------------------
  Trait                              | **greatest length of skull**
  Sex                                | **females**                    
  Count                              | **six**
  Stat                               | **means**
  Unit                               | **mm**
  Ref                                | **Peters et al. (2002)**
  -----------------------------------------------------------------------

Each Traitval should be linked with every bit of information that makes
its measurement complete. There could be repetitive links to the same
entities for such.

## 3.1 Caution for Relations Making

Once the annotation process is complete, please save it in the
webanno.tsv format. You can upload the file later as well in case you
think you've forgotten something. Regardless, if you're using the online
browser version of INCEpTION any changes you make should be
automatically saved. The status of the annotations can be restored if
any problem arises.

### Relations

All relations are based on TraitVal. The source or the base of all
relations is TraitVal. With a trait value you have to link all the rest
of corresponding tags.

### Occurences

A bit trickier but not by much. The starting term is Species with only
one exception, GIVEN COORDS:

![Fig. 18](img/guidelines_18.jpg)

TABLE 2: RELATION TABLE BETWEEN ENTITIES. TRAITS
 <table>
  <tr>
    <th>NAME</th>
    <th>ENTITY 1</th>
    <th>ENTITY 2</th>
    <th>RELATION</th>
    <th>REMARKS</th>
  </tr>
  <tr>
    <th colspan="5">MEASUREMENT RELATIONS</th>
  </tr>
  <tr>
    <td>meas_Species</td>
    <td>TraitVal</td>
    <td>Species</td>
    <td>verbatimTraitValue–verbatimScientificName</td>
    <td>Trait Value of Species linked with Species Name</td>
  </tr>
  <tr>
    <td>meas_Trait</td>
    <td>TraitVal</td>
    <td>Trait</td>
    <td>verbatimTraitValue–verbatimTraitName</td>
    <td>Trait Value linked with Trait Name</td>
  </tr>
  <tr>
    <td>meas_Unit</td>
    <td>TraitVal</td>
    <td>Unit</td>
    <td>verbatimTraitValue–verbatimTraitUnit</td>
    <td>Trait Value linked with its Trait Unit</td>
  </tr>
  <tr>
    <td>meas_Stat</td>
    <td>TraitVal</td>
    <td>Stat</td>
    <td>verbatimTraitValue–StatisticalMethod</td>
    <td>Trait Value linked with Statistical Methods (e.g range, means+-SD, SD, coefficient of variations)</td>
  </tr>
  <tr>
    <td>meas_Loc</td>
    <td>TraitVal</td>
    <td>Loc</td>
    <td>verbatimTraitValue–verbatimLocality</td>
    <td>The Location where the measurements were made is linked with TraitValue.</td>
  </tr>
  <tr>
    <td>meas_Count</td>
    <td>TraitVal</td>
    <td>Count</td>
    <td>verbatimTraitValue–individualCount</td>
    <td> </td>
  </tr>
  <tr>
    <td>meas_Sex</td>
    <td>TraitVal</td>
    <td>Sex</td>
    <td>verbatimTraitValue–Sex</td>
    <td> </td>
  </tr>
  <tr>
    <td>meas_LStage</td>
    <td>TraitVal</td>
    <td>LStage</td>
    <td>verbatimTraitValue–LifeStage</td>
    <td> </td>
  </tr>
  <tr>
    <td>meas_Ref</td>
    <td>TraitVal</td>
    <td>Ref</td>
    <td>verbatimTraitValue–References</td>
    <td> </td>
  </tr>
  <tr>
    <td>meas_Date</td>
    <td>TraitVal</td>
    <td>Date</td>
    <td>verbatimTraitValue–measurementDeterminedDate</td>
    <td> </td>
  </tr>
</table> 

TABLE 3: RELATION TABLE BETWEEN ENTITIES. OCCURENCES.
 <table>
  <tr>
    <th>NAME</th>
    <th>ENTITY 1</th>
    <th>ENTITY 2</th>
    <th>RELATION</th>
    <th>REMARKS</th>
  </tr>
  <tr>
    <th colspan="5">SPECIES LOCATION RELATION</th>
  </tr>
  <tr>
    <td>OCCURS</td>
    <td>Species</td>
    <td>Loc / Coord</td>
    <td>Species→Loc</td>
    <td>Occurrence of a species at any location. If unpaired, i.e.: is described only with a set of coordinates, Coord is the end term, otherwise Loc takes precedence.</td>
  </tr>
  <tr>
    <td>DATE</td>
    <td>Species</td>
    <td>LocDate</td>
    <td>Species→LocDate (One-Many)</td>
    <td> </td>
  </tr>
  <tr>
    <td>GIVEN COORDS</td>
    <td>Loc</td>
    <td>Coord</td>
    <td>Loc→Coord (One-One)</td>
    <td>If a location is described with both a Loc and Coord entities, this relation is established between them.</td>
  </tr>
</table> 

# 4. End notes

If you can think of anything specific please suggest it, but we think
this document should have everything important. The relations are a last
easy step, the most challenging part are the entities. If you have any
questions, please reach me at vasco.branco@helsinki.fi.
