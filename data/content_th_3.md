22

ระดับแรงดันที่จ่ายให้มอเตอร์สูงขึ้น ระยะเวลา t<sub>ON</sub> จะกว้างจนถึงระดับแรงดันอ้างอิง วงจรสับไฟฟ้าจะมีอุปกรณ์เปรียบเทียบแรงดันอินพุตและเอาต์พุต เพื่อตรวจสอบสภาวะการทำงานของวงจรให้ได้ระดับแรงดันที่ต้องการในการควบคุมการทำงานของมอเตอร์ ซึ่งจะได้กล่าวถึงแนวคิดการออกแบบในหัวข้อต่อไป

**2.6 แนวคิดการออกแบบอุปกรณ์จำกัดกระแสของแบตเตอรี่**
เมื่อนำแบตเตอรี่มาต่ออนุกรมเข้าด้วยกัน 4 ลูก เพื่อให้ได้แรงดัน 48 Vdc โดยมีความจุเท่ากับ 1 ลูกเท่านั้นคือ 65 Ah เพื่อเพิ่มระยะเวลาการจ่ายกระแสให้ยาวนานขึ้นจึงนำแบตเตอรี่ 4 ลูก ต่ออนุกรมกันมาขนานเข้าด้วยกัน 2 ชุด แบตเตอรี่มีความไม่เป็นเชิงเส้นและแต่ละลูกก็มิได้มีพลังงานสะสมเท่ากันอย่างสมบูรณ์แบบ แบตเตอรี่ที่มีพลังงานสะสมต่ำกว่าจะกลายสภาพเป็นการอยู่ช่วงเวลาหนึ่ง เมื่อต่อร่วมกับแบตเตอรี่ที่มีพลังงานสะสมสูงกว่า จนกระทั่งแบตเตอรี่ที่มีพลังงานมากกว่าจะปรับสภาพตัวเองให้มีความสามารถจ่ายพลังงานได้ใกล้เคียงกับลูกที่มีพลังงานน้อยกว่า ดังนั้นจึงต้องมีอุปกรณ์ที่จำกัดหรือควบคุมให้มีการจ่ายพลังงานที่เท่า ๆ กันโดยไม่ให้แบตเตอรี่ลูกใดลูกหนึ่งกลายเป็นภาระแก่กันซึ่งสามารถใช้หลักการของการแบ่งกระแส ดังแสดงในภาพที่ 2.24 กระแสที่ไหลผ่าน R<sub>1</sub> คือกระแสที่ต้องการควบคุมไม่ให้เกินขนาด เมื่อนำอัตราการขยายของทรานซิสเตอร์ Q<sub>1</sub> มาหารจะได้กระแสที่จะใช้ในการไบแอส Q<sub>1</sub> เพื่อที่จะควบคุมไม่ให้ทรานซิสเตอร์ Q<sub>1</sub> นำกระแสเกินที่ได้ตั้งไว้ โดยใช้สัดส่วนของความต้านทาน R<sub>2</sub> และ R<sub>3</sub> เป็นตัวควบคุมกระแสไบแอสให้กับวงจร

```mermaid
graph LR
 subgraph Circuit
 Vin[+] --o --- R1 --- Q1_Base --- Q1_Collector --- Vout[+ o]
 Vin[-] --o --- R2 --- Q1_Emitter --- R3 --- Ground(( ))
 Q1_Base --- Q1_Emitter_Internal[Internal Emitter]
 Q1_Collector --- Q1_Base_Internal[Internal Base]
 Q1_Base_Internal --- Q1_Emitter_Internal
 Q1_Emitter_Internal --- Q1_Emitter
 Q1(( )) --- Q1_Base[Base]
 Q1 --- Q1_Collector[Collector]
 Q1 --- Q1_Emitter[Emitter]
 label[Darlington] --o Q1
 end
style Q1 fill:none,stroke:#000,stroke-width:2px
style Vin fill:none,stroke:none
style Vout fill:none,stroke:none
style Ground fill:none,stroke:#000,stroke-width:2px
style R1 text:R₁,fill:none,stroke:none
style R2 text:R₂,fill:none,stroke:none
style R3 text:R₃,fill:none,stroke:none
style label text:Darlington,fill:none,stroke:none

linkStyle 0 stroke-width:1px,stroke:#000
linkStyle 1 stroke-width:1px,stroke:#000
linkStyle 2 stroke-width:1px,stroke:#000
linkStyle 3 stroke-width:1px,stroke:#000
linkStyle 4 stroke-width:1px,stroke:#000
linkStyle 5 stroke-width:1px,stroke:#000,stroke-dasharray: 5 5
linkStyle 6 stroke-width:1px,stroke:#000,stroke-dasharray: 5 5
linkStyle 7 stroke-width:1px,stroke:#000,stroke-dasharray: 5 5
linkStyle 8 stroke-width:1px,stroke:#000,stroke-dasharray: 5 5
linkStyle 9 stroke-width:1px,stroke:#000
linkStyle 10 stroke-width:1px,stroke:#000
linkStyle 11 stroke-width:1px,stroke:#000
linkStyle 12 stroke-width:1px,stroke:#000,stroke-dasharray: 5 5

%% Diagram Representation
%% V_in+ o----vvv(R1)----o(Base Q1)----o(Collector Q1)----o V_out+
%%                      |              |
%%                      |              | Darlington Symbol
%%                      |              |
%% V_in- o----vvv(R2)----o(Emitter Q1)---vvv(R3)----(Ground)
```

***

*ภาพที่ 2.24 วงจรจำกัดกระแสแบบดาร์ลิงตัน*

**2.7 แนวคิดการออกแบบอุปกรณ์ปรับเปลี่ยนระดับพลังงานแบตเตอรี่**
จากหัวข้อที่ 2.5 ในการขับเคลื่อนมอเตอร์กระแสตรงชนิดวงจรสนามแยกส่วนในงานวิจัยนี้จะต้องปรับระดับแรงดันของแบตเตอรี่ที่ป้อนมอเตอร์ให้มีค่า 220 Vdc ตามพิกัดของมอเตอร์ การปรับเปลี่ยนระดับแรงดันแบตเตอรี่จาก 48 Vdc ไปเป็น 220 Vdc เริ่มจากการออกแบบวงจรที่แปลงไฟฟ้ากระแสตรงเป็นกระแสสลับ โดยอาศัยการสับไฟฟ้าที่ความถี่ตามที่ต้องการ ในงานวิจัยนี้จะ
