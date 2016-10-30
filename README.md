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
* การทำงานองนาฬิกาบอกเวลา : 3
![]
(http://www.plantuml.com/plantuml/img/JO_12iCW38RlUOg0jqAXrrrAjnLVOkmWLN0m5MnabB5tNupjM3pz_vSFuhIIoLJ24sxT7Vj-n9UXnGDmJwu5DGoQ1z-0A5lZwfOKhT9wFbzEtBOiUdZ4GaxDr_gGMIk4-LJoBbLI8w8GQtuEWvfs458a_-T8RcXp9XyEV41E5S0t0amkMlxM5m00)


```
@startuml
[*] --> watch

state watch#00FFFF {
  [*] ->second#FFDAB9
  second --> minute#DCDCDC 
  minute --> hour#FFDAB9 
  hour   --> date#DCDCDC
  date   --> month#FFDAB9 
  month  --> year#DCDCDC

}
watch --> [*]

@enduml
```

* การใช้งานfacebook : 4
![]
(http://www.plantuml.com/plantuml/img/SoWkIImgAStDuOhMYbNGrRLJoCbFpynJTdCpDB4qvW9pmC9fYScfIVdvsLnSG1qbgN2-ieM9kO6Rcq8rbu82p0YGYj9YPNDdDsS30oJnWlpY4apHvFpStDGyc8G2ian68XRrEPdPgLWK9-Na9sV3L7FLSi4S29O4AkBYSaZDIm7w5000)


```
@startuml
[*] --> login#FF1493
login --> facebook

state facebook#8470FF {
  [*] --> status#7CFC00
  [*] --> post#7CFC00
  [*] --> comment#7CFC00 
  [*] --> chat#7CFC00
  [*] --> like#7CFC00 
  [*] --> block#7CFC00

}
facebook --> [*]

@enduml
```

















