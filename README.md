# Benchmarked dataset for entity resolution

## This repository helps to create dataset for entity resolution. 

```java
    root
    |-- recid: string (nullable = true)
    |-- givename: string (nullable = true)
    |-- surname: string (nullable = true)
    |-- suburb: string (nullable = true)
    |-- postcode: string (nullable = true)
```

> ```recId``` entites with the same recId refer to the same entity.

## Download the dataset 

- [North Carolina Voters 10M](https://dbs.uni-leipzig.de/research/projects/object_matching/benchmark_datasets_for_entity_resolution)

- Copy the unzip files into the data directory. 

- More information about the research see [Evaluation of entity resolution approaches on real-world match problems](https://dbs.uni-leipzig.de/publication/title/evaluation_of_entity_resolution_approaches_on_real_world_match_problems)

## Remove duplicates 

```python
people.distinct()
    .repartition(4)
    .write
    .option("compression","gzip")
    .format("csv") 
    .mode(SaveMode.Overwrite)
    .save("file:/home/jovyan/work/data/de-duplicated/")
```
