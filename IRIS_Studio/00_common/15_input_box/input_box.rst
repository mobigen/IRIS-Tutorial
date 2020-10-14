===================================================================
텍스트 입력
===================================================================

| 텍스트 입력(input box) 객체는 Input Box에 사용자가 입력한 값이나 외부로부터 값을 받아 화면에 보여 줍니다.
| 회원 가입 화면처럼 이름, 비밀번호, 전화 번호 등을 입력하는 input box 생성에 많이 사용됩니다.
| 입력하는 유형은 text, password, number 에서 선택할 수 있습니다.


* 예제 보고서 : `EDU_(1)텍스트입력 <http://b-iris.mobigen.com:80/studio/exported/d209d1eef85149bcb70b0ffa1fa8da27b5845f500aa0453c8bfc245bd1259ad2>`__


.. image:: ./images/input_box_3.png
    :scale: 60%
    :alt: input_box_3


| 유형 설정 text 로 이름을 입력하는 "텍스트 입력" 객체를 생성할 때, ``디폴트 값 선택`` 에서 기본값, 안내 문구에 문구를 입력하면, input box 에 옅게 text 로 표시됩니다.

* 내용 입력 전 화면

.. image:: ./images/input_box_5.png
    :scale: 60%
    :alt: input_box_5


* 내용 입력 화면

.. image:: ./images/input_box_4.png
    :scale: 40%
    :alt: input_box_4

| 유형이 password 일 때는 입력 문자가 input box 에 별표로 표시됩니다.

| 텍스트 박스에서 입력 내용을 확인하기 위해  ${input_1},  ${input_2}, ${input_3} 로 "설정할 변수/값" 부분에 사용합니다.

.. image:: ./images/input_box_6.png
    :scale: 40%
    :alt: input_box_6