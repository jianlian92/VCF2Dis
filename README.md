# VCF2Dis
<b>VCF2Dis: A new simple and efficient software to calculate p-distance matrix based Variant Call Format</b>

1) Install
------------
  Just  [make]  or [sh  make.sh ]  to compile this software.
  the final software can be found in the Dir [bin/VCF2Dis]
<pre>
        tar -zxvf  VCF2DisXXX.tar.gz
        cd VCF2DisXXX;
        make ; make clean
        ./bin/VCF2Dis
</pre>


2) Example
------------
* 1) Parameter description:
```php
	Usage: VCF2Dis -InPut  <in.vcf>  -OutPut  <p_dis.mat>

		-InPut     <str>     Input GATK VCF genotype File
		-OutPut    <str>     OutPut Sample p-Distance matrix

		-SubPop    <str>     SubGroup SampleList of VCFFile [ALLsample]
		-KeepMF              Keep the Middle File diff & Use matrix

		-help                Show this help [hewm2008 v1.08]

```

* 2) draw the Figure

```
# 2.1） To new all the sample p_distance matrix based VCF, run VCF2Dis directly
      ./bin/VCF2Dis	-InPut	in.vcf.gz	-OutPut p_dis.mat

# 2.2) To new sub group sample p_distance matrix ; Pput their sample name into File sample.list
      ./bin/VCF2Dis	-InPut	in.vcf.gz	-OutPut p_dis.mat  -SubPop  sample.list
```

* 3) constructd nj-tree and present it (need deal with Other software)
```
      #    3.1 Run  PHYLIP  
      #   After p_distance done , software PHYLIP 3.69 (http://evolution.genetics.washington.edu/phylip.html) ,with neighbor-joining method can was used to construct the phylogenetic tree on the basis of this  p_distance matrix;
       
           PHYLIPNEW-3.69.650/bin/fneighbor  -datafile p_dis.matrix  -outfile tree.out1.txt -matrixtype s -treetype n -outtreefile tree.out2.tre

      #    3.2 Run  MEGA  
      #    The MEGA6 (http://www.megasoftware.net/) was used to present the phylogenetic tree based this file [tree.out2.tre].
	
```
* 4) you can see the neighbor-joining tree and save it as PDF format



3) Introduction
------------
To new the p_distance matrix besed the VCF file. the more infomation
  about the  p_distance matrix ,see this website:
  http://evolution.genetics.washington.edu/phylip/doc/distance.html

  The VCF SNPs datasets were used to calculate p-distance between individuals, according to the follow formula to operate the sample i and sample j genetic distance:

                D_ij=1/L *[(sum(d(l)_ij))]

  </br> Where L is the length of regions where SNPs can be identified, and given the alleles at position l are A/C:
```
            d(l)_ij=0.0     if the genotypes of the two individuals were AA and AA;
            d(l)_ij=0.5     if the genotypes of the two individuals were AA and AC;
            d(l)_ij=0.0     if the genotypes of the two individuals were AC and AC;
            d(l)_ij=1.0     if the genotypes of the two individuals were AA and AC;
            d(l)_ij=0.0     if the genotypes of the two individuals were CC and CC;
```


4) Results
------------
some LD decay images which I draw in the paper before.

* [50 Rices NBT](http://www.nature.com/nbt/journal/v30/n1/images/nbt.2050-F1.jpg)
* [31 soybeans  NG]( http://www.nature.com/ng/journal/v42/n12/images/ng.715-F1.jpg)

5）Discussing
------------
- email: hewm2008@gmail.com / hewm2008@qq.com  
- join the<b><i> QQ Group : 125293663</b></i>



######################swimming in the sky and flying in the sea ########################### ##

