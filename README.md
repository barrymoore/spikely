# spikely

Synopsis:

# Get this usage statement (note this is a function not an option).
spikely help

# Get usage statement for a particular function.
spikely spike_cohort --help

# Run cohort spiking mode with parameters defined in a config file.
spikely spike_cohort --config_file spikely.yaml --disease_vcf clinvar.vcf.gz 
    --sample_vcf case_control.vcf.gz

# Run trio spiking mode with parameters on the command line.
spikely spike_trio --ped family.ped --inheritance recessive --maf_key MAF 
    disease_alleles.vcf.gz

Description:

This script will consume a VCF file of causal variants and produce a
VCF file with those variants 'spiked' into the genotypes of a set of
individuals defined by various genetic and population parameters.  The
script has several modes of operation corresponding to various NGS
genetic analysis designs (i.e. trio, pedigree, cohort etc.).  It
understands genetic concepts such as inheritance, penetrance and
population attributable risk and allele population frequency and
allows those parameters to be specified in a configuration file.  the
VCF file of affected cases.

Functions:

help
spike_duo
spike_trio
spike_quartet1
spike_quartet2
spike_pedigree
spike_cohort
Option h requires an argument

# spikely cohort

Synopsis:

# Get a template config file for the cohort mode.
spikely spike_cohort --config_tmplt

# Run cohort spiking mode with parameters defined in a config file.
spikely  spike_cohort --config_file spikely.yaml --disease_vcf clinvar.vcf.gz 
    --sample_vcf case_control.vcf.gz

Description:

The spike_cohort function will consume a VCF file of disease variants
and produce a VCF file with those variants 'spiked' into the genotypes
of a set of case & control samples defined by various genetic and
population parameters.  The script understands genetic concepts such
as inheritance, penetrance and population attributable risk and allele
population frequency and allows those parameters to be specified in a
configuration file.

Options:

--inheritance, -i

    recessive - Two causal alleles per affected individual in a given
		causal gene.  Causal alleles show recessive mendelian
		inheritance in families.
    dominant  - One causal allele per affected individual.  Causal alleles
		show dominant mendelian inheritance in families.
    x-linked  - One causal allele on chromosome X per male inherited from mother.
    additive  - Potentially many causal alleles per affected individual.

--max_rate, -r

    The max MAF for any given variant.

--par, -p

    The max percent of individuals affected with a given gene.

--penetrance, -e

    The max percent of individuals with causal alleles, but labeled in
    PED file as unaffected.

--heritability, -h

    The max percent of individuals without causal alleles, but labeled
    in PED file as affected.

--ped_file, -d

    The pedigree file in plink PED format.

--maf_key, -f

    The INFO key in the VCF file that contains the population MAF for
    each variant.

--gene_key, -g

    The INFO key in the VCF file that contains the gene symbol for
    each variant.

--config_file, -c

    The filename for a YAML formatted file that contains gene and
    variant configuration options.

--config_tmplt, -t

    If this option is given, together with the --mode option, the
    script will print a config file template and exit.  The template
    will have each of the key/value relavant for the given mode and
    you can edit the template and used the resulting config file with
    the --config_file option above.

