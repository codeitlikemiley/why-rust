# Why Use Rust?

## AWS take on Rust
https://aws.amazon.com/blogs/opensource/sustainability-with-rust/

##   Web Framework Benchmarks Bare Metal Performance (not serverless/not cloud)
https://www.techempower.com/benchmarks/#section=data-r21

|Rnk|Framework|Best performance (higher is better)|   |Errors|Cls|Lng|Plt|FE|Aos|DB|Dos|Orm|IA|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|1|drogon-core|616,607|100.0%|0|Ful|C++|Non|Non|Lin|Pg|Lin|Raw|Rea|
|2|xitca-web|587,955|95.4%|0|Plt|rs|Non|xit|Lin|Pg|Lin|Raw|Rea|
|3|drogon|556,046|90.2%|0|Ful|C++|Non|Non|Lin|Pg|Lin|Mcr|Rea|
|4|salvo [pg]|542,547|88.0%|0|Mcr|rs|rs|hyp|Lin|Pg|Lin|Raw|Rea|
|5|just-js|538,414|87.3%|0|Plt|JS|jus|Non|Lin|Pg|Lin|Raw|Rea|
|6|may-minihttp|520,976|84.5%|0|Mcr|rs|rs|may|Lin|Pg|Lin|Raw|Rea|
|7|actix-http|512,422|83.1%|0|Plt|rs|Non|act|Lin|Pg|Lin|Raw|Rea|
|8|axum [postgresql]|498,541|80.9%|0|Ful|rs|rs|hyp|Lin|Pg|Lin|Raw|Rea|
|9|aspcore-ado-pg|458,677|74.4%|0|Plt|C#|.NE|kes|Lin|Pg|Lin|Raw|Rea|
|10|officefloor-sqlclient|432,309|70.1%|0|Plt|Jav|off|woo|Lin|Pg|Lin|Raw|Rea|
|374|laravel-laravel-s|16,657|2.7%|0|Ful|PHP|swo|Non|Lin|My|Lin|Ful|Rea|
|382|laravel-swoole|16,004|2.6%|0|Ful|PHP|swo|Non|Lin|My|Lin|Ful|Rea|
|414|laravel|8,437|1.4%|0|Ful|PHP|fpm|ngx|Lin|My|Lin|Ful|Rea|
****
Rust Frameworks:

[salvo postgresql](https://salvo.rs)

[actix-http](https://actix.rs)

[axum postgresql](https://github.com/tokio-rs/axum)


PHP Frameworks:

laravel-laravel-s

laravel-swoole

[Laravel](https://laravel.com)


## Actix Web vs Laravel Benchmark 


[![Actix Web vs Laravel Benchmark ](https://img.youtube.com/vi/Vk41-xPxQI4/0.jpg)](https://www.youtube.com/watch?v=Vk41-xPxQI4)



# [AWS Lambda Comparison on different Languages](https://filia-aleks.medium.com/aws-lambda-battle-2021-performance-comparison-for-all-languages-c1b441005fd1#f590)

Excerpt from: https://filia-aleks.medium.com/aws-lambda-battle-2021-performance-comparison-for-all-languages-c1b441005fd1#f590

---


## Cold start:

- **All languages(except Java and .Net) have a pretty small cold start.**
- Java even cannot start with 128Mb. It needs more memory. But GraalVM can help in this case.
- Rust beats all runtimes for all setups for cold start, the only exception is 128 MB where Python is the best.

## Warm start:

- Golang and Rust are the winners. They have the same brilliant performance.
- .Net has almost the same performance as Golang and Rust, but only after 1k iterations(after JIT).
- GraalVM has a stable great performance almost the same as .Net and a bit worse than Rust and Golang. But it doesn’t perform well for the smallest setup.
- Java is the next after GraalVM.The same as .Net, Java needs some time(1–3k iterations) for JIT(C1). Unfortunately for this particular use case, I was not able to achieve the expected great performance after JIT C2 compilation. Maybe AWS just disabled it.
- Python has stable good performance but works too slow for the 128 MB
- Ruby has almost the same performance as Python, but we see some duration growing after 20 min invocations(after 15k iteration).
- NodeJs is the slowest runtime, after some time it becomes better(JIT?) but still is not good enough. In addition, we see the NodeJS has the worst maximum duration.

> Cold+warm start **winners are Golang and Rust**. They are always faster than other runtimes and demonstrated very stable results.


---



## GRPC vs REST API
https://medium.com/sahibinden-technology/benchmarking-rest-vs-grpc-5d4b34360911#3dbc

**JSON (9 Bytes)**
```
{  
  "id":42  
}
```

**Protobuf (2 Bytes)**

```
0x08 0x2a
```

**Benchmark Results:**

![](https://miro.medium.com/v2/resize:fit:1400/1*Md1l-CcrwCEEYZWNNZl1hQ.png)

It looks even more clear with higher loads of data that **gRPC and Protobuff really out-performs REST and JSON.**



# [Go (Golang) vs Rust: The Ultimate Performance Battle (2023)](https://youtu.be/IcMdPfJpbyc?t=209)

Golang is known for using GRPC , this video compares rust using GRPC , and make's it a clear choice due to memory efficiency , since Golang has Garbage Collectors.

[![# Go (Golang) vs Rust: The Ultimate Performance Battle (2023)](https://img.youtube.com/vi/IcMdPfJpbyc/0.jpg)](https://www.youtube.com/watch?v=IcMdPfJpbyc)


