==================================================
탐색 결과를 파일로 내보내기
==================================================

| 데이터 브라우저 > 검색 메뉴로 진입합니다. 


.. figure:: ./images/enter_00.png
        :scale: 100%
        :figclass: align-center
        :alt: IRISMenu


| 
| 좌측의 데이터 모델 탭에서 데이터 모델을 선택합니다.

- 예시: WEATHER 선택


.. figure:: ./images/export_st_00.png
        :alt: 데이터 모델 선택


| 
| 시간 탭에서 원하는 기간을 선택하고 필요에 따라 Command를 작성한 다음 우측 상단의 작은 삼각형 버튼을 눌러 실행합니다. 

- 예시: 전체기간 선택, Command : | fields  LOCATION, AVG_TEMP, RAINFALL_CONT_TIME


.. figure:: ./images/export_st_01.png
        :alt: 기간,Command 설정

| 
| 검색 결과가 나오면 중앙의 내려받기 버튼을 클릭합니다.

.. figure:: ./images/export_st_02.png
        :alt: 내보내기


-----------------------------
 로컬에 다운로드
-----------------------------


| 파일 형태로 로컬에 내려받을 경우, 로컬을 선택하고 내보내기를 클릭합니다.

- 필요에 따라 확장자(csv, tsv, json)와 분리기호, 파일명, 제한 여부를 선택할 수 있습니다.(디폴트 설정은 csv, download.csv)

.. figure:: ./images/export_st_03.png
        :alt: 파일 설정


| 
| 다운로드한 파일을 열어보면 미리보기에 출력된 내용과 동일한 데이터가 다운로드된 것을 확인할 수 있습니다.

.. figure:: ./images/export_st_04.png
        :alt: 파일 확인


-------------------------------
 HDFS에 내보내기
-------------------------------

| HDFS에 내보낼 경우, HDFS와 연결정보를 선택하고 찾아보기를 클릭합니다. 

.. figure:: ./images/export_HDFS_st_03.png
        :alt: HDFS 내보내기

| 
| 저장할 폴더를 선택하고 선택된 폴더선택을 클릭합니다. 

- 예시: Weather 폴더 선택

.. figure:: ./images/export_HDFS_st_04.png
        :alt: 폴더 선택

| 
| 경로와 연결정보를 확인하고 내보내기를 클릭합니다.

.. figure:: ./images/export_HDFS_st_05.png
        :alt: 내보내기


.. figure:: ./images/export_HDFS_06.png
        :alt: 성공

| 
| HDFS조회- HDFS브라우저로 진입하여 해당 경로로 접근하면 파일을 확인할 수 있습니다. 

.. figure:: ./images/export_HDFS_st_07.png
        :alt: 파일 확인

.. figure:: ./images/export_HDFS_st_08.png
        :alt: 파일 확인