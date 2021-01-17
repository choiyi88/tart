1. 주제 : 2030의 가처분 소득과 금융자산(주식) 

2. 사용 API :
 (1) 국민연금 가입 현황(http://apis.data.go.kr/B552015/NpsSbscrbInfoProvdService/getSbscrbAgeInfoSearch)
 (2) 국토교통부_아파트 전월세 자료(http://openapi.molit.go.kr:8081/OpenAPI_ToolInstallPackage/service/rest/RTMSOBJSvc/getRTMSDataSvcAptRent) 
 (3) 한국예탁결제원_기업정보서비스(http://api.seibro.or.kr/openapi/service/CorpSvc/getStkDistributionAgeStatus)
 
3. 목차
 (1) 소득
    API 국민연금 가입현황 - 가입현황 정보조회
    input : 지역(법정동 주소) 연령(가입자 연령) 
    output : 평균납부금액, 평균가입기간 
   -> 평균납부금액/평균가입기간/9%(국민연금요율)
      = 지역 & 연령별 소득 평균금액(월)
   
  (2) 소비
    KOSIS 국가통계포털 - 가구특성별 비목별 소비지출
    29세이하 : 경상소득 : 3,533만원  /  소비 : 1,939만원(주거비 : 377만원) 비소비 : 495만원(이자비용 : 84만원) -> 소비비율(주거제외) : 55.84%(1,973만원/3,533만원)
    30세~39세 : 경상소득 : 6,346만원 / 소비 : 2,919만원(주거비 : 330만원) 비소비 : 1,223만원(이자비용 : 232만원) ->소비비율(주거제외) : 56.41%(3,580만원/6,346만원)

    가정 : 주거비 제외 소득대비 소비비중 동일 가정 & 이자비용(주택담보대출, 전세자금대출등) 주거비로 인해 발생 가정

    API 국토교통부_아파트 전월세 자료
    input : 지역(지역코드 : 법정동 시&구(5자리)),계약월(YYYYMM)
    output : 건축년도, 년, 법정동, 보증금액, 아파트, 월, 월세금액, 일, 전용면적, 지번, 지역코드, 층
    -> 전용면적당 지역별 평균 시세 : (보증금액 * 전월세전환율 + 월세)/전용면적 * 12월 의 평균

  (3) 가처분 소득
      지역별&연령별 가처분 소득
      소득*(1-소비비율(주거비제외))-지역별 평균시세 * 평균 면적 = 가처분소득
      
  (4) 지역별 평균 자산
      가처분 소득 * 연령별 평균가입기간 = 평균 자산

  (5) 2030의 주식 보유 현황 분석
      API 한국예탁결제원_기업정보서비스 - 주식분포현황 연령별소유 현황
      input : 발행회사번호(기업기본정보 기업개요 조회 ->회사명 조회) / 기준일
      output : 주주수, 주주비율, 구분명, 주식수
      
      1) 주식시장에서 2030 비율
         개별 주식 * 기준일 종가 /발행주식수 * 기준일 종가(시가총액)
         -> 연령별 투자규모(파이차트)
      2) 2030 관심 기업
        투자액 상위 종목 : 개별주식 * 기준일 종가 기준 상위 종목(bar그래프)
        타 연령 대비 관심종목 : 연령별 비율 상위종목(파이차트)
        투자 형태 : 상장 기업수 대비 보유 종목수 - 특정 종목에 쏠림 여부
        시계열 분석 : 시점(기준일)별로 주식수 변동을 통해 타연령대비 관심종목 식별
                       
  



