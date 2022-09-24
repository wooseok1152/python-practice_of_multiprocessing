# 목표

- '액면가'값이 '\N'이 아닌 'KOSDAQ'상장 증권만 조회한 후, 해당 조회 결과에 '액면가 * 2'값이 저장된 'NEW_액면가'컬럼을 생성하기 

# 참고 사항

- 'main.ipynb'內 새로운 셀을 생성하여, 코드를 작성할 것
<br>

- 데이터(연산 대상) 경로 : ./csv/SEC01H_20220501.csv
<br>

- 주어진 연산을 '병렬처리'로 수행할 것
- 'Manager.Queue 객체'와, 'Process 객체'를 활용할 것
- 활용되는 process 개수 : CPU core 개수 // 2
- (EX. CPU core 개수 : 4 -> 'df_of_stock_master'을 '두 개'로 분할하고, '두 개'의 프로세스가 주어진 연산을 병렬로 실시)
<br>

- CPU core 개수 조회 : os.cpu_count()
- DataFrame을 n개로 분할 : np.array_split()
<br>

- subprocess들의 pid를 출력하여, 주어진 연산을 병렬처리 했다는 사실을 나타낼 것
- pid 출력 : os.getpid()
<br>

- 'sqldf'함수를 활용하여, 'NEW_액면가'컬럼을 생성할 것<br>
  (pandas 문법 사용을 지양할 것)
- 'pandasql'패키지가 없다면, 해당 패키지를 설치할 것