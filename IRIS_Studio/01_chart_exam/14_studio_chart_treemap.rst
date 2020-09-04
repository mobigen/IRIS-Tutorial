트리맵 
============================================================================

| 트리맵 챠트는 데이터를 그룹과 그 그룹의 값에 따라 크기와 색을 다르게 표현하는 챠트입니다.



데이터 모델
------------------------------


| 데이터 모델 : SEOUL_MELT_FIRE_CAUSE
| 기간 : 2011 ~ 2018년 연간 통계
| 내용 : 서울시 소방서, 화재원인별 화재 발생 건수 통계


.. image:: images/table_1_01.png
    :scale: 60%
    :alt: table_1_01



트리맵 챠트
-------------------------------------------

| 검색어


.. code::

  * YEAR=2018 FIRE_CENTER = '종로소방서' | 
  sql "select FIRE_CAUSE,CNT as 발생건수 from angora"  | 
  sort -CNT


| 2018년 종로소방서의 화재원인 별 발생 건수를 내림차순으로 구합니다.
| 트리맵의 색깔이 진할 수록 발생건수가 많으며, 사각형의 면적이 큽니다.



.. image:: images/chart_treeMap_35.png
    :alt: chart_treeMap_35







