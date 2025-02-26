# การใช้งาน latex

## font ที่ทดสอบแล้วไม่มีปัญหาสระลอย 
### ทดสอบบน article
#### กลุ่มดีที่สุด ไม้เอก โท ไม่ลอย
* CS PraJad
#### กลุ่มพอใช้ได้ ไม้เอก โท ลอย ตำแหน่งตรง
* Laksaman
#### กลุ่มเหมือนจะใช้ได้ ไม้เอก โท ลอย ตำแหน่งเยี้องออกขวา
* TH Sarabun New

### ทดสอบบน book
#### กลุ่มดีที่สุด ไม้เอก โท ไม่ลอย
* ไม่มี
#### กลุ่มพอใช้ได้ ไม้เอก โท ลอย ตำแหน่งตรง
* Laksaman
#### กลุ่มเหมือนจะใช้ได้ ไม้เอก โท ลอย ตำแหน่งเยี้องออกขวา
* TH Sarabun New
#### กลุ่ม error หาไม่เจอ
*  CS PraJad

convert markdown to pdf
* https://pandoc.org/
From markdown to PDF:
```linux
pandoc MANUAL.txt --pdf-engine=xelatex -o example13.pdf
```
PDF with numbered sections and a custom LaTeX header:
```linux
pandoc -N --variable "geometry=margin=1.2in" --variable mainfont="Palatino" --variable sansfont="Helvetica" --variable monofont="Menlo" --variable fontsize=12pt --variable version=2.0 MANUAL.txt --include-in-header fancyheaders.tex --pdf-engine=lualatex --toc -o example14.pdf
```
