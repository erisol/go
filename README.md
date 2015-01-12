# Report: Lab 1

<h2>Question 1</h2><br>
<strong>Exercise 43:</strong>
```
package main

import (
  "fmt"
  "math"
)

func Sqrt(x float64) float64 {
  z := float64(2.)
  s := float64(0)
  for {
    z = z - (z*z - x)/(2*z)
    if math.Abs(s-z) < 1e-15 {
      break
    }
    s = z
  }
  return s
}
func main() {
  fmt.Println(Sqrt(2))
  fmt.Prinln(math.Sqrt(2))
}
```
