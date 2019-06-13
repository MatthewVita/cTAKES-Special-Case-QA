# cTAKES Special Case QA

This repository describes a quality assurance issue between two cTAKES systems.

The issue appears when running the sentence `severe bipolar i disorder` with both the proper cTAKES program and the cTAKES Web Rest MySQL solution. The former recognizes the term `bipolar` (with the SNOMEDCT_US coding scheme) while the latter does not.


## Enviroments

1) cTAKES proper @ svn 1850060 with the resources data loaded on disk/in memory
2) cTAKES Web Rest MySQL version @ svn 1850060 with the resource data loaded in via plain SQL


## MySQL Data

The follow was ran on the MySQL database:

```
cui_terms(236784,12,13,'severe bipolar i disorder , most recent episode mixed , with psychotic features','features')
TUI(236784,48)
PREFTERM(236784,'Severe mixed bipolar I disorder with psychotic features')
SNOMEDCT_US(236784,10981006)
```

## Execution & Results

1) Web Rest was ran with both `Full` and `Default` pipelines via the web interface. Both results can be found in the folder here: `REST MySQL Results`. The results are somewhat the same, with `Full` having more textsems, refsems, syntax, and cas nodes.

2) The regular program was ran with the `AggregatePlaintextFastUMLSProcessor` pipeline via the CLI. All results can be found in the folder here: `CVD Results`. `XCAS` and `XMI CAS` both show the SNOMED_US-linked findings `Bipolar I disorder` and `Severe bipolar I disorder`, which are the correct results.


### License

CC0
