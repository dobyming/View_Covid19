## 코로나 세계 현황판 만들기

전세계별 코로나 확진자수를 보여주는 최종 프로젝트 폴더입니다

## 자바스크립트 프로젝트에 타입스크립트 적용하기

⚠️ **Before starting..**

- 기능적 변경은 절대 하지 말것
- 테스트 커버리지(테스트코드가 다루는 범위가 좁을때)가 낮을땐 TS를 적용하지 말것
- 타입은 점진적으로 확장시켜갈것

0. 자바스크립트 파일에 JSDoc으로 타입 시스템 입히기 // @ts-check
1. 타입스크립트의 기본 환경 구성
    - NPM 초기화
    - 타입스크립트 라이브러리 설치
    - 타입스크립트 설정 파일 생성 및 기본 값 추가
    - 자바스크립트 파일을 타입스크립트 파일로 변환
    - `tsc` 명령어로 타입스크립트 컴파일 하기
2. 명시적인 `any` 선언하기
    - `tsconfig.json` 파일에 `noImplictAny` 값을 `true`로 추가 

## 타입스크립트 프로젝트 환경 구성

1. 프로젝트 폴더 생성
2. `npm init -y`로 `package.json` 파일 생성
3. 아래 명령어로 타입스크립트 및 문법 검사, 코드 정리 도구 라이브러리 추가

```sh
npm i -D typescript @babel/core @babel/preset-env @babel/preset-typescript @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint prettier eslint-plugin-prettier
```

4. 프로젝트 폴더 바로 아래에 ESLint 설정 파일 추가
   
```js
// .eslintrc.js
module.exports = {
  root: true,
  env: {
    browser: true,
    node: true,
  },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/eslint-recommended',
    'plugin:@typescript-eslint/recommended',
  ],
  plugins: ['prettier', '@typescript-eslint'],
  rules: {
    'prettier/prettier': [
      'error',
      {
        singleQuote: true,
        semi: true,
        useTabs: false,
        tabWidth: 2,
        printWidth: 80,
        bracketSpacing: true,
        arrowParens: 'avoid',
      },
    ],
  },
  parserOptions: {
    parser: '@typescript-eslint/parser',
  },
};
```

5. ESLint 이그노어 파일 추가

```
// .eslintignore
node_modules
```

## VSCode ESLint 플러그인 관련 설정

1. VSCode의 [ESLint 플러그인](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) 설치
2. VSCode에서 `ctrl` + `shift` + `p` / `cmd` + `shift` + `p` 키를 이용하여 명령어 실행 창 표시 (window/mac)
3. 명령어 실행 창에 `open settings (json)` 입력 후 선택
4. VSCode 사용자 정의 파일인 `settings.json` 파일의 내용에 아래와 같이 ESLint 플러그인 관련 설정 추가.

```js
{
  // ... <-- 기존 내용을 꼭 유지한 상태에서 아래 내용을 추가하고 이 주석은 제거할 것
  "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true
  },
  "eslint.alwaysShowStatus": true,
  "eslint.workingDirectories": [
      {"mode": "auto"}
  ],
  "eslint.validate": [
      "javascript",
      "typescript"
  ],
}
```

5. `ctrl` + `,` 또는 `cmd` + `,` 눌러서 VSCode 설정 파일(Settings)에 들어간 후 `format on save` 검색 후 체크가 **해제** 됐는지 확인.

## 참고 자료

- [존스 홉킨스 코로나 현황](https://www.arcgis.com/apps/opsdashboard/index.html#/bda7594740fd40299423467b48e9ecf6)
- [Postman API](https://documenter.getpostman.com/view/10808728/SzS8rjbc?version=latest#27454960-ea1c-4b91-a0b6-0468bb4e6712)