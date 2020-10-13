mkdir busblog
mkdir bsub_submit
mkdir snpeff/01.snpeff
mkdir snpeff/02.snpeff
mkdir snpeff/01.annotated
mkdir snpeff/02.annotated
mkdir snpeff/03.annotated
mkdir snpeff/04.annotated
mkdir snpeff/05.annotated
mkdir snpeff/06.annotated

foreach sample ("`cat samples.list`")
foreach chr ("`cat chrs.list`")

echo  "bsub_submit/snpeff.${sample}_${chr}.lsf"


#cat <<EOF > bsub_submit/snpeff.${sample}_${chr}.lsf

#BSUB -J ${sample}_$chr
#BSUB -W 2:00
#BSUB -o /rsrch3/scratch/lym_myl_rsch/qcai1/MCLdata/snakemake-gatk-SNV-CNV-byC/busblog/snpeff.${sample}_${chr}.o
#BSUB -e /rsrch3/scratch/lym_myl_rsch/qcai1/MCLdata/snakemake-gatk-SNV-CNV-byC/busblog/snpeff.${sample}_${chr}.err
#BSUB -cwd /rsrch3/scratch/lym_myl_rsch/qcai1/MCLdata/snakemake-gatk-SNV-CNV-byC/
#BSUB -q short
#BSUB -u qcai1@mdanderson.org
#BSUB -n 1
#BSUB -M 10
#BSUB -R rusage[mem=40]


cd /rsrch3/scratch/lym_myl_rsch/qcai1/MCLdata/snakemake-gatk-SNV-CNV-byC/
module load bcftools/1.3.1

      bcftools view -f PASS -i 'INFO/ANN ~ "missense_variant" ' \
              --output-type v snpeff/01.annotated/01.${sample}_${chr}_9_somatic_oncefiltered.ann.vcf  \
                          > snpeff/02.annotated/02.passed.${sample}_${chr}_9_somatic_oncefiltered.ann.vcf


end
end
