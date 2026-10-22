# Data source and sample

## Source

The project context identifies the source as the **DataCo Smart Supply Chain** dataset, covering orders from 2015 through January 2018.

- Kaggle dataset page: [DataCo Smart Supply Chain for Big Data Analysis](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)
- Upstream Mendeley Data version 5: [DataCo Smart Supply Chain for Big Data Analysis](https://data.mendeley.com/datasets/8gx2fvg2k6/5), DOI [10.17632/8gx2fvg2k6.5](https://doi.org/10.17632/8gx2fvg2k6.5)
- Upstream dataset authors: Fabian Constante, Fernando Silva, and António Pereira.
- Upstream Mendeley version 5 license: CC BY 4.0, according to the source record.

<!-- TODO: à compléter — verify and record the license and attribution metadata for the specific Kaggle copy used by this project. -->

## Files included here

- `sample/DescriptionDataCoSupplyChain.csv`: the small accompanying description file found with the source data.
- `sample/orders_sample.csv`: a 100-row sample derived from the source orders, retaining selected business fields and omitting customer names, email addresses, passwords, street addresses, postal codes, and coordinates.

The full source CSV and tokenized access-log file are not included. The order CSV is approximately 91 MiB and includes personal fields; the access log is similarly large and is not required to inspect this portfolio report. The sample is for structure and demonstration only, not a substitute for the complete dataset.

## Download and refresh

Download the source files from the linked dataset page only after reviewing its license and terms. Place the full order CSV in a local `data/raw/` folder (ignored by Git), then open the PBIX and update the `Stg_DataCo` Power Query file path to that local copy before refreshing.

The PBIX currently contains a machine-specific source path. Refreshing the report on another computer therefore requires changing that path. Do not add raw personal fields or access logs to a public repository.
