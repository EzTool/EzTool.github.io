# Jemeter

[YouTube:【DevOps 線 11】透過 Azure DevOps 執行 JMeter Load Test](https://www.youtube.com/watch?v=wQWog1Pm74A)

## 工具
* [非常詳細的Fiddler工具使用說明（包含APP抓包）](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/32041/)
* [Web Testing with JMeter: How To Properly Handle Embedded Resources in HTML Responses](https://www.blazemeter.com/blog/web-testing-jmeter-how-properly-handle-embedded-resources-html-responses)
* [[效能調教] 使用 JMeter 作為網站效能參考指標](https://dotblogs.com.tw/wasichris/2017/06/06/013503)

## 畫面

鹿哥給的路徑
* [TCS](
https://tw-tpeweb521.asia.pwcinternal.com/SitePages/OAPortalAgent.aspx?AppName=MailLinkUrl*Url={{ASRWebServer}}/PwCTW/Client/Service/Confirmation/WebUI_Branch/?Action{e}GetPage{a}Namespace{e}Confirmation.Form{a}CertID{e}{{CertID}}{a}ClientIP{e}{{ClientIP}}*Width=480*Height=330
)
會轉到這裡()
* [TCS](https://tw-tpeapp507.asia.pwcinternal.com/PwCTW/Client/Service/Confirmation/WebUI_Branch/SmartPage/ExecAction?Action=GetPage&K=aa74a602-111b-4210-91d1-f88c5cf3164e&Namespace=Confirmation.Form&w=202D60E0-01C5-44CB-9881-943FFE2260C9)


https://tw-tpeweb521.asia.pwcinternal.com/SitePages/OAPortalAgent.aspx?AppName=MailLinkUrl*Url=%7B%7BNewWebServer%7D%7D/PwCTW/BusinessManagement/SparkPortal/WebUI/?Action%7Be%7DGetPage%7Ba%7DNamespace%7Be%7DPortal.Menu%7Ba%7DMenuNamespace%7Be%7DPwCTW.Client.Service.Confirmation.ApplyWeb_Branch%7Ba%7DCertID%7Be%7D%7B%7BCertID%7D%7D%7Ba%7DClientIP%7Be%7D%7B%7BClientIP%7D%7D


https://tw-tpeweb521.asia.pwcinternal.com/SitePages/Login.aspx?CertID=768491744574578&User=ATS
https://tw-tpeweb521.asia.pwcinternal.com/SitePages/Login.aspx?CertID=768479940707181&User=ALL



cookie: _ga=GA1.2.447442258.1585535042; rxVisitor=1588900378289F92PUKH99V2P7D7EFNCQJ80DEBEDQILI; dtLatC=939; dtSa=false%7C_load_%7C1%7C_load_%7C-%7C1588900375368%7C100378274_971%7Chttps%3A%2F%2Fhkg.fedsvc.pwcinternal.com%2Fofis%2F%3Fwa%3Dwsignin1.0%26wtrealm%3Dofis_253apwc_253abroker%26wct%3D2020-05-08T01_253a12_253a56Z%26wctx%3Dhttps_253a_252f_252fpwc-spark.com%7CWorking...%7C1588900378274%7C%7C; dtCookie=v_4_srv_74_sn_31C23D5A7139223DF653A1D5A69764C0_perc_100000_ol_0_mul_1_app-3Aea7c4b59f27d43eb_0; rxvt=1588902178562|1588900378293; dtPC=74$100378274_971h-vHAHCMPCHHWHKCJTHMFNLTMKPAQFGJLCT-0; ASP.NET_SessionId=s5yhaulsn0jvitmn3tmyws0q; aa74a602-111b-4210-91d1-f88c5cf3164e1=2020/05/07 11:37:43; aa74a602-111b-4210-91d1-f88c5cf3164e2=ZzkNOoKVqAZlyHaI%2bi0qCQ%3d%3d; aa74a602-111b-4210-91d1-f88c5cf3164e3=13fjC0TgLNSTOL7xiEH%2bBQ%3d%3d; __RequestVerificationToken_L1B3Q1RXL0NsaWVudC9TZXJ2aWNlL0NvbmZpcm1hdGlvbi9XZWJVSV9CcmFuY2g1=I-w33Qv4XVcKAY5GARDOUwCWVVzw2zuOk0hEPIV0HqWXIQHTA9zZoTs0ILphkGBkHn8H9jnw8V7vyA6nHyu-i0FHrmNFnj77JMrTF-Vw9dI1; c5be9617-2f24-4bcf-94a4-76310f7997121=2020/05/07 11:37:43; c5be9617-2f24-4bcf-94a4-76310f7997122=6uXWGJI4LumEkBgwPOUG%2bQ%3d%3d; c5be9617-2f24-4bcf-94a4-76310f7997123=mGWFUn%2b7MbRlHh3A6KOPXg%3d%3d

ALL：
aa74a602-111b-4210-91d1-f88c5cf3164e1=2020/05/07 11:37:43; aa74a602-111b-4210-91d1-f88c5cf3164e2=ZzkNOoKVqAZlyHaI%2bi0qCQ%3d%3d; aa74a602-111b-4210-91d1-f88c5cf3164e3=13fjC0TgLNSTOL7xiEH%2bBQ%3d%3d; __RequestVerificationToken_L1B3Q1RXL0NsaWVudC9TZXJ2aWNlL0NvbmZpcm1hdGlvbi9XZWJVSV9CcmFuY2g1=I-w33Qv4XVcKAY5GARDOUwCWVVzw2zuOk0hEPIV0HqWXIQHTA9zZoTs0ILphkGBkHn8H9jnw8V7vyA6nHyu-i0FHrmNFnj77JMrTF-Vw9dI1; c5be9617-2f24-4bcf-94a4-76310f7997121=2020/05/07 11:37:43; c5be9617-2f24-4bcf-94a4-76310f7997122=6uXWGJI4LumEkBgwPOUG%2bQ%3d%3d; c5be9617-2f24-4bcf-94a4-76310f7997123=mGWFUn%2b7MbRlHh3A6KOPXg%3d%3d

ALL:
Action: GetPage
K: aa74a602-111b-4210-91d1-f88c5cf3164e
Namespace: Confirmation.Form
w: CFE8969D-08CB-4545-85FD-C84A07747BCD


cookie: _ga=GA1.2.447442258.1585535042; rxVisitor=1588900378289F92PUKH99V2P7D7EFNCQJ80DEBEDQILI; dtLatC=939; dtSa=false%7C_load_%7C1%7C_load_%7C-%7C1588900375368%7C100378274_971%7Chttps%3A%2F%2Fhkg.fedsvc.pwcinternal.com%2Fofis%2F%3Fwa%3Dwsignin1.0%26wtrealm%3Dofis_253apwc_253abroker%26wct%3D2020-05-08T01_253a12_253a56Z%26wctx%3Dhttps_253a_252f_252fpwc-spark.com%7CWorking...%7C1588900378274%7C%7C; dtCookie=v_4_srv_74_sn_31C23D5A7139223DF653A1D5A69764C0_perc_100000_ol_0_mul_1_app-3Aea7c4b59f27d43eb_0; rxvt=1588902178562|1588900378293; dtPC=74$100378274_971h-vHAHCMPCHHWHKCJTHMFNLTMKPAQFGJLCT-0; ASP.NET_SessionId=s5yhaulsn0jvitmn3tmyws0q; aa74a602-111b-4210-91d1-f88c5cf3164e1=2020/05/07 11:37:43; aa74a602-111b-4210-91d1-f88c5cf3164e2=ZzkNOoKVqAZlyHaI%2bi0qCQ%3d%3d; aa74a602-111b-4210-91d1-f88c5cf3164e3=13fjC0TgLNSTOL7xiEH%2bBQ%3d%3d; __RequestVerificationToken_L1B3Q1RXL0NsaWVudC9TZXJ2aWNlL0NvbmZpcm1hdGlvbi9XZWJVSV9CcmFuY2g1=I-w33Qv4XVcKAY5GARDOUwCWVVzw2zuOk0hEPIV0HqWXIQHTA9zZoTs0ILphkGBkHn8H9jnw8V7vyA6nHyu-i0FHrmNFnj77JMrTF-Vw9dI1; c5be9617-2f24-4bcf-94a4-76310f7997121=2020/05/07 11:37:43; c5be9617-2f24-4bcf-94a4-76310f7997122=6uXWGJI4LumEkBgwPOUG%2bQ%3d%3d; c5be9617-2f24-4bcf-94a4-76310f7997123=mGWFUn%2b7MbRlHh3A6KOPXg%3d%3d; fa0d5aa6-dd14-459d-ad90-164f9e4abc9a1=2020/05/07 11:37:43; fa0d5aa6-dd14-459d-ad90-164f9e4abc9a2=63k5VDeNFQhFaaK6j3UBag%3d%3d; fa0d5aa6-dd14-459d-ad90-164f9e4abc9a3=tY7zmE7j0Ye24P0cfBTyzw%3d%3d

ATS:
fa0d5aa6-dd14-459d-ad90-164f9e4abc9a1=2020/05/07 11:37:43; fa0d5aa6-dd14-459d-ad90-164f9e4abc9a2=ZzkNOoKVqAZlyHaI%2bi0qCQ%3d%3d; fa0d5aa6-dd14-459d-ad90-164f9e4abc9a3=13fjC0TgLNSTOL7xiEH%2bBQ%3d%3d; __RequestVerificationToken_L1B3Q1RXL0NsaWVudC9TZXJ2aWNlL0NvbmZpcm1hdGlvbi9XZWJVSV9CcmFuY2g1=I-w33Qv4XVcKAY5GARDOUwCWVVzw2zuOk0hEPIV0HqWXIQHTA9zZoTs0ILphkGBkHn8H9jnw8V7vyA6nHyu-i0FHrmNFnj77JMrTF-Vw9dI1; c5be9617-2f24-4bcf-94a4-76310f7997121=2020/05/07 11:37:43; c5be9617-2f24-4bcf-94a4-76310f7997122=6uXWGJI4LumEkBgwPOUG%2bQ%3d%3d; c5be9617-2f24-4bcf-94a4-76310f7997123=mGWFUn%2b7MbRlHh3A6KOPXg%3d%3d;

ATS:
Action: GetPage
K: fa0d5aa6-dd14-459d-ad90-164f9e4abc9a
Namespace: Confirmation.Form
w: 2B1A68CE-32C6-49C7-84EC-FBA87E6D09B0



cookie: _ga=GA1.2.447442258.1585535042; rxVisitor=1589154575281US4RCJRPDE7UT9KB8HPM7OL15J38AFUS; dtPC=72$354575271_49h1vSPEURREEEDPUPHKCCKGAEVBMLKSCSDFQ-0; dtLatC=1150; dtSa=false%7C_load_%7C1%7C_load_%7C-%7C1589154572089%7C354575271_49%7Chttps%3A%2F%2Fhkg.fedsvc.pwcinternal.com%2Fofis%2F%3Fwa%3Dwsignin1.0%26wtrealm%3Dofis_253apwc_253abroker%26wct%3D2020-05-10T23_253a49_253a31Z%26wctx%3Dhttps_253a_252f_252fpwc-spark.com%7CWorking...%7C1589154575271%7C%7C; dtCookie=v_4_srv_72_sn_F7762E5056D7F22532306FD30F698E3C_perc_100000_ol_0_mul_1_app-3Aea7c4b59f27d43eb_0; rxvt=1589156375776|1589154575285; ASP.NET_SessionId=roll4kihg0i0lxwf4lbrzew4; e7e18b68-fbba-43c2-b329-ad7b7822af981=2020/05/07 11:37:43; e7e18b68-fbba-43c2-b329-ad7b7822af982=fOuST6FBqHZO0rWxaqJYWw%3d%3d; e7e18b68-fbba-43c2-b329-ad7b7822af983=2d52zaTwDe%2fxn2iBv%2bDu4A%3d%3d; __RequestVerificationToken_L1B3Q1RXL0NsaWVudC9TZXJ2aWNlL0NvbmZpcm1hdGlvbi9XZWJVSV9CcmFuY2g1=cpSloHZJu7Kbgbqfu17YI1C9SQtKyE8_CaIu4M8vybCFKF7OfBMWwpu-RdcYmi699I5C5Y4-60Fag0azYldvRjPfXx76-0byZfvmKuMAjAQ1

