# OOAD-WEEK11
State Diagram

State Diagram
* การทำงานของPower Bank : 1

![]
(http://www.plantuml.com/plantuml/img/SoWkIImgAStDuUAArefLqDMrKqZEI2nAJurFIYmfIIsgL7PsTWC2BYueFpudlrm1GnKN5ofVmKeX8ByyjIWuiImLXvHFVZc6Bh3r-NbvgSabgIdn9Vdn9HcfyGKP-NcfocPcRcxEpbpOPS4QaHm8TBIniO41Yfkje4w6gSDbb9K2X8QeBi9d8p34kBWSKlDIWE470000)

```
@startuml

[*] --> charge_battery#CCFFFF

battery_low -> charge_battery

charge_battery : PowerSave
charge_battery : PowerLow

charge_battery --> connected_to_the_phone#66FFCC
connected_to_the_phone --> battery_low#CC3300
battery_low : charge battery
connected_to_the_phone : phone charger
connected_to_the_phone --> [*]

@enduml

```
* การใช้งานลิฟท์ : 2
![]
(http://www.plantuml.com/plantuml/img/TL5D2uCm3BttLmIy3GGPOvixoDHEs6yOGyHsGr0hjiN3yBylZRelM2z9Nj_BQzAZDaLlR5CpTbbTmVSZgAkROGnn8odtE8y3pk7108WJmLdK4YiNl5CORdSnAU_AgDngsSC1Xg8oI7bZNfQbGPg0Bv2fEjaYYS9DzK2YKZMkAw4UNoURVUhCobffkTIpfcZ5X8CJJ9bxWUroeOQMq3b_-VwpLTPyDt5ZBHECooPeXDzD8BdhfTQvxSWg238yUFk98icrUb-w2bwB7jbHjW9_u0a0)


```
@startuml

[*] --> lift

state lift#DDA0DD {
  [*] -> Idle
  Idle#E9967A --> goto_user : wait
   goto_user#FFC0CB -d-> open : open for user come
   open#D2B48C -> close#D2B48C : open and close 
   close --> up_down 
   up_down#FFC0CB --> open : open for user out
   close --> Idle : wait
}

state user#DDA0DD {
  [*] --> press_updown#00FFFF
  press_updown-> wait#00FFFF
  wait -> lift

}
@enduml
```
