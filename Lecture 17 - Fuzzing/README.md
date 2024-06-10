## Fuzzing

“fuzzing” technique to test the security and vulnerabilities of crypto libraries in Android applications.

The tools used for fuzzing in this lecture include

1. **OSS-Fuzz:** Continuous Fuzzing Service for Open Source Software
2. **ClusterFuzz:** Scalable Fuzzing Infrastructure
3. **FuzzBench:** Fuzzer benchmarking as a service

which are automated processes used by Google for open-source projects.

Fuzzing involves testing the behavior and vulnerabilities of functions by manipulating inputs, such as strings or images.

[Fuzzing](https://github.com/google/fuzzing) Refer this for more information.

These are all common fuzzing tools, but we will be discussing the CDF (crypto differential fuzzing) tool.

##   CDF (crypto differential fuzzing)

CDF is a tool to automatically test the correctness and security of cryptographic software. CDF can detect implementation errors, compliance failures, side-channel leaks, and so on.

CDF implements a combination of unit tests with "differential fuzzing", an approach that compares the behavior of different implementations of the same primitives when fed edge cases and values maximizing the code coverage.

Unlike general-purpose fuzzers and testing software, CDF is:

- **Smart**: CDF knows what kind of algorithm it's testing and adapts to the tested functions.
- **Fast**: CDF tests only what needs to be tested and parallelizes its tests as much as possible.
- **Polyvalent**: CDF isn't specific to any language or API, but supports arbitrary executable programs or scripts.
- **Portable**: CDF will run on any Unix or Windows platform, since it is written in Go without any platform-specific dependencies.

The purpose of CDF is to provide more efficient testing tool to developers and security researchers, being more effective than test vectors and cheaper than manual audit of formal verification.

[CDF](https://github.com/kudelskisecurity/cdf)Refer this for more information.


## INSTALLATION

![image](https://github.com/ananthan05/Android-Security/assets/140697378/6e389c52-b90e-46ae-8e64-4db65145801d)

```
git clone https://github.com/kudelskisecurity/cdf.git
```

![image](https://github.com/ananthan05/Android-Security/assets/140697378/b2e499fa-591d-4256-a332-4cfbf6eded70)


## First build the cdf binary.

```
make
```

![2024-06-10_09-43 1](https://github.com/ananthan05/Android-Security/assets/140697378/cfd411d2-a81f-42b3-b966-0e75cb7d35e3)


```
 make examples-all
```
 will build all the examples.
 
 while 
 ```
make examples-go
```
 will only build the Go examples.

 ![image](https://github.com/ananthan05/Android-Security/assets/140697378/66064e2e-8af8-4e82-8131-e384480ee92d)


```
make test
```
will run unit tests (of CDF).


you may want to view usage info by running 

```
cdf -h
```


You may then try an example such as the rsaenc interface against the RSA OAEP Go and CryptoPP examples. Viewing CryptoPP as our reference, you can test the Go implementation by doing:

```
cdf rsaenc /examples/oaep_rsa2048_go /examples/oaep_rsa2048_cryptopp
```
This command will perform various tests specific to the rsaenc interface.

![image](https://github.com/ananthan05/Android-Security/assets/140697378/2d5e2000-7e13-4fa5-9297-e2b7f3d07612)

![image](https://github.com/ananthan05/Android-Security/assets/140697378/19f277f4-de2d-4f1a-a7f2-e7b894dd6a27)


>In this example, CDF should complain about the maximum public exponent size the Go implementation support: if we check its code we can see the public exponent is being stored as a normal integer, whereas in CryptoPP (and most other implementations), it is stored as a big integer. This is however by design and will likely not be changed.
