# Description

Connecting SDC's M&A database to Compustat requires `gvkey`'s for both the acquirer and target (if they are traded/public). [Gordon Phillips](http://www.tuck.dartmouth.edu/faculty/faculty-directory/gordon-phillips) and [Alexei Zhdanov](https://sites.psu.edu/auz15/) ([RFS, 2013](https://academic.oup.com/rfs/article/26/1/34/1593273)) created the first major mapping between firms in SDC and Compustat using a combination of name and date matching.  Gaps where filled in using [this website](http://makeresearchgreatagain.com/data_search/) that replicates the `gvkey` search in WRDS.  The data was used in [Ewens, Peters and Wang (2018)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3287437). Either [myself](https://ewens.caltech.edu/) or a research assistant searched all M&As deals from 1996-2016 that did not have a `gvkey` in the Phillips and Zhdanov data, comparing names and dates by hand.

# Data

[The data connecting SDC deal number to gvkeys](https://github.com/michaelewens/sdc_ma_gvkeys/blob/master/dealnum_to_gvkey.csv) is in csv form with the following structure:

`(DealNumber, tgvkey, agvkey)`

where 

* `DealNumber`: SDC identifier for deals.  
* `agvkey`: the acquirer gvkey (can be missing)
* `tgvkey`: the target gvkey (can be missing)

Note that this includes all deals where we could find a gvkey for either the acquirer or target.  Basic statistics as of Nov. 20th, 2018:

* 100,454 deals with `agvkey`
* 50,248 deals with `tgveky`
* 22,259 with both `agvkey` and `tgveky`

## Company-level match using CUSIP

[The second file](https://github.com/michaelewens/SDC-to-Compustat-Mapping/blob/master/sdc_compustat_cusip_gvkey.csv) was built by taking all the SDC name-CUSIP pairs without a match in the main repo's mapping (above) and comparing them to all Compustat-GVKEY pairs. The match is then done on SDC names-Compustat names. Note that this is a time-invariant mapping based entirely on company names (so there can be multiple SDC CUSIPs to one Compustat GVKEY as a company changes its CUSIP over time). From Daniel Yang (Ohio State).

# Updates

Stay tuned (i.e., watch or star this repo.) for updates.  Any errors or fill-ins, please email michael.ewens@gmail.com.

# Citations

```Latex
@article{phillips2013r,
  title={R\&D and the Incentives from Merger and Acquisition Activity},
  author={Phillips, Gordon M and Zhdanov, Alexei},
  journal={The Review of Financial Studies},
  volume={26},
  number={1},
  pages={34--78},
  year={2013},
  publisher={Society for Financial Studies}
  }
```

and

```Latex
@article{ewensPetersWang2018,
 title={Acquisition prices and the measurement of intangible capital},
 author={Ewens, Michael and Peters, Ryan and Wang, Sean},
 journal={Working Paper}
 year={2018}
 }
```
