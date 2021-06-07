테이블과 검색어 1
========================================================================

| IRIS Studio 의 **챠트-테이블** 유형에서 

- 필터링 ( 검색에 추가/제외하기 )  : where
- 조건 : case

| 을 검색어로 사용한 결과를 테이블에서 확인해 봅니다.



데이터 모델
------------------------------


| 데이터 모델 : EDU_CHART_SEOUL_MELT_FIRE_CAUSE
| 기간 : 2011 ~ 2018년 연간 통계
| 내용 : 서울시 소방서별 / 화재원인별 발생 건수 통계
|

.. list-table::
   :header-rows: 1

   * - YEAR
     - FIRE_CENTER
     - FIRE_CAUSE
     - CNT
   * - 2018
     - 강남소방서
     - 실화_화학적요인
     - 6
   * - 2018
     - 강남소방서
     - 실화_기타
     - 3
   * - 2018
     - 강동소방서
     - 실화_가스누출
     - 4
   * - 2018
     - 강동소방서
     - 실화_부주의
     - 191
   * - 2018
     - xx소방서
     - ...
     - ...





테이블 : where 구문으로 필터링하기
-------------------------------------------

.. code::

   *  | where FIRE_CENTER='종로소방서' and  YEAR=2018 | where FIRE_CAUSE like '실화%'


| FIRE_CENTER 가 '종로소방서' && YEAR=2018 인 데이터 중에서( 파이프로 전달함 ) FIRE_CAUSE 가 "실화" 로 시작하는 데이터를 검색합니다.

- 자세한 설명 : 검색어 `WHERE <http://docs.iris.tools/manual/IRIS-Manual/IRIS-Discovery-Middleware/command/commands/where.html#where>`__ 

|


.. list-table::
   :header-rows: 1

   * - YEAR
     - FIRE_CENTER
     - FIRE_CAUSE
     - CNT
   * - 2018
     - 종로소방서
     - 실화_전기적요인
     - 65
   * - 2018
     - 종로소방서
     - 실화_기계적요인
     - 8
   * - 2018
     - 종로소방서
     - 실화_화학적요인
     - 2
   * - 2018
     - 종로소방서
     - 실화_가스누출
     - 1
   * - 2018
     - 종로소방서
     - 실화_교통사고
     - 2
   * - 2018
     - 종로소방서
     - 실화_부주의
     - 137
   * - 2018
     - 종로소방서
     - 실화_기타
     - 4




테이블 : case 문으로 조건문 만들기 
---------------------------------------------

- 검색어

.. code::

  * | where FIRE_CENTER='종로소방서' and  YEAR=2018 
    | case when FIRE_CAUSE like '실화%' 
           then '실화' 
           when FIRE_CAUSE like '방화%'
           then '방화'
           otherwise FIRE_CAUSE as CAUSE_KIND


- 검색어 해설

.. code::

    FIRE_CENTER 가 '종로소방서' && YEAR=2018 인 데이터 중에서( 파이프로 전달함 )
    FIRE_CAUSE(화재원인) 이 "실화"로 시작하는 데이터는 CAUSE_KIND = '실화'
    FIRE_CAUSE(화재원인) 이 "방화"로 시작하는 데이터는 CAUSE_KIND = '방화'
    그 외는 CAUSE_KIND = FIRE_CAUSE  


- 결과

.. list-table::
   :header-rows: 1

   * - YEAR
     - FIRE_CENTER
     - FIRE_CAUSE
     - CNT
     - CAUSE_KIND
   * - 2018
     - 종로소방서
     - 실화_전기적요인
     - 65
     - 실화
   * - 2018
     - 종로소방서
     - 실화_기계적요인
     - 8
     - 실화
   * - 2018
     - 종로소방서
     - 실화_화학적요인
     - 2
     - 실화
   * - 2018
     - 종로소방서
     - 실화_가스누출
     - 1
     - 실화
   * - 2018
     - 종로소방서
     - 실화_교통사고
     - 2
     - 실화
   * - 2018
     - 종로소방서
     - 실화_부주의
     - 137
     - 실화
   * - 2018
     - 종로소방서
     - 실화_기타
     - 4
     - 실화
   * - 2018
     - 종로소방서
     - 자연적인_요인
     - 1
     - 자연적인_요인
   * - 2018
     - 종로소방서
     - 방화_명확
     - 6
     - 방화
   * - 2018
     - 종로소방서
     - 방화_의심
     - 1
     - 방화
   * - 2018
     - 종로소방서
     - 원인불명
     - 27
     - 원인불명




