## BEAGLE

This directory contains code to infer and phase strain haplotypes of mixed *Plasmodium falciparum* samples using [Browning and Browning (2007)](#beagle)'s method.

`BEAGLE` requires genotype likelihood of homozygous reference, heterozygous and homozygous alternative as input, which is calculated by <img src="https://raw.githubusercontent.com/shajoezhu/DEploid-Supplementary-Materials/master/benchMark/beagle/eq_no_01.png" alt="Equation not rendered" height="20">, where *r* and *a* are the reference and alternative allele counts, and *x* is the error rate, which takes value of 0.01, 0.5 and 0.99 when it's homozygous reference, heterozygous and homozygous alternative. We first convert the VCF to `BEAGLE` input format

```bash
./convert_pf3k_vcf_to_beagle_input.py labMixedAfterFilter.vcf.gz
```

then run `BEAGLE` with following command:

```bash
java  -Xmx3512m -jar ~/researchDiary/beagle/beagle.r1398.jar gl=labMixedAfterFilter.gl.vcf.gz out=labMixedAfterFilter.gl.out
```

### References

Browning, S. R. and B. L. Browning (2007) Rapid and accurate haplotype phasing and missing-data inference for whole-genome association studies by use of localised haplotype clustering. *American Journal of Human Genetics* 81(5), 1084–1097. <a name="beagle"></a>

