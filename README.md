# cTAKES Special Case QA

This repository describes a quality assurance issue between two cTAKES systems.

The issue appears when running the sentence `severe bipolar i disorder` with both the proper cTAKES program and the cTAKES Web Rest MySQL solution. The former recognizes the term `bipolar` while the latter is not.


## Enviroments

1) cTAKES Web Rest MySQL version @ 1850060 with the resource data loaded in via plain SQL
2) cTAKES proper @ 1850060 with the resources data loaded on disk/in memory

## MySQL Data

The follow was run on the MySQL database:

```
cui_terms(236784,12,13,'severe bipolar i disorder , most recent episode mixed , with psychotic features','features')
TUI(236784,48)
PREFTERM(236784,'Severe mixed bipolar I disorder with psychotic features')
SNOMEDCT_US(236784,10981006)
```

## Execution & Results

1) Web Rest was ran with both `Full` and `Default` pipelines via the web interface. Both results can be found in the folder here: `REST MySQL Results`.
2) The regular program was ran with the `AggregatePlaintextFastUMLSProcessor` pipeline via the CLI. All results can be found in the folder here: `CVD Results`.


### License

CC0