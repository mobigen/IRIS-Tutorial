------------------------------------
예측
------------------------------------

| 시각화 유형 ``예측`` 은 시계열 데이터에서 미래 시점의 값을 예측하기 위해 DSL ``forecasts`` 의 결과를 보여주는 시각화 챠트입니다.
| DSL 명령어 `forecasts <https://docs.iris.tools/manual/IRIS-Manual/IRIS-Discovery-Middleware/command/commands/forecasts.html#forecasts>`__  의 결과는 예측에 사용된 과거 데이터와 함께 미럐시점의 데이터가 같이 출력됩니다.
|

Forecast 그래프
'''''''''''''''''''''''''''''''''''''''''''''''''''

- 챠트 설명에 사용한 데이터모델 : EDU_DSL_BeijingAir_18h
- 2016/02/01 ~ 2016/05/01 동안 중국 북경 11개 지점(station) 중 station = 'Dingling' 에서 매일 18:00 시에 측정한 대기질 정보
- 중간에 PM10 이 null 인 행은 삭제하는 조건을 넣었습니다. `fillna <https://docs.iris.tools/manual/IRIS-Manual/IRIS-Discovery-Middleware/command/commands/fillna.html#fillna>`__ 명령어 메뉴얼을 참조하세요.
- station = 'Dingling' 일 때의 PM10 을 10일치(f_coeff = 10)를  seasonal 알고리즘으로 예측해봅니다.

|

- Forecast 옵션  : 물음표 아이콘에 툴팁으로 각 옵션에 대한 설명이 나옵니다. 자세한 것은 `forecasts <https://docs.iris.tools/manual/IRIS-Manual/IRIS-Discovery-Middleware/command/commands/forecasts.html#forecasts>`__ 를 참고하세요.

  - alg : 예측 알고리즘. linear / seasonal
  


.. image:: images/ko/show_charts_28.png
  :alt: 예측
 
 
