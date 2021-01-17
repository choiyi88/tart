1. 주제 : 2030의 가처분 소득과 자산 구성

2. 사용 API :
 (1) 국민연금 가입 현황(http://apis.data.go.kr/B552015/NpsSbscrbInfoProvdService/getSbscrbAgeInfoSearch)
 (2) 국토교통부_아파트 전월세 자료(http://openapi.molit.go.kr:8081/OpenAPI_ToolInstallPackage/service/rest/RTMSOBJSvc/getRTMSDataSvcAptRent) 
 (3) 한국예탁결제원_기업정보서비스(http://api.seibro.or.kr/openapi/service/CorpSvc/getStkDistributionAgeStatus)
 
3. 목차
 (1) 소득
    국민연금 가입현황 - 가입현황 정보조회
    input : 지역(법정동 주소) 연령(가입자 연령) 
    output : 평균납부금액, 평균가입기간 
   -> 평균납부금액/평균가입기간/9%(국민연금 부담율)
      = 지역 & 연령별 근로소득 평균금액
   
   





