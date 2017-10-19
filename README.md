![spikely](https://github.com/Yandell-Lab/spikely/blob/master/img/Spikely.png)

# spikely - spike pathogenic alleles into VCF files.

## Synopsis:

Get this usage statement (note this is a function not an option).

```
spikely help
```

Get usage statement for a particular function.

```
spikely cohort --help
```

Run cohort spiking mode with parameters defined in a config file.

```
spikely cohort --config_file spikely.yaml --disease_vcf clinvar.vcf.gz \
    --sample_vcf case_control.vcf.gz
```

Run trio spiking mode with parameters on the command line. NOTE: trio spiking not yet implimented.

```
spikely trio --ped family.ped --inheritance recessive --maf_key MAF \
    disease_alleles.vcf.gz
```

## Description:

This script will consume a VCF file of causal variants and produce a
VCF file with those variants 'spiked' into the genotypes of a set of
individuals defined by various genetic and population parameters.  The
script has several modes of operation corresponding to various NGS
genetic analysis designs (i.e. trio, pedigree, cohort etc.).  It
understands genetic concepts such as inheritance, penetrance and
population attributable risk and allele population frequency and
allows those parameters to be specified in a configuration file. Note
that currently only cohort spiking is implimented.

## Functions:

```
help
duo
trio
quartet1
quartet2
pedigree
cohort
```

