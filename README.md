# Report: Lab 1, Erik Solhaug

<h3>Question 1</h3>
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
<strong>Exercise 46:</strong>
```
package main

import "fmt"

func fibonacci() func() int {
  x := 0
  y := 1
  return func() int {
    x,y = y,x+y
    return x
  }
}

func main() {
  f := fibonacci()
  for i := 0; i < 10; i++ {
    fmt.Println(f())
  }
}
```
<strong>Exercise 58:</strong>
```
package main

import (
  "fmt"
  "tour/pic"
  "image/color"
)

type Image struct  {
  Width, Height int
  colr uint8
}

func (r *Image) Bounds() image.Rectangle {
  return image.Rect(0, 0, r.Width, r.Height)
}

func (r *Image) ColorModel() color.Model {
  return color.RGBAModel
}

func (r *Image) At(x, y, int) color.Color {
  return color.RGBA{r.colr+uint8(x), r.colr+uint8(y), 255, 255}
}

func main() {
  m := Image{100, 100, 128}
  pic.ShowImage(&m)
}
```
<h3>Question 2</h3>
ok (bool) is false
<h3>Question 3</h3>
You can define a "class" in golang with the use of structs:
```
type Message struct {
  Sender <type>
  Content <type>
}
```
<h3>Question 4</h3>
```
func CheckForError(m Message) (err, error) {}
```
<h3>Question 5</h3>
Source code can be found on Github
