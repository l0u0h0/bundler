## Bundler
- 외부 패키지의 도움을 받아 HTML/CSS/ES5 등 웹에서 보여줄 수 있도록  
변환시켜줌
### Parcel
- 구성 없는 단순한 자동 번들링
- 소/중형 프로젝트에 적합
### Webpack
- 매우 꼼꼼한 구성
- 중/대형 프로젝트에 적합
---
## postcss, autoprefixer
- 버전이 맞지 않는 구 버전의 브라우저에서도 적용될 수 있는 `css` 스타일  
속성을 자동으로 부여해주기 위한 패키지
### autoprefixer
- `pakage.json` 파일 하단에 배열 형태의 속성 추가
- 지원할 브라우저의 범위 설정
```json
"browserslist": [
    "> 1%",
    "last 2 versions"
  ]
```
- `"> 1%"` - 전 세계에 점유율이 1퍼센트 이상인 모든 브라우저
- `"last 2 versions"` - 해당하는 브라우저의 마지막 2개까지는 지원
### postcss
- 루트 경로에 `.postcss.js` 파일을 생성해줌
- 뒤에 붙은 `rc`는 일반적으로 구성 파일을 의미
- 파일 명 앞에 `.`이 붙으면 일반적으로 구성옵션이나 숨김파일을 의미
- `import`, `export`와 같은 일반적인 `ESM`에서의 방식이 아닌  
`CommonJS` 방식으로 작성, `nodejs`에서는 `CommonJS`를 따르기에
- 이떄 사용하는 함수는 `require()`.
- 내보낼 때는 `module.exports`와 같이 사용
---
## Babel
- `ES 2015+`코드를 이전 js 엔진에서 실행할 수 있는 이전 버전과 호환되는  
js 버전으로 변환하는 데 주로 사용되는 무료 오픈 소스 js 트랜스 컴파일러
- `ES6`,`ES7`,`ES8`을 `ES5`로 변환
- 루트 경로에 `.babelrc.js` 파일을 추가해 사용하며 위와 동일하게  
`package.json` 파일에 `browerslists` 속성을 설정해줘야 한다.
---
## Parcel CLI(Command Line Interface)
- `parcel index.html`
- 개발용 서버 시작 앱이 수정되면 자동으로 다시 빌드, 빠른 모듈 교체 지원
- `parcel build index.html`
- 에셋을 한 번 빌드, 제품화할 때의 빌드에서 사용
- `parcel builde entry.js --out-dir build/output`
- 기본 디렉토리인 `dist`가 아닌 다른 디렉토리에서 열고 싶을 때 사용
- `parcel serve entry.js --port 1111`
- 포트 번호를 변경하고 싶을 때나 충돌하는 경우 사용
- `parcel entry.js --open`
- 따로 브라우저에 접속하지 않아도 브라우저를 열 수 있음
- `parcel entry.js --no-hmr`
- 빠른 모듈 교체 비활성화, 디폴트 값은 `HMR` 활성
- `HMR`이란 `Hot Module Replacement`의 약어로,  
런타임에 페이지 새로고침 없이 수정된 내용을 자동으로 갱신하는 방식
- `parcel build entry.js --no-cache`
- 캐시가 활성화 되어있어 문제가 있는 경우에 캐시를 비활성화 시킬 수 있음.
- 디폴트 값은 활성화