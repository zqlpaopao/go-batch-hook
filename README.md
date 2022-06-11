# go-batch-hook
支持go的各种类型数据的 聚总批量处理，提高程序的效率到一个档次

```
$ go test -bench=.  --benchmem
insert-HOOK 22.710411792s
goos: darwin
goarch: arm64
pkg: github.com/zqlpaopao/tool/batch_hook/pkg
BenchmarkInsert-10                     1        22710426375 ns/op       1110348496 B/op 10002595 allocs/op
end
BATCH-HOOK 13.802230125s
BenchmarkNewBatchHook-10               1        13802237000 ns/op       764493256 B/op   2306961 allocs/op
PASS
ok      github.com/zqlpaopao/tool/batch_hook/pkg        36.999s
```
