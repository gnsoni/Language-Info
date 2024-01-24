# Language Performace
The project is created as reference for the performance of programing languages, simply counts upto ten million (10000000) and corresponding elapsed time is logged in output.

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


## Go, 
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


## C#, the one I am using for over 15 years
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


## Python, Interpreted language
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
    Elapsed time: 0:10:50.824000ms
