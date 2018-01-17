# Clustering by fast search and find of density peaks

论文地址：
http://science.sciencemag.org/content/344/6191/1492

基于密度中心的聚类，和DBSCAN的区别主要是，DBSCAN是找到一个个小聚集点，然后再把小类聚成大类，
density peaks是先求聚类的中心点，再通过一次iteration把距离最近各中心点最近的聚成一类


