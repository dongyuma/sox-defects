对于GSL 2.7.1中的函数 ，我们发现在某些输入下会导致一些函数发生浮点异常，导致代码缺陷，进而导致错误的程序行为。
对于发现的每一类浮点异常，列出了 1 或 2 个。我们描述了函数名称、抛出的异常类型、触发异常的输入以及导致异常的代码的具体位置。

第一类：无效操作异常
1.函数gsl_sf_conicalP_xlt1_large_neg_mu_e在文件/gsl-2.7.1/specfunc/legendre_con.c中第221行输入tau=1.0, mu=2.0, x=3.0时抛出无效异常：double p = x/sqrt(beta2* (1.0-xx) + 1.0); 由于sqrt参数不能为负数，此时会出现无效异常。
2.函数gsl_cdf_laplace_Qinv在文件/gsl-2.7.1/cdf/laplaceinv.c中第67行输入Q=-0.5时抛出无效异常：x = -a * log(2Q);因为log参数不能为负数，此时会出现无效异常。
类别2：溢出
3.函数gsl_sf_bessel_Knu_scaled_asymp_unif_e在文件/gsl-2.7.1/specfunc/bessel.c第398行输入nu=1.45e-192, x=1.0时抛出溢出异常： double root_term =hypot(1.0,z);
4.函数gsl_sf_conicalP_xlt1_large_neg_mu_e在文件/gsl-2.7.1/specfunc/legendre_con.c的第219行输入tau =1.23e189,mu=1e-2时抛出溢出异常：double beta2 = beta*beta;
类别3：下溢
5.函数gsl_sf_bessel_Jnu_asympx_e在文件/gsl-2.7.1/specfunc/bessel.c第217行输入nu=1.23e-189, x=1.0时抛出下溢异常：double mu = 4.0*nu*nu;
第四类：被零除
6.函数gsl_sf_bessel_Knu_scaled_asympx_e在文件/gsl-2.7.1/specfunc/bessel.c的第318行输入x=0.0时抛出被零除浮点异常：double r = nu/x;
第五类：类型转换
7、函数gsl_ran_gamma_knuth在文件/gsl-2.7.1/randist/gamma.c第44行输入a=1.23e189时抛出类型转换异常导致的溢出： unsigned int na = Floor(a);
第6类：不精确（舍入误差）
8.函数 hyperg_1F1_1 抛出舍入错误异常，导致 while 循环在文件 /gsl-2.7.1/specfunc/hyperg_1F1.c 中第 378 行的输入 b=x=1.23e189 时无法终止： while(bp > b +0.1) {.当x达到1.23e189（一个非常大的值）时，378处的循环不会终止，
因为第380行的bp -= 1.0使得bp – 1.0四舍五入为bp本身，因此bp > b处的while条件 378处的+0.1始终满足且无法终止。

对于上面列出的8种情况，我认为在调用函数之前，提前对输入参数的范围进行检查会避免浮点异常的发生，避免导致错误的程序行为。 同时也能够避免对函数调用得到的无效返回值再次进行操作（依然导致无效值）导致的问题。 
（因此，应该在调用函数之前，提前对输入参数的范围进行检查，而不是不做任何操作。以上处都存在缺陷。例如，在调用 sqrt(x) 函数之前，放入 if(x<0){return;} 以便进行检查，等等。）
