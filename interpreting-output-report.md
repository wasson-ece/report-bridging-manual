# Generating & Interpreting Output Report

### Generating Report

Once the user has configured the software and selected two appropriate report files, the `EXPORT REPORT` button fixed to the bottom right corner of the application window will no longer be disabled. Click it to generate a report. Upon success, a status message will appear informing the user of success or failure.

### Location

The resultant report will be stored in the user defined directory \(see [configuration](configuration.md#file-options)\) and with a `.csv` extension. 

### Format

The output report is broken into three sections: the header, which describes the output component attributes; 6 lines of metadata; and output components. Each line is delimited by a newline character `\n`, and each field within a line is delimited by a comma `,`. String values are always wrapped in quotes \(e.g. `"some-field"`\). This avoids ambiguity in field delimitation for fields which may contain commas, such as analyte names \(e.g. `"1,1,3-trimethylcyclohexane"`\). 

#### Header

The 1st line in the file contains the header information, and describes the three columns of output component attributes: `Analyte`, `Concentration (mol %)`, and `Normalized Concentration (mol %)`

#### Metadata

The 2nd - 7th lines collate metadata taken from user configuration, the input DHA report, and input ChemStation report. The format is in CSV `Field, Value` pairs. The values are as follows:

1. `"ChemStation Report File", "path/to/chem-station.xml"`
2. `"DHA Report File", "path/to/dha-ascii-report.ASC"`
3. `"ChemStation Injection Date Time", "iso-8601-format-date"`
4. `"DHA Injection Date Time", "iso-8601-format-date"`
5. `"ChemStation Sample Name", "name-of-sample"`
6. `"DHA Sample Name", "name-of-sample"`

#### Body

The 8th line to the end of the file are a list of components in the format described by the [header](interpreting-output-report.md#header) section. **The component list has no guaranteed order. The user may not assume that a given component will appear on a given line for every output report.** Components are generally ordered alphabetically, but as the input report parameters may change \(see the [configuration ](configuration.md)section\), some components may be ignored, extra components may appear, etc. In general, reference components by their name, not the line they happen to be on for a particular report output.

#### Notes

The generated report format is technically not standard CSV format due to the metadata fields [discussed above](interpreting-output-report.md#metadata). **If the user wishes to apply a standard CSV parsing routine to the output report, the user** _**must**_ **remove lines 2 - 7 from the report.** Failing to remove the non-standard metadata lines could cause in unexpected results.



