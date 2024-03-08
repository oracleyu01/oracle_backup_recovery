# 18기를 위한 오라클 백업과 복구 가이드

안녕하세요, 18기 여러분! 🌟

오라클 dba와 오라클 엔지니어를 준비하시는 여러분들을 위해 오라클 백업과 복구 수업 스크립트를 정리하였습니다.

## 시작하는 법

아래의 내용을 순서데로 보시면 됩니다.

## 수업 자료 (업데이트: 2024.03.04)

| 순서 | 항목 | 코드 |
|-----|------|------|
|     |**1. 사용자 관리 백업하기**   |
| 1.1 | 아카이브 모드로 변경하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EC%95%84%EC%B9%B4%EC%9D%B4%EB%B8%8C%20%EB%AA%A8%EB%93%9C%20%EB%B3%80%EA%B2%BD.txt) |
| 1.2 | cold  backup 수행하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/cold%20backup%20%EC%88%98%ED%96%89%ED%95%98%EA%B8%B0.txt) |
| 1.3 | hot backup 수행하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EC%82%AC%EC%9A%A9%EC%9E%90%20%EA%B4%80%EB%A6%AC%20hot%20backup%20%EC%88%98%ED%96%89%ED%95%98%EA%B8%B0.txt) |
| 1.4 | control file 백업하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/controlfile%20%20hotbackup%20%ED%95%98%EA%B8%B0.txt) |
|   | **2. 사용자 관리 완전 복구하기** |  |
| 2.1 | non system data file을 삭제하고 복구(db close 상태) | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/non%20system%20data%20file%EC%9D%84%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B3%A0%20%EB%B3%B5%EA%B5%AC.txt) |
| 2.2 | non system data file을 삭제하고 복구(db open 상태) | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/non%20system%20datafile%20%EC%9D%B4%20%EA%B9%A8%EC%A1%8C%EC%9D%84%20%EB%95%8C%20%20db%20open%20%EC%83%81%ED%83%9C%EC%97%90%EC%84%9C%20%EB%B0%94%EB%A1%9C%20%EB%B3%B5%EA%B5%AC%ED%95%98%EA%B8%B0.txt) |
| 2.3 | system data file을 삭제하고 복구 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/system%20%20data%20file%20%EC%9D%84%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B3%A0%20%EB%B3%B5%EA%B5%AC%20%ED%95%98%EA%B8%B0.txt) |
| 2.4 | 모든 data file들을 전부 삭제하고 복구 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EB%AA%A8%EB%93%A0%20data%20file%EB%93%A4%EC%9D%84%20%EC%A0%84%EB%B6%80%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B3%A0%20%EB%B3%B5%EA%B5%AC.txt) |
| 2.5 | control file이 삭제되었을 때 복구 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/control%20file%EC%9D%B4%20%EC%82%AD%EC%A0%9C%EB%90%98%EC%97%88%EC%9D%84%20%EB%95%8C%20%EB%B3%B5%EA%B5%AC.txt) |
| 2.6 | contol file 을  multiplexing 하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/contol%20file%20%EC%9D%84%20%20multiplexing%20%ED%95%98%EA%B8%B0.txt) |
| 2.7 | multiplexing 된 controlfile 중에 1개를 삭제하고 복구 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/multiplexing%20%EB%90%9C%20controlfile%20%EC%A4%91%EC%97%90%201%EA%B0%9C%EB%A5%BC%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B3%A0%20%EB%B3%B5%EA%B5%AC.txt) |
| 2.7 | inactive 상태의 redo log file이 삭제 되었을 때 복구 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/inactive%20%EC%83%81%ED%83%9C%EC%9D%98%20redo%20log%20file%EC%9D%B4%20%EC%82%AD%EC%A0%9C%20%EB%90%98%EC%97%88%EC%9D%84%20%EB%95%8C%20%EB%B3%B5%EA%B5%AC.txt) |
| 2.8 | redo log file 의 다중화 하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/redo%20log%20file%20%EC%9D%98%20%EB%8B%A4%EC%A4%91%ED%99%94%20%ED%95%98%EA%B8%B0.txt) |
| 2.9 | redo log group 의 멤버 삭제하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/redo%20log%20group%20%EC%9D%98%20%EB%A9%A4%EB%B2%84%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B8%B0.txt) |
| 2.10 | redo log group 추가하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/redo%20log%20group%20%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0.txt) |
| 2.11 | redo log group 삭제하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/redo%20log%20group%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B8%B0.txt) |
| 2.12 | 다중화 된 상태에서 inactive 리두 로그 멤버 1개를 손상시키기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EC%98%88%EC%A0%9C.%20%20%EB%8B%A4%EC%A4%91%ED%99%94%20%EB%90%9C%20%EC%83%81%ED%83%9C%EC%97%90%EC%84%9C%20inactive%20%EB%A6%AC%EB%91%90%20%EB%A1%9C%EA%B7%B8%20%EB%A9%A4%EB%B2%84%EB%A5%BC%20%EC%86%90%EC%83%81%EC%8B%9C%ED%82%A4%EA%B8%B0.txt) |
| 2.13 | 그룹의 모든 멤버를 삭제되었을때 복구하는 방법 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EA%B7%B8%EB%A3%B9%EC%9D%98%20%EB%AA%A8%EB%93%A0%20%EB%A9%A4%EB%B2%84%EB%A5%BC%20%EC%82%AD%EC%A0%9C%EB%90%98%EC%97%88%EC%9D%84%EB%95%8C%20%EB%B3%B5%EA%B5%AC%ED%95%98%EB%8A%94%20%EB%B0%A9%EB%B2%95.txt) |
|    | **3. 사용자 관리 불완전 복구하기** |  |
| 3.1 | time base 불완전 복구 수행하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/time%20base%20%EB%B6%88%EC%99%84%EC%A0%84%20%EB%B3%B5%EA%B5%AC%20%EC%88%98%ED%96%89%ED%95%98%EA%B8%B0.txt) |
| 3.2 | cancel base 불완전 복구 수행하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/cancel%20base%20%EB%B6%88%EC%99%84%EC%A0%84%20%20%EB%B3%B5%EA%B5%AC.txt) |
| 3.3 | 모든 redo logfile 이 삭제되었을 때 복구 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EB%AA%A8%EB%93%A0%20redo%20file%20%EC%9D%B4%20%EC%82%AD%EC%A0%9C%EB%90%98%EC%97%88%EC%9D%84%20%EB%95%8C%20%EB%B3%B5%EA%B5%AC.txt) |
| 3.4 | 모든 datafile, controlfile, redo logfile 이 삭제되었을때 복구 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EB%AA%A8%EB%93%A0%20data%20file%2C%20controlfile%2C%20redo%20logfile%20%EC%9D%B4%20%EC%82%AD%EC%A0%9C%EB%90%98%EC%97%88%EC%9D%84%20%EB%95%8C%20%EB%B3%B5%EA%B5%AC.txt) |
|    | **4. RMAN 을 사용하여 백업하기** |  |
| 4.1 | RMAN 을 사용하여 cold backup 수행하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C%20cold%20backup%20%EC%88%98%ED%96%89%ED%95%98%EA%B8%B0.txt) |
| 4.2 | RMAN 을 사용하여 hot backup 수행하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C%20cold%20backup%20%EC%88%98%ED%96%89%ED%95%98%EA%B8%B0.txt) |
| 4.3 | RMAN 을 사용하여 특정 테이블 스페이스만 백업하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C%20%ED%8A%B9%EC%A0%95%20tablespace%EB%A7%8C%20%EB%B0%B1%EC%97%85%EB%B0%9B%EA%B8%B0.txt) |
|    | **5. RMAN 을 사용하여 복구하기** |  |
| 5.1 | Non System datafile 삭제하고 RMAN 으로로 복구하기(open상태) | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C%20Non%20system%20datafile%20%EC%86%90%EC%83%81%EC%8B%9C%20%EB%B3%B5%EA%B5%AC%ED%95%98%EA%B8%B0(open%EC%83%81%ED%83%9C).txt) |
| 5.2 | system datafile 들을 삭제하고 RMAN 으로 복구하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C%20system%20datafile%20%EB%93%A4%EC%9D%84%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B3%A0%20%EB%B3%B5%EA%B5%AC%ED%95%98%EA%B8%B0.txt) |
| 5.3 | 모든 datafile을 삭제하고 RMAN 으로 복구하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C%20%EB%AA%A8%EB%93%A0%20data%20file%EB%93%A4%EC%9D%84%20%EC%A0%84%EB%B6%80%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B3%A0%20%EB%B3%B5%EA%B5%AC%ED%95%98%EA%B8%B0.txt) |
| 5.4 | 모든 controlfile을 삭제하고 RMAN 으로 복구하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C%20%EB%AA%A8%EB%93%A0%20control%20file%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B3%A0%20%EB%B3%B5%EA%B5%AC%ED%95%98%EA%B8%B0.txt) |
| 5.5 | 모든 datafile 과 controlfile을 삭제하고 RMAN 으로 복구하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EB%AA%A8%EB%93%A0%20data%20file%2C%20controlfile%2C%20redo%20logfile%20%EC%9D%B4%20%EC%82%AD%EC%A0%9C%EB%90%98%EC%97%88%EC%9D%84%20%EB%95%8C%20%EB%B3%B5%EA%B5%AC.txt) |
| 5.6 | 파라미터 파일이 손상되었을 때 RMAN 으로 복구하기  | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%20%ED%8C%8C%EC%9D%BC%EC%9D%B4%20%EC%86%90%EC%83%81%EB%90%98%EC%97%88%EC%9D%84%20%EB%95%8C%20RMAN%20%EC%9C%BC%EB%A1%9C%20%EB%B3%B5%EA%B5%AC%ED%95%98%EA%B8%B0.txt) |
| 5.7 | RMAN 을 사용해서  time base 불완전 복구하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C%20%20time%20base%20%EB%B6%88%EC%99%84%EC%A0%84%20%EB%B3%B5%EA%B5%AC%ED%95%98%EA%B8%B0.txt) |
| 5.8 | RMAN 을 사용해서  cancel base 불완전 복구하기 | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C%20%20cancel%20base%20%EB%B6%88%EC%99%84%EC%A0%84%20%EB%B3%B5%EA%B5%AC%ED%95%98%EA%B8%B0.txt) |
| 5.9 | RMAN 을 사용하지 않고 백업본이 없을 때 복구 방법      | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%95%98%EC%A7%80%20%EC%95%8A%EA%B3%A0%20%EB%B0%B1%EC%97%85%EB%B3%B8%EC%9D%B4%20%EC%97%86%EC%9D%84%20%EB%95%8C%20%EB%B3%B5%EA%B5%AC%20%EB%B0%A9%EB%B2%95.txt) |
| 5.10 |  RMAN 을 사용해서 백업본이 없을 때 복구 방법   | [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/RMAN%20%EC%9D%84%20%EC%82%AC%EC%9A%A9%ED%96%88%EC%9D%84%20%EB%95%8C%20%EB%B0%B1%EC%97%85%EB%B3%B8%EC%9D%B4%20%EC%97%86%EC%9D%84%20%EB%95%8C%20%EB%B3%B5%EA%B5%AC%20%EB%B0%A9%EB%B2%95.txt) |
| 5.11 |    | [관련 코드]() |
| 5.12 |    | [관련 코드]() |
| 5.13 |    | [관련 코드]() |
| 5.14 |   | [관련 코드]() |
