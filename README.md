# Language comparision
I have been predomently developing software on Microsoft and related technology for over 20 year now, few years back I migrated my personnal monolith VB 6 winform project to ASP.Net core api as backend with Angualr as frontend. 

Now days the open source projects are not limited to personal projects but also many business are now adopting open source projects.

- __C++__
  > C/C++ are Low-level programming languages, any higher level legnguage can't compete in terms of performance, and reliablity however this language are not simple to read and understand at first sign.
   
- __Go__
  > Go is a statically typed, compiled high-level programming language.
 
- __C#__
  > C# is higher-level compiled programing language, .Net frame work is needed to host the applicaton at run time.

- __Java__
  > Java is compiled high-level programing langaugage. JVM is needed to host the applicaton at run time.

- __Python__
  > Python is an interpreted high-level, general-purpose programming language.

-----------------

|               | OOP Standard  | Low level     | High level    | Interpreted   | Output       | Note                                                                   |
| ------------- | ------------- | ------------- |-------------- | ------------- | ------------ | ---------------------------------------------------------------------- |
| C/C++         |    &check;    |    &check;    |               |               | Machine code | Compiled to matchine code.                                             |
| Go            |               |               |    &check;    |               | Machine code | Compiled to matchine code.                                             |
| C#            |    &check;    |               |    &check;    |               | Byte code    | Compiled to byte code which can only invoked with .Net framework       |
| Java          |    &check;    |               |    &check;    |               | Byte code    | Compiled to byte code which can only invoked though JVM                |
| Python        |    &check;    |               |               |    &check;    | N/A          | Follows OOP.                                                           |

-----------------

## Execution test
Although this comparision of tasks ran on same workstation and with similar sort of load, but this is not valid comparision as below languages are dominating different domains. The project is for my personal reference, it simply counts upto ten million (10000000) and corresponding elapsed time is logged in output.

## C++
```
#include <chrono>
#include <iostream>
#include <thread>
 
int main()
{
    using namespace std::chrono_literals;

    const auto sttm = std::chrono::high_resolution_clock::now();

    int counter = 0;
    do
    {
        counter++;
    } while (counter < 10000000);

    const auto etm = std::chrono::high_resolution_clock::now();
    const std::chrono::duration<double, std::milli> elapsed = etm - sttm;
 
    std::cout << "Elapsed time: " << elapsed << '\n';
}
```
### Output
    Elapsed time: 0.001272ms


## Go 
```
package main

import (
	"fmt"
	"time"
)

func main() {
	var sttm = time.Now()
	var i int64
	for i < 10000000 {
		i++
	}
	var etm = time.Now()

	fmt.Println("Elapsed time: ", etm.Sub(sttm).Milliseconds(), " ms")

}
```
### Output
    Elapsed time:  0.0032457 ms


## C#
```
using System;

internal class Program
{
    static void Main(string[] args)
    {
        DateTime sttm, etm;
        int icounter = 0;

        sttm = DateTime.Now;

        for(icounter = 0; icounter < 10000000; icounter++)
        {
        }

        etm = DateTime.Now;

        Console.WriteLine($"Elapsed time: {sttm.Subtract(etm)}ms" );
    }
}

```
### Output
    Elapsed time: 00:00:00.0312505ms


## Java
```

```
### Output
    Elapsed time: tbc


## Python
```
import datetime
sttm = datetime.datetime.utcnow()
i = 1

while i < 10000000:
  i += 1

etm = datetime.datetime.utcnow()

delta = (etm - sttm)

print("Elapsed time: " + str(delta * 1000) + "ms")
```
### Output
    Elapsed time: 0:00:10.824000ms
