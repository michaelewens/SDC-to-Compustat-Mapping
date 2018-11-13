# Description

Connecting SDC's M&A database to Compustat requires `gvkey`'s for both the acquirer and target (if they are traded/public).  [Gordon Phillips](http://faculty.tuck.dartmouth.edu/gordon-phillips/) did a lot of the legwork to get this project started.  The final product has over X% coverage of targets and acquirers that appear to be public.   

# How it was done

I ([Michael Ewens](https://ewens.caltech.edu/) created [this website](http://makeresearchgreatagain.com/data_search/) to replicate the `gvkey` search in WRDS.  Either myself or a research assistant searched for nearly all M&As deals using this tool.  

# Data

CSV coming soon.  The data format is 

`(DealNumber, tgt_gvkey, acq_gvkey)`

where the `DealNumber` is the SDC identifier for deals.  Note that this includes all deals, even those missing `gvkey`'s.

# Code to implement

The following code snippets will help you incorporate the data into yours.

  ## Stata
  
  Coming soon.
  
  ## R
  
  Coming soon.
  
  ## Python
  
  Coming soon.
