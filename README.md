# summary-shopspring-decimal-func
record the readme of most used shopspring decimal func
- **`NewFromInt`**
  d := decimal.NewFromInt(42)   //แปลงint เป็นdecimal
- **`NewFromFloat`**
  d := decimal.NewFromFloat(42.42)   //แปลงfloat เป็นdecimal
- **`NewFromString`**
  d, err := decimal.NewFromString("42.42")   //แปลงString เป็นdecimal
  if err != nil {
    log.Fatal(err)
  }
## ก่อนที่จะ Add Sub Mul Div Mod Cmp Equals GreaterThan GreaterThanOrEqual LessThan LessThanOrEqual , conversion, rounding, utility, math; d1 d2 ต้องเป็น decimal แล้ว (คือ NewFrom ตามด้านบนมาก่อนแล้ว)
- **`Add`**
  sum := d1.Add(d2)
- **`Sub`**
  diff := d1.Sub(d2)
- **`Mul`**
  product := d1.Mul(d2)
- **`Div`**
  quotient := d1.Div(d2)
- **`Mod`**
  remainder := d1.Mod(d2)   e.g. 10.Mod(3) ก็ 1 remainder

- **`Cmp`**
  result := d1.Cmp(d2)    //ได้1 ถ้า d1>d2  ไม่ใช่ก็ 0
- **`Equals`**
  isEqual := d1.Equals(d2)   //true false
- **`GreaterThan`**
  isGreater := d1.GreaterThan(d2)   //true false
- **`GreaterThanOrEqual`**
  isGreaterOrEqual := d1.GreaterThanOrEqual(d2)   //true false
- **`LessThan`**
  isLess := d1.LessThan(d2)   //true false
- **`LessThanOrEqual`**
  isLessOrEqual := d1.LessThanOrEqual(d2)   //true false
  
## conversion from d
- **`convert back to String`**
  str := d.String()
- **`convert back to float64`**
  f, err := d.Float64()
  if err != nil {
      log.Fatal(err)
  }
- **`เอาเฉพาะ int หน้าทศนิยม จากตัวเลข`**
  i := d.IntPart()
- **`แปลงค่าเศษส่วน (rational number) ด้วยเมธอด Rat()`**
  **`e.g.  0.125 -> 1/8`**
  r := d.Rat()
- **`convert back to BigInt`**
  b := d.BigInt()
  
## rounding d
- **`Round ตามปกติ`**
  rounded := d.Round(2)
- **`RoundBank ปัดเศษตามกฎการปัดเศษของ Banker`**
  rounded := d.RoundBank(2)
- **`RoundCash ปัดตามช่วงเศษ ปรับตามเราต้องการ`**
- rounded1 := d1.RoundCash(5)  // d1: 2.37 ปัดเป็น 2.35 (เทียบ .35 กับ .40)
- rounded2 := d2.RoundCash(10)  // d2: 2.37 ปัดเป็น 2.40 (เทียบ .30 กับ .40)
- rounded3 := d3.RoundCash(25)  // d3: 2.37 ปัดเป็น 2.25 (เทียบ .25 กับ .50)
- rounded4 := d4.RoundCash(100)  // d4: 2.37 ปัดเป็น 2.00 (เทียบ 2 กับ 3)
- **`Truncate  เอาแค่ n หลักทศนิยม`**
  truncated := d.Truncate(2)   //d: 42.4242 ได้ 42.42

## Utility
- abs := d.Abs()
- neg := d.Neg()
- sign := d.Sign()  // ได้ 1 ถ้า positive
- exp := d.Exponential()  // เอา e ยกกำลัง dของเรา
- exp := d.Exp()  // เอา e ยกกำลัง dของเรา(เหมือนข้างบน)
- ceil := d.Ceil()  //ปัด d ขึ้น ได้เป็นจำนวนเต็ม   42.42 -> 43
- floor := d.Ceil()  //ปัด d ลง ได้เป็นจำนวนเต็ม   42.42 -> 42
- power := d.Pow(3)  //dเรา ยกกำลัง3
- sqrt := d.Sqrt()  //square root
   
