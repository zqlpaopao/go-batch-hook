# go-batch-hook
支持go的各种类型数据的 聚总批量处理，提高程序的效率到一个档次

# 1万数据
```
$ go test -bench=.  --benchmem
BenchmarkInsert 2.39923775s
goos: darwin
goarch: arm64
pkg: github.com/zqlpaopao/go-batch-hook/pkg
BenchmarkInsert-10                     1        2399253583 ns/op        88804536 B/op    1069830 allocs/op
BenchmarkNewBatchHook-end 4.22179075s
BenchmarkNewBatchHook-10               1        4221820833 ns/op        47484008 B/op     370034 allocs/op
PASS
ok      github.com/zqlpaopao/go-batch-hook/pkg  7.128s

```


# 10万数据的落盘操作
```
$ go test -bench=.  --benchmem
BenchmarkInsert 26.579409333s
goos: darwin
goarch: arm64
pkg: github.com/zqlpaopao/go-batch-hook/pkg
BenchmarkInsert-10                     1        26579423833 ns/op       889199336 B/op  10701614 allocs/op
BenchmarkNewBatchHook-end 3.915047166s
BenchmarkNewBatchHook-10               1        3915075291 ns/op        505668440 B/op   3704230 allocs/op
PASS
ok      github.com/zqlpaopao/go-batch-hook/pkg  30.821s

```
从内存执行时间分析都是批量处理的更胜一筹
当前事3个协程在操作，如果增加协程数量效果会更佳
```
BenchmarkInsert 26.579409333s
BenchmarkNewBatchHook-end 3.915047166s
```
内存分配
```
BenchmarkInsert-10                     1        26579423833 ns/op       889199336 B/op  10701614 allocs/op
BenchmarkNewBatchHook-10               1        3915075291 ns/op        505668440 B/op   3704230 allocs/op
```

# 1百万数据
```
$ go test -bench=.  --benchmem
BenchmarkInsert 3m35.142929125s
goos: darwin
goarch: arm64
pkg: github.com/zqlpaopao/go-batch-hook/pkg
BenchmarkInsert-10                     1        215142940375 ns/op      8907524464 B/op 107014932 allocs/op
BenchmarkNewBatchHook-end 30.161605125s
BenchmarkNewBatchHook-10               1        30161636875 ns/op       5260201240 B/op 37048280 allocs/op
PASS
ok      github.com/zqlpaopao/go-batch-hook/pkg  245.785s
```
百万数据的时候效果更佳
```
BenchmarkInsert 3m35.142929125s
BenchmarkNewBatchHook-end 30.161605125s
```

