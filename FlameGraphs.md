

1. 服务器上部署 perf  

    ```
    # yum install perf
    ```

1. 部署 [FlameGraph on github](https://github.com/brendangregg/FlameGraph)  
> Flame graphs can be created in three steps: 
>     1. Capture stacks
>     2. Fold stacks
>     3. flamegraph.pl

> ```bash
> perf record -F 99 -p 181 -g -- sleep 60 
> perf script > out.perf
> ./stackcollapse-perf.pl out.perf > out.folded
> ./flamegraph.pl out.kern_folded > kernel.svg
> ```


# 参考

1. [FlameGraph on github](https://github.com/brendangregg/FlameGraph)
1. [如何读懂火焰图](http://www.ruanyifeng.com/blog/2017/09/flame-graph.html)
1. [用 CPI 火焰图分析 Linux 性能问题](https://www.ctolib.com/topics-130088.html)
1. [动态追踪技术漫谈](https://openresty.org/posts/dynamic-tracing/)
