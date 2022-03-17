# Mxtasking 测试

## 准备

1. 设置 numa-balance

   ```bash
   $ sudo cat /proc/sys/kernel/numa_balancing
   1
   $ sudo su -c "echo 0 > /proc/sys/kernel/numa_balancing"
   or
   $ sysctl -w kernel.numa_balancing=0
   $ sudo cat /proc/sys/kernel/numa_balancing
   0
   ```

   或者在 ` /etc/sysctl.conf` 文件中设置。

2. 生成测试

   `make ycsb-a`

   输出：

   ```text
    Generaring YCSB workload workloada with key type randint
    Command line: -load -db com.yahoo.ycsb.BasicDB -P /home/writex/hjn/index-bench/mxtasking/workloads_specification/workloada -s
    YCSB Client 0.16.0

    Loading workload...
    Starting test.
    DBWrapper: report latency for each error is false and specific error codes to track for latency are: []
    2022-03-17 19:03:42:427 0 sec: 14 operations; ∞ current ops/sec; est completion in 0 second [INSERT: Count=26, Max=2701, Min=44, Avg=155.65, 90=63, 99=2701, 99.9=2701, 99.99=2701] 
    2022-03-17 19:03:52:402 10 sec: 2594335 operations; 259328.37 current ops/sec; est completion in 1 minute [INSERT: Count=2594646, Max=19999, Min=3, Avg=3.22, 90=4, 99=6, 99.9=15, 99.99=23] 
    2022-03-17 19:04:02:398 20 sec: 5347903 operations; 275466.99 current ops/sec; est completion in 55 seconds [INSERT: Count=2753547, Max=9247, Min=3, Avg=3.1, 90=3, 99=5, 99.9=15, 99.99=20] 
    2022-03-17 19:04:12:398 30 sec: 8108427 operations; 276052.4 current ops/sec; est completion in 44 seconds [INSERT: Count=2760552, Max=6663, Min=3, Avg=3.1, 90=3, 99=5, 99.9=15, 99.99=20] 
    2022-03-17 19:04:22:397 40 sec: 10881269 operations; 277284.2 current ops/sec; est completion in 34 seconds [INSERT: Count=2772744, Max=10279, Min=3, Avg=3.1, 90=3, 99=5, 99.9=15, 99.99=19] 
    2022-03-17 19:04:32:398 50 sec: 13630530 operations; 274926.1 current ops/sec; est completion in 24 seconds [INSERT: Count=2749372, Max=1351, Min=3, Avg=3.11, 90=3, 99=5, 99.9=15, 99.99=20] 
    2022-03-17 19:04:42:398 60 sec: 16427541 operations; 279701.1 current ops/sec; est completion in 14 seconds [INSERT: Count=2796907, Max=8991, Min=3, Avg=3.07, 90=3, 99=5, 99.9=15, 99.99=19] 
    2022-03-17 19:04:52:397 70 sec: 19199914 operations; 277237.3 current ops/sec; est completion in 3 second [INSERT: Count=2772393, Max=8887, Min=3, Avg=3.12, 90=3, 99=5, 99.9=15, 99.99=19] 
    2022-03-17 19:04:55:264 72 sec: 20000000 operations; 279164.69 current ops/sec; [CLEANUP: Count=1, Max=5, Min=5, Avg=5, 90=5, 99=5, 99.9=5, 99.99=5] [INSERT: Count=799813, Max=1367, Min=3, Avg=3.11, 90=3, 99=5, 99.9=14, 99.99=19] 
    Command line: -t -db com.yahoo.ycsb.BasicDB -P /home/writex/hjn/index-bench/mxtasking/workloads_specification/workloada -s
    YCSB Client 0.16.0

    Loading workload...
    Starting test.
    DBWrapper: report latency for each error is false and specific error codes to track for latency are: []
    2022-03-17 19:04:55:601 0 sec: 171 operations; ∞ current ops/sec; est completion in 0 second [READ: Count=232, Max=1064, Min=9, Avg=32.75, 90=36, 99=123, 99.9=1064, 99.99=1064] 
    2022-03-17 19:05:05:572 10 sec: 2622413 operations; 262197.98 current ops/sec; est completion in 1 minute [READ: Count=2622623, Max=3783, Min=3, Avg=3.18, 90=3, 99=6, 99.9=13, 99.99=21] 
    2022-03-17 19:05:15:570 20 sec: 5391719 operations; 276958.3 current ops/sec; est completion in 55 seconds [READ: Count=2769116, Max=1306, Min=3, Avg=3.09, 90=3, 99=5, 99.9=13, 99.99=19] 
    2022-03-17 19:05:25:571 30 sec: 8164781 operations; 277306.2 current ops/sec; est completion in 44 seconds [READ: Count=2773079, Max=6951, Min=3, Avg=3.1, 90=3, 99=5, 99.9=15, 99.99=19] 
    2022-03-17 19:05:35:571 40 sec: 10975534 operations; 281075.3 current ops/sec; est completion in 33 seconds [READ: Count=2810777, Max=1598, Min=3, Avg=3.07, 90=3, 99=5, 99.9=13, 99.99=19] 
    2022-03-17 19:05:45:570 50 sec: 13826901 operations; 285136.7 current ops/sec; est completion in 23 seconds [READ: Count=2851336, Max=246, Min=3, Avg=3.05, 90=3, 99=5, 99.9=13, 99.99=19] 
    2022-03-17 19:05:55:570 60 sec: 16681728 operations; 285482.7 current ops/sec; est completion in 12 seconds [READ: Count=2854684, Max=14783, Min=3, Avg=3.06, 90=3, 99=5, 99.9=9, 99.99=19] 
    2022-03-17 19:06:05:570 70 sec: 19456385 operations; 277465.7 current ops/sec; est completion in 2 second [READ: Count=2774748, Max=162431, Min=3, Avg=3.12, 90=3, 99=5, 99.9=13, 99.99=19] 
    2022-03-17 19:06:07:477 71 sec: 20000000 operations; 285212.49 current ops/sec; [READ: Count=543405, Max=30, Min=3, Avg=3.04, 90=3, 99=5, 99.9=12, 99.99=19] [CLEANUP: Count=1, Max=11, Min=11, Avg=11, 90=11, 99=11, 99.9=11, 99.99=11] 
    Built target ycsb-a
   ```

