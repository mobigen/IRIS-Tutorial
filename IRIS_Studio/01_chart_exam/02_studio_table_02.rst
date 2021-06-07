테이블과 검색어 2
========================================================================

| IRIS Studio 의 **챠트-테이블** 유형에서 

- stats 구문
- sort 

| 을 검색어로 사용한 결과를 테이블에서 확인합니다.


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




테이블 : stats 문
-------------------------------------------

- 검색어

.. code::

  * | where FIRE_CENTER='종로소방서' and  YEAR=2018 
    | case when FIRE_CAUSE like '실화%' 
           then '실화' 
           when FIRE_CAUSE like '방화%'
           then '방화'
           otherwise FIRE_CAUSE as CAUSE_KIND
    
    | stats SUM(CNT) as SUM_CNT by YEAR,FIRE_CENTER, CAUSE_KIND


|
| ``case``  구문으로 새로 만든 CAUSE_KIND 컬럼으로 CNT(발생건수) 의 합계를 구하는 데 ``stats`` 를 사용합니다.
| 자세한 설명 - 검색어 `STATS <http://docs.iris.tools/manual/IRIS-Manual/IRIS-Discovery-Middleware/command/commands/stats.html>`__ 를 참조하세요.
|

- case 문 결과
|

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


- stats 결과

.. list-table::
   :header-rows: 1

   * - YEAR
     - FIRE_CENTER
     - CAUSE_KIND
     - SUM_CNT
   * - 2018
     - 종로소방서
     - 자연적인_요인
     - 1
   * - 2018
     - 종로소방서
     - 원인불명
     - 27
   * - 2018
     - 종로소방서
     - 방화
     - 7
   * - 2018
     - 종로소방서
     - 실화
     - 219




테이블 : sort 
---------------------------------------------

- 검색어

.. code::

  * | where FIRE_CENTER='종로소방서' and  YEAR=2018 
    | case when FIRE_CAUSE like '실화%' 
           then '실화' 
           when FIRE_CAUSE like '방화%'
           then '방화'
           otherwise FIRE_CAUSE as CAUSE_KIND
    
    | stats SUM(CNT) as SUM_CNT by YEAR,FIRE_CENTER, CAUSE_KIND

    | sort +YEAR


| stats 로 나온 결과를 YEAR 변수의 값을 오름차순(점점 커지는 순서)로 출력합니다.
| 자세한 설명 - 검색어 `SORT <http://docs.iris.tools/manual/IRIS-Manual/IRIS-Discovery-Middleware/command/commands/sort.html>`__ 를 참조하세요.

|

- 결과

.. list-table::
   :header-rows: 1

   * - YEAR
     - FIRE_CENTER
     - CAUSE_KIND
     - SUM_CNT
   * - 2018
     - 종로소방서
     - 자연적인_요인
     - 1
   * - 2018
     - 종로소방서
     - 방화
     - 7
   * - 2018
     - 종로소방서
     - 원인불명
     - 27
   * - 2018
     - 종로소방서
     - 실화
     - 219

