# 18기를 위한 오라클 백업과 복구 가이드

안녕하세요, 18기 여러분! 🌟

오라클 dba와 오라클 엔지니어를 준비하시는 여러분들을 위해 오라클 백업과 복구 수업 스크립트를 이 깃허브에 정리해보았습니다.

&nbsp;

## 시작하는 법

아래의 내용을 순서데로 하나 하나 차근 차근 보시면 됩니다.


&nbsp;

## 수업 자료 (업데이트: 2024.03.04)


### 1. 백업하기
 
- **아카이브 모드로 변경하기**: [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EC%95%84%EC%B9%B4%EC%9D%B4%EB%B8%8C%20%EB%AA%A8%EB%93%9C%20%EB%B3%80%EA%B2%BD.txt)
 
- **cold  backup 수행하기**: [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/cold%20backup%20%EC%88%98%ED%96%89%ED%95%98%EA%B8%B0.txt)

- **hot backup 수행하기**: [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/%EC%82%AC%EC%9A%A9%EC%9E%90%20%EA%B4%80%EB%A6%AC%20hot%20backup%20%EC%88%98%ED%96%89%ED%95%98%EA%B8%B0.txt)

- **control file 백업하기**: [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/controlfile%20%20hotbackup%20%ED%95%98%EA%B8%B0.txt)

&nbsp;

### 2. 완전 복구하기
 
- **non system data file을 삭제하고 복구(db close 상태)**: [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/non%20system%20data%20file%EC%9D%84%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B3%A0%20%EB%B3%B5%EA%B5%AC.txt)

- **non system data file을 삭제하고 복구(db open 상태)**: [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/non%20system%20datafile%20%EC%9D%B4%20%EA%B9%A8%EC%A1%8C%EC%9D%84%20%EB%95%8C%20%20db%20open%20%EC%83%81%ED%83%9C%EC%97%90%EC%84%9C%20%EB%B0%94%EB%A1%9C%20%EB%B3%B5%EA%B5%AC%ED%95%98%EA%B8%B0.txt)
  
- **system data file을 삭제하고 복구**: [관련 코드](https://github.com/oracleyu01/oracle_backup_recovery/blob/main/system%20%20data%20file%20%EC%9D%84%20%EC%82%AD%EC%A0%9C%ED%95%98%EA%B3%A0%20%EB%B3%B5%EA%B5%AC%20%ED%95%98%EA%B8%B0.txt)

- **모든 data file들을 전부 삭제하고 복구**: [관련 코드](링크)
 
- **control file이 삭제되었을 때 복구**: [관련 코드](링크)


---

감사합니다!

[코딩 대한민국](https://codingkorea.example.com)
