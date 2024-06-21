# Description

Connecting SDC's M&A database to Compustat requires `gvkey`'s for both the acquirer and target (if they are traded/public). [Gordon Phillips](http://www.tuck.dartmouth.edu/faculty/faculty-directory/gordon-phillips) and [Alexei Zhdanov](https://sites.psu.edu/auz15/) ([RFS, 2013](https://academic.oup.com/rfs/article/26/1/34/1593273)) created the first major mapping between firms in SDC and Compustat using a combination of name and date matching.  Gaps were filled in using a fuzzy string search aided by manual checks that replicates the `gvkey` search in WRDS.  The data was used in [Ewens, Peters and Wang (2024)](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3287437). Either [myself](https://ewens.caltech.edu/) or a research assistant searched all M&As  deals from 1976-2024 with a public target or acquirer that did not have a `gvkey` in the Phillips and Zhdanov data, comparing names and dates by hand after a fuzzy merge.

# Data

[The data connecting SDC deal number to gvkeys](https://github.com/michaelewens/sdc_ma_gvkeys/blob/master/dealnum_to_gvkey.csv) is in csv form with the following structure:

`(DealNumber, tgvkey, agvkey, source)`

where 

* `DealNumber`: SDC identifier for deals.  
* `agvkey`: the acquirer gvkey (can be missing)
* `tgvkey`: the target gvkey (can be missing)
* `source`: indicates a new merge from a June 2024 merge of SDC and Compustat, 0 or 1. 

Note that this includes all deals where we could find a gvkey for the acquirer or target.  Basic statistics as of June 21, 2024:

* 100,454 deals with `agvkey`
* 50,248 deals with `tgveky`
* 22,259 with both `agvkey` and `tgveky`

## Company-level match using CUSIP

This file was removed because [WRDS](https://wrds-www.wharton.upenn.edu/login/?next=/pages/get-data/center-research-security-prices-crsp/annual-update/crspcompustat-merged/compustat-crsp-link/) provides this already and SDC has a CUSIP. 

# Updates

Stay tuned (i.e., watch or star this repo.) for updates.  For any errors or fill-ins, please email michael.ewens@gmail.com.

# Citations

```Latex
@article{ewensPetersWang2018,
 title={Measuring Intangible Capital with Market Prices},
 author={Ewens, Michael and Peters, Ryan and Wang, Sean},
 journal={Management Science}
 year={2024}
 }
```
and 
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



