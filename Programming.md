# 🧑‍🏫 แนวทางการเขียนโปรแกรม (Style Guide) - CN

> วิชา: Introduction to Computer Science and Programming in Python

---

## 1. จำนวนเต็ม (Integer) และจำนวนทศนิยม (Float)

* หลีกเลี่ยงการใช้ float ในการเปรียบเท่ากัน (`==`) เนื่องจากอาจเกิดความคลาดเคลื่อน เช่น `0.1 + 0.1 + 0.1 ≠ 0.3`
```python
variable = 0.0
while variable != 0.3:
    variable += 0.1
```
* ใช้ `int` สำหรับการนับ
* ควรแปลงชนิด (`typecast`) อย่างถูกต้องก่อนการหาร เช่น `float(3)/5` ไม่ใช่ `float(3/5)`

---

## 2. `for` กับ `while`

* ใช้ `for` เมื่อรู้จำนวนรอบแน่นอน เช่น การวนลูป 500 ครั้ง
* ใช้ `while` เมื่อรอเงื่อนไขใดเงื่อนไขหนึ่ง เช่น รับ input จนถูกต้อง
* ใช้ `break` ออกจากลูปเมื่อได้คำตอบแล้ว เพื่อเพิ่มประสิทธิภาพ

---

## 3. การตรวจสอบค่า Boolean

* ไม่ควรใช้รูปแบบ `if my_function() == True:`
  ให้ใช้ `if my_function():` แทน
* หากต้องการกลับค่าจาก boolean ให้ใช้ `not` เช่น `return not my_function()`

---

## 4. การใช้ Docstring

* ใส่ docstring ให้กับ class และ function เพื่ออธิบายจุดประสงค์
* ช่วยให้ผู้อื่นเข้าใจและเรียกดูคำอธิบายได้ผ่าน interactive shell

```python
class TitleTrigger(WordTrigger):
    """
    Subclass ของ WordTrigger สำหรับตรวจสอบคำใน title ของข่าว
    """
```

---

## 5. หลีกเลี่ยงการแก้ไข collection ขณะวนลูป

* การเพิ่มหรือลบจาก list ขณะวนลูป อาจทำให้ข้ามบางค่าหรือวนลูปไม่จบ
* ```python
  elems = ['a', 'b', 'c']
  for e in elems:
      print e
  elems.remove(e)
```
* แนวทางที่ดีกว่า:

  * วนลูปผ่านสำเนา: `for item in list_copy`
  * สร้าง list ใหม่แล้วเลือกเฉพาะค่าที่ต้องการเก็บไว้

---

## 6. การเข้าถึงตัวแปรภายใน class โดยตรง

* ไม่ควรใช้ `story.title` โดยตรง
* ควรใช้ method เช่น `story.get_title()` แทน เพื่อไม่ผูกกับโครงสร้างภายในของ class

---

## 7. การเรียก constructor ของ superclass จาก subclass

* ควรใช้ `superclass.__init__()` เพื่อ reuse code
* ป้องกันข้อผิดพลาดจากการใช้ตัวแปรชื่อไม่ตรง
* ตัวอย่างที่ดี:

```python
class ResistantVirus(SimpleVirus):
    def __init__(self, maxBirthProb, clearProb, resistances, mutProb):
        SimpleVirus.__init__(self, maxBirthProb, clearProb)
        self.resistances = resistances
        self.mutProb = mutProb
```

---

## 8. ข้อควรระวังในการเก็บ object ลงในโครงสร้างข้อมูล

* Python เปรียบเทียบ object ด้วยตำแหน่งในหน่วยความจำ (default)
* ใช้ tuple เช่น `(x, y)` แทน object เช่น `Position(x, y)` เพื่อเปรียบเทียบได้ถูกต้อง
* ทางที่ดีควรใช้ `tuple` หรือ override method `__eq__` และ `__hash__`

---

## 9. ควรใช้โครงสร้างข้อมูลแบบใด?

| โครงสร้างข้อมูล             | ข้อดี                      | ข้อเสีย                               |
| --------------------------- | -------------------------- | ------------------------------------- |
| `list` ของ tuple            | ใช้ง่าย                    | ค้นหาช้า, เก็บสถานะแบบ boolean แบบแฝง |
| `set` ของ tuple             | เร็ว, ไม่มีซ้ำ             | ยังเก็บ boolean แบบแฝง                |
| list of lists (matrix)      | ชัดเจน                     | indexing ซับซ้อน                      |
| `dict` เช่น `{(x,y): True}` | ยืดหยุ่นที่สุด, อัปเดตเร็ว | -                                     |

**คำแนะนำ**: คิดก่อนเลือกโครงสร้างข้อมูลที่เหมาะกับปัญหา

---

## 📚 แหล่งอ้างอิง

* MIT OpenCourseWare

---

---
[C programming](C%20programming.md)
[Programming solve](Programming%20solve.md)
[[Python programming]]


[[]]
