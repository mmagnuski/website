---
title: ft_statfun_indepsamplesZcoh
tags: 
---
```
 FT_STATFUN_INDEPSAMPLESCOHZ calculates the independent samples coherence
 Z-statistic on the biological data in dat (the dependent variable), using the
 information on the independent variable (ivar) in design.

 Use this function by calling one of the high-level statistics functions as
   [stat] = ft_timelockstatistics(cfg, timelock1, timelock2, ...)
   [stat] = ft_freqstatistics(cfg, freq1, freq2, ...)
   [stat] = ft_sourcestatistics(cfg, source1, source2, ...)
 with the following configuration option
   cfg.statistic = 'ft_statfun_indepsamplesZcoh'

 The samples-dimension of the dat-variable must be the result of a reshaping
 operation applied to a data structure with dimord chan_(freq_time) or
 pos_(freq_time). The configuration must contain channel labels in cfg.label or
 position information in cfg.pos. This information is used to determine the number
 of channels. The dimord of the output fields is [prod(nchancmb,nfreq,ntime),1]. The
 channel combinations are the elements of the lower diagonal of the cross-spectral
 density matrix.

 Configuration options
   cfg.computestat    = 'yes' or 'no', calculate the statistic (default='yes')
   cfg.computecritval = 'yes' or 'no', calculate the critical values of the test statistics (default='no')
   cfg.computeprob    = 'yes' or 'no', calculate the p-values (default='no')

 The following options are relevant if cfg.computecritval='yes' and/or
 cfg.computeprob='yes'.
   cfg.alpha = critical alpha-level of the statistical test (default=0.05)
   cfg.tail  = -1, 0, or 1, left, two-sided, or right (default=1)
               cfg.tail in combination with cfg.computecritval='yes'
               determines whether the critical value is computed at
               quantile cfg.alpha (with cfg.tail=-1), at quantiles
               cfg.alpha/2 and (1-cfg.alpha/2) (with cfg.tail=0), or at
               quantile (1-cfg.alpha) (with cfg.tail=1).

 Design specification
   cfg.ivar  = column number of the design that contains the labels of the conditions that
               must be compared (default=1). The labels are the numbers 1 and 2.

 See also FT_TIMELOCKSTATISTICS, FT_FREQSTATISTICS or FT_SOURCESTATISTICS
```