## 测试

### Blink Tree

#### 基础测试

```bash
./bin/blinktree_benchmark 1:4                        
core configuration: 
  1: 0
  2: 0 1
  4: 0 1 2 3
workload: fill: 20m / read-only: 20m

1       1       0       9259 ms 2.16006e+06 op/s
1       1       1       7185 ms 2.78358e+06 op/s
2       1       0       6121 ms 3.26744e+06 op/s
2       1       1       4109 ms 4.86736e+06 op/s
4       1       0       3338 ms 5.99161e+06 op/s
4       1       1       1957 ms 1.02197e+07 op/s
```

###### Running workload A using optimistic synchronization

    ./bin/blinktree_benchmark 1: -s 2 -i 3 -pd 3 -p -f workloads/fill_randint_workloada workloads/mixed_randint_workloada -o optimistic.json

###### Running workload A using best matching synchronization

    ./bin/blinktree_benchmark 1: -s 2 -i 3 -pd 3 -p --sync4me -f workloads/fill_randint_workloada workloads/mixed_randint_workloada -o sync4me.json

###### Running workload A using reader/writer-locks
    
    ./bin/blinktree_benchmark 1: -s 2 -i 3 -pd 3 -p --latched -f workloads/fill_randint_workloada workloads/mixed_randint_workloada -o rwlocked.json
    
###### Running workload A using core-based sequencing
    
    ./bin/blinktree_benchmark 1: -s 2 -i 3 -pd 3 -p --exclusive -f workloads/fill_randint_workloada workloads/mixed_randint_workloada -o core-sequenced.json
    
###### Running workload A using spin-locks
        
    ./bin/blinktree_benchmark 1: -s 2 -i 3 -pd 3 -p --latched --exclusive -f workloads/fill_randint_workloada workloads/mixed_randint_workloada -o spinlocked.json
#### 测试d

### Hash Join