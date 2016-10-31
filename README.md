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

* การพิมพ์งานเอกสาร : 5

![]
(http://www.plantuml.com/plantuml/img/JO_R2eCm343VynK5tmP24TdjOIY8Fp76w6nnihKfCJBy-xMiEjzo3k64L2Chuic-uRgxYJo_2FJ6PMrzb8S2uYpEmY6R1-9hOK_Oax9_71mRWX_7XXtl7oITjMLTxYKa3AjQiHB6CSrRYTraWrnLJAHeriX2dYGaNAvj-OcC7VfvSFsgOo4y150PfyDtNm00)

```
@startuml
[*] --> open#FA8072
open : notebook
open : program
open : printer

open --> ms_word#F4A460
ms_word : data entry
ms_word : document
ms_word --> printer#D02090
printer : print
printer : photocopying
printer --> [*]

@enduml
```

Activity Diagram 5 รูป

 * การเลือกใช้ทางด่วนกับไม่ใช้ : 1
 
 ![](http://www.plantuml.com/plantuml/img/NOzD3e9034RNz1JDi54J4jo8AuAYN8Auc407nmm_cIbHRc_5bQxQz7rzJOl0slFSEzZijfZa4QhMUcfOHN5LdG_b7i0QLFIQF8Nmr8j2ljC0Y4cIr-ndkltG-9YLr-eKmJU1Qj8BykXSM8sNB4rNucrtP-5o5iW5-WppscXfHSXU6sCRVEZ-trYxSUYGRI-vTNbehG4efCeRRm00)
 
```
@startuml
(*) ->	 "direct"	#FFB6C1

if "expressway" then
  -->[true] "expressway"#87CEFA	

  --> "pay tolls"	#FFD700
  --right-> (*)
else
  ->[false] "traffic jam"#87CEFA	

  -->[long time] (*)
endif

@enduml
```

* การติดต่อสื่อสาร : 2

![](http://www.plantuml.com/plantuml/img/XL71QiCm33tFNo6SopOeU2jZwQKqnSrFb1rCgb23Oez4RN-_icEwzb1c30RflQVtvCt4RkJJG4gzlh_1Oh46tuFkuZ2SWkySemO-Ob0AKdFFIFXxZ05_1EI8z4jbRMEibRxSn2q4a2Dg6GNdw3jHSXEuPRMgs-sg5W3IX1cNHoPSxpgyuui2OSz99dM0_O0oiMrgy_rP4CcNE1FtkN3Jp7v1dmy-GjR-ZnWElbT_hyfAAVPw7wB4lOoUyJwla3KXCuvIDSRkxCTSdINLhAJSyhRMieQIB_kJXPAkshRvCaOzc2f9SeZ40_81dq3dIHjvvIkl)

```
@startuml

(*) --> if "communicate" then

  -->[telephone] "call"	#DDA0DD
  
  if "" then
    -> "call voice" as a3#98FB98
  else
    if "call face" then
      -left-> "face time"	#FA8072
        ---->(*)
    else
      --> "vdio call "	#FA8072
        ---->(*)
    endif
  endif
  
else

  ->[no] "write"	#DDA0DD
  -->"letter"	#00DED1
  -->(*)
  
endif

a3 --> if "voice" then
  --> "tell"#FFA500
    ---->(*)
else
  -> "voice line"#FFA500
    ---->(*)
endif

@enduml
```


* การท่องเที่ยว : 3

![](http://www.plantuml.com/plantuml/img/XP71IWCn48RFpLCCxKM57cgX4EWkxKeNl8ZG9nYxSGrDCcKsMr7ntPt4eaiHcqiottpyoP1L5v5ZxvrItTw60p9wUCBTlcNgGtD7ZXWcwtKjQs3WBjgZZM_meG2sAU9a9cy-5rWXVwEHCAqN2s6Rdy21TdPLahN-epEQQ5tNEQSYRimf_j5mBwYc41_G6xZt1tcS-bJgwkOQfjCInf7nQDmObakeJ6i3bALAZQ8eO3jBMoxVYNxnRSO39KUzOZJyZCxz8wPEP_22uMMmY3QSQwbi2Lx8ctoM8PHQcT385tq1)


```
@startuml

skinparam backgroundColor #AAFFFF
skinparam activity {
  StartColor #FFFF33
  BarColor 	#FF9966
  EndColor #FFFF33
  BackgroundColor #FF9999
  BackgroundColor 	#99FF66
  BorderColor Peru
  FontName Impact
}

(*) --> "travel" << Begin >>
--> === S1 ===
--> zoo
--> === S2 ===
 === S1 === --> waterfall
--> === S2 ===
 === S1 ===--> sea
--> === S2 ===
 === S1 ===--> mountain
--> === S2 ===
--> go home
--> (*)

@enduml
```









