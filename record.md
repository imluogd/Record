### 计算H(T)的标准方法：

[](https://github.com/imluogd/Record/blob/main/%E8%AE%A1%E7%AE%97H(T).png)

### Thermo

[两篇热力学数据计算的入门介绍文章 - 量子化学 (Quantum Chemistry) - 计算化学公社 (keinsci.com)](http://bbs.keinsci.com/forum.php?mod=viewthread&tid=123)

### shell中换后缀

比如g16< $i > {$i%.*}.log，$i为1.gjf

[shell---消除文件后缀四种方法_weixin_34351321的博客-CSDN博客](https://blog.csdn.net/weixin_34351321/article/details/93072697)

还有多种方法，Tian Lu的脚本中还有别的方法。

### BOMD

[求助：BOMD和MD理论差别 - 分子模拟 (Molecular Modeling) - 计算化学公社 (keinsci.com)](http://bbs.keinsci.com/thread-21981-1-1.html)

介绍了XTB属于半经验的KS-DFT，属于BOMD。

*“基于诸如PM6、GFN-xTB、DFTB+这些半经验层面的方法做动力学，虽然用AIMD这个词有点牵强，毕竟这些方法里面引入了大量经验参数，但为了表述方便往往也被算作AIMD（此时的AIMD就泛指基于量子力学方法的分子动力学了）。”*

### ORCA5

**new grids**  ：The new DefGrid2 is larger but much more robust than the previous default and the upgrade to DefGrid3 is only required in rare cases.   

the **RIJCOSX** approximation is now the default for DFT calculations (including double-hybrids) and can be turned off via
!NoCOSX.   

The **RI-MP2** approximation is on by default for double-hybrid DFT calculations   

If the default SCF solver fails to converge or is not progressing fast enough, ORCA 5 will switch to the new **TRAH** solver (see section 9.7.7), which will almost always converge, except in extreme cases such as a totally unreasonable geometry or severe basis set deficiencies or linear dependence. It can be turned off via !NoTrah 

  **GRID and RI and associated basis set settings**：

HF或杂化泛函，双电子积分有两种：库仑积分和交换积分。库仑积分是用RIJ加速，交换积分是用K或COSX加速

**单位转换**

1 Eh = 27.2113834 eV
1 eV = 8065.54477 cm−1 = 23.0605 kcal/mol
1 cm−1 = 29979.2458 MHz
1 a0 = 0.5291772083 A
1 a.t.u. = 2.4188843 10−17 s

**并行核数**：

The efficiency is such that for RI-DFT perhaps up to 16 processors are a good idea while for hybrid DFT and Hartree-Fock a few more processors are appropriate.  

Coupled cluster calculations usually scale well up to at least 8 processors but probably it is also worthwhile to try 16.  

For Numerical Frequencies or Gradient runs it makes sense to use as many processors as 6*Number of Atoms.  
