트리맵 
============================================================================

| 트리맵 챠트는 영역의 크기와 색으로 해당 데이터의 속성을 한 눈에 파악하기 쉽게 표현한 챠트입니다.

- 참고 studio 보고서 : `EDU_Studio treemap chart_데이터객체버전 <http://b-iris.mobigen.com:80/studio/exported/93ea4e841056476b918da6e36b7891b9ea7c6d58755a416190fbdacf8b407dbf>`__



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



트리맵 챠트
-------------------------------------------

- 검색어


.. code::

  * | where YEAR=2018 and FIRE_CENTER = '종로소방서' 
    | sort -CNT
    | fields FIRE_CAUSE,CNT as 발생건수




| 2018년 종로소방서의 화재원인 별 발생 건수를 내림차순으로 구합니다.
| 트리맵의 색깔이 진할 수록 발생건수가 많으며, 사각형의 면적이 큽니다.



.. image:: images/chart_treeMap_35.png
    :alt: chart_treeMap_35
