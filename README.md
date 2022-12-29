## 코로나 세계 현황판 만들기

최종 프로젝트 폴더입니다

## 자바스크립트 프로젝트에 타입스크립트 적용하기

⚠️ **주의점**

- 기능적 변경은 절대 하지 말것
- 테스트 커버리지(테스트코드가 다루는 범위가 좁을때)가 낮을땐 TS를 적용하지 말것
- 타입은 점진적으로 확장시켜갈것

0. 자바스크립트 파일에 JSDoc으로 타입 시스템 입히기 (//@ts-check)
1. 타입스크립트의 기본 환경 구성
    - NPM 초기화
    - 타입스크립트 라이브러리 설치
    - 타입스크립트 설정 파일 생성 및 기본 값 추가
    - 자바스크립트 파일을 타입스크립트 파일로 변환
    - `tsc` 명령어로 타입스크립트 컴파일 하기
2. 명시적인 `any` 선언하기
    - `tsconfig.json` 파일에 `noImplictAny` 값을 `true`로 추가 

## 참고 자료

- [존스 홉킨스 코로나 현황](https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6)
- [Postman API](https://documenter.getpostman.com/view/10808728/SzS8rjbc?version=latest#27454960-ea1c-4b91-a0b6-0468bb4e6712)