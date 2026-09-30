# RiskResources

Reference tables for human health risk screening, kept at fixed file names so
the **Env Data Tools** Excel add-in can copy them into a workbook with one
click (**Env Data Tools > Reference > Reference Tables**).

| File | What it is | Sheets |
|---|---|---|
| `RSL_THQ0.1.xlsx` | EPA Regional Screening Levels, target cancer risk 1E-06 and target hazard quotient 0.1 | Summary, Res Soil, Res Tapwater, Res Air, Soil to GW, Ind Soil, Ind Air, Parameters, Subchronic - each ending in the release (`1124` = November 2024) |
| `ATSDR_MRLs.xlsx` | ATSDR Minimal Risk Levels | `ATSDR MRLs 0626` |
| `IRIS_RfD.xlsx` | IRIS oral reference doses | `IRIS RfD 0926` |
| `IRIS_RfC.xlsx` | IRIS inhalation reference concentrations | `IRIS RfC 0926` |
| `PPRTV.xlsx` | EPA Provisional Peer-Reviewed Toxicity Values: each chemical's RfD and RfC, weight of evidence, and links to its assessment and IRIS page | `PPRTV 0926` |

`tables.txt` lists the files the add-in offers, one per line:
`the name shown in Excel | the file name`. Adding a table is adding its file
and one line there; the add-in needs no update.

## Updating a table

1. Download the new release from the source.
2. Replace the file here **under the same file name**.
3. Name each sheet with the release on the end, as EPA does: `Res Soil 0525`,
   `ATSDR MRLs 0626` (month and year, `MMYY`). The add-in copies sheets by the
   names in the file, so the release travels with the sheet.
4. Commit with a message naming the release, such as `RSL May 2025`. The
   add-in records the file's last commit on each sheet it copies, so a
   workbook shows which release it used. Earlier releases stay in this
   repo's history.

## Sources

- RSLs: <https://www.epa.gov/risk/regional-screening-levels-rsls-generic-tables>
- ATSDR MRLs: <https://wwwn.cdc.gov/TSP/MRLS/mrlsListing.aspx>
- IRIS: <https://iris.epa.gov/AtoZ/>
- PPRTVs: <https://www.epa.gov/pprtv/provisional-peer-reviewed-toxicity-values-pprtvs-assessments>

The ATSDR file's MRL Value and Units columns were split from MRL+Units by
formula in the original download; here they are plain values (the MRL as a
number), so the file works in any version of Excel.

EPA's PPRTV list downloads as a web page table named `.xls`. Here it is a real
workbook: each RfD and RfC is kept as listed (`6 x 10^-3 mg/m3` - the exponent
was a superscript on EPA's page), with its number (0.006) and units in their
own columns, blank where EPA says *Not available* or *See IRIS*. The chemical,
assessment and IRIS links still work. EPA lists Methyl Acrylate's RfC in
mg/kg-day; it is kept as listed.
