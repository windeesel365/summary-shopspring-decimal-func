# summary-shopspring-decimal-func
record the readme of most used shopspring decimal func
- **`NewFromInt`**
- d := decimal.NewFromInt(42)   //แปลงint เป็นdecimal
- **`NewFromFloat`**
- d := decimal.NewFromFloat(42.42)   //แปลงfloat เป็นdecimal
- **`NewFromString`**
- d, err := decimal.NewFromString("42.42")   //แปลงString เป็นdecimal
- if err != nil {
    log.Fatal(err)
  }
## ก่อนที่จะ Add Sub Mul Div Mod Cmp Equals GreaterThan GreaterThanOrEqual LessThan LessThanOrEqual; d1 d2 ต้องเป็น decimal แล้ว (คือ NewFrom ตามด้านบนมาก่อนแล้ว)
- **`Add`**
- sum := d1.Add(d2)
- **`Sub`**
- diff := d1.Sub(d2)
- **`Mul`**
- product := d1.Mul(d2)
- **`Div`**
- quotient := d1.Div(d2)
- **`Mod`**
- remainder := d1.Mod(d2)   e.g. 10.Mod(3) ก็ 1 remainder

- **`Cmp`**
- result := d1.Cmp(d2)   //ได้1 ถ้า d1>d2  ไม่ใช่ก็ 0
- **`Equals`**
- isEqual := d1.Equals(d2)   //true false
- **`GreaterThan`**
- isGreater := d1.GreaterThan(d2)   //true false
- **`GreaterThanOrEqual`**
- isGreaterOrEqual := d1.GreaterThanOrEqual(d2)   //true false
- **`LessThan`**
- isLess := d1.LessThan(d2)   //true false
- **`LessThanOrEqual`**
- isLessOrEqual := d1.LessThanOrEqual(d2)   //true false

