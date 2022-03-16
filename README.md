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