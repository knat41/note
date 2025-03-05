# รวมที่จดมาเมื่อครั้งอบรม kidbright forcast
1. การเข้าใจเรื่องฤดูกาล

ฤดูฝนภาคใต้ ฤดูหนาวภาคเหนือ

2. กระแสลม
ถ้ามันจะมีฝนมันต้องมีลม

3. เฆต การดูว่าเมฆจะสร้าง อากาศเย็นได้ไหม

 note แสดงว่าต้องมีการแสดงความรู้ ในการแข่งขัน
เช่นที่ว่า โอโซน ถ้าบอกว่าไปสูดแล้ว จะโดนหักคะแนน

ดาวเทียวทางอุตุนิยม
geostationary เห็น domain คงที่ (ดาวเทียมค้างฟ้า)
polar-orbiting (landsat-8)

แนวการถ่ายภาพ มีลักษณะเป็นแถบ ไม่ครอบคลุม ไม่มีภาพถ่ายทุกตำแหน่ง

TIFF file 

worldview.earthdata.nasa.gov

ให้ตรวจสอบดูว่ามีการกระทำแบบใดบ้าง 

 
 ข้อมูลฝุ่น
https://drive.google.com/file/d/10610N98HX0E-5UdmKUotCaDFGvG-X5ME/view?usp=sharing
ข้อมูลสภาพอากาศ
https://drive.google.com/file/d/1Q32Yotqtfv333vidjf_k1uWfYIh_07hi/view?usp=sharing


https://bit.ly/3vb3e9o

http://forecast.netpie.io:3000/login
ChiangMai

http://forecast.netpie.io:8086
nectec-org
GOgLxJURrMp1PGOAk8_WL1svsFBj-H-vqsDjeVNj_jcub3n6R4GFNj7iUoHaStV07ULWRjhiBQcrNtml8ubThQ==


from(bucket: "ChiangMai")
|> range(start: v.timeRangeStart, stop: v.timeRangeStop)
|> filter(fn: (r) => r["_measurement"] == "CHM001")
|> filter(fn: (r) => r["_field"] == "temperature")
|> aggregateWindow(every: v.windowPeriod, fn: last, createEmpty: false)
|> yield(name: "last")

humidity

from(bucket: "ChiangMai")
|> range(start: v.timeRangeStart, stop: v.timeRangeStop)
|> filter(fn: (r) => r["_measurement"] == "MOU008")
|> filter(fn: (r) => r["_field"] == "humidity")
|> aggregateWindow(every: v.windowPeriod, fn: last, createEmpty: false)
|> yield(name: "last")

from(bucket: "ChiangMai")
|> range(start: v.timeRangeStart, stop: v.timeRangeStop)
|> filter(fn: (r) => r["_measurement"] == "CM-LS-242")
|> filter(fn: (r) => r["_field"] == "humidity")
|> aggregateWindow(every: v.windowPeriod, fn: last, createEmpty: false)
|> yield(name: "last")
https://www.chonkanya.ac.th/HeadCover.png
