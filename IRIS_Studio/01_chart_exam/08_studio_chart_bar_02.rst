세로 / 가로 막대 그래프 2
============================================================================

| 막대그래프(bar chart) 는 이산형 변수에 대해 범주(category), 계급(class)별로 빈도나 합계 등을 막대로 그려셔 비교할 때 유용합니다.
| 1개 범주나 class 에 1개의 bar 만 표시할 수 도 있고, 데이터에 따라서 1개 범주나 class 에 2개 이상의 빈도나 합계를  여러 개의 bar 로 그릴 수도 있습니다.



데이터 모델
------------------------------

| 데이터 모델 : EDU_SEOUL_FIRE_CAUSE
| 기간 : 2011 ~ 2018년 연간 통계
| 내용 : 서울시 소방서별 / 화재원인별 발생 건수 통계
|

.. list-table::
   :header-rows: 1

   * - YEAR
     - FIRE_CENTER
     - TOTAL
     - ACCIDENTAL_ELECRIC
     - ACCIDENTAL_MECHANIC
     - ACCIDENTAL_CHEMICAL
     - ACCIDENTAL_GAS_EXP
     - ACCIDENTAL_TRAFFIC
     - ACCIDENTAL_CARELESS
     - ETC
     - NATURAL
     - CLEAR_ARSON
     - SUSPICIOUS_ARSON
     - UNKNOWN
   * - 2018
     - 종로소방서
     - 182
     - 73
     - 7
     - 0
     - 0
     - 1
     - 56
     - 4
     - 0
     - 2
     - 20
     - 19
   * - 2018
     - XX소방서
     - ...
     - ...
     - ...
     - ...
     - ...
     - ...
     - ...
     - ...
     - ...
     - ...
     - ...
     - ...


| 데이터모델 생성할 때 별칭으로 컬럼의 설명을 넣어서 데이터모델을 만들면 챠트를 그릴 때 별칭을 보여 줄 수 있습니다.


.. image:: images/chart_bar_21.png
    :alt: chart_bar_21




예) Multi - 세로 막대 그래프
-------------------------------------------------

- 검색어

.. code::

  * | where YEAR=2018 |  fields -TOTAL


| 2018년 데이터 중에서 TOTAL 컬럼을 제외한 데이터를 대상으로 챠트를 그립니다.


.. image:: images/chart_bar_18.png
    :scale: 70%
    :alt: chart_bar_18



- 데이터 및 시각화 설정

| X 축에 소방서(FIRE_CENTER) 를 설정하고,  Y 축으로 화재원인에 해당하는 나머지 컬럼들을 ``모두 선택``  으로 설정합니다.
|
| X축인 소방서별로 화재원인에 해당하는 나머지 컬럼들의 값(=발생건수)의 합을 막대(bar) 로 그린 결과입니다.
| 챠트를 확대해서 보면 각 막대들이 어떤 값을 의미하는지 더 명확하게 보입니다.


.. image:: images/chart_bar_22.png
    :scale: 50%
    :alt: chart_bar_22
