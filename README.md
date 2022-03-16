# Phaser 3 Webpack 프로젝트 탬플릿

> 출처 : [https://github.com/photonstorm/phaser3-project-template.git](https://github.com/photonstorm/phaser3-project-template.git)

A Phaser 3 프로젝트 탬플릿은 [Babel 7](https://babeljs.io/) and [Webpack 4](https://webpack.js.org/) 를 통해 ES6 를 지원한다. (개발을 위한 핫 리로딩 및 운영 배포를 포함)

Phaser 3.50.0 이상의 버전으로 업데이트 됨

이미지 로딩 시 자바스크립트 모듈을 통한 `import`  키워드를 지원.(비록 추천하지는 않지만...)

## 요구사항

[Node.js](https://nodejs.org) 설치 및 `npm` 을 통한 의존성(라이브러리) 설치가 필요.

## degit 설치

> git 으로 clone 하면 되지만 remote 저장소 및 history 가 그대로 남아있고 남아 있어 degit 을 통해 저장소를 복제하는 것을 추천한다

`npm i -g degit` 을 통해 degit 을 설치한다.

이후 아래와 같이 작업하여 저장소를 복제하여 사용할 수 있다.

```sh
degit https://github.com/wonsama/p3js-template.git my-app

cd my-app

# git repo init
git init
git add .
git commit -m "처음 커밋"
```

## 사용가능 커맨드

| Command | Description |
|---------|-------------|
| `npm install` | 프로젝트 의존성 라이브러리를 설치 |
| `npm start` | 프로젝트를 빌드하고 웹서버를 기동한다. |
| `npm run build` | `production` 설정으로 배포 번들을 수행한다. (minification, uglification, 등) |

## 코드 작성 및 확인

`npm install` 을 통해 의존성 설치 이후 `npm start` 커맨드 입력을 통해 로컬 개발서버를 시작할 수 있다.

`src` 폴더 내 파일을 수정하면 webpack 이 자동적으로 재컴파일을 수행하며 `http://localhost:8080` 를 통해 변경된 사항을 바로 확인할 수 있다.

## 탬플릿 커스트 마이징

### 바벨

최신 ES6+ JavaScript를 작성할 수 있으며 Babel은 이를 프로젝트에서 지원하려는 JavaScript 버전으로 변환합니다. 대상 브라우저는 `.babelrc` 파일에 설정되어 있으며 기본값은 현재 총 사용량이 "0.25%" 이상인 모든 브라우저를 대상으로 하지만 IE11 및 Opera Mini는 제외됩니다.

```json
"browsers": [
  ">0.25%",
  "not ie 11",
  "not op_mini all"
]
 ```

### 웹팩

새 웹팩 로더 또는 플러그인 추가(예: CSS 또는 글꼴 로드용)와 같이 빌드를 사용자 정의하려면 프로젝트 간 변경을 위해 `webpack/base.js` 파일을 수정하거나 다음을 수정할 수 있습니다. 또는 새 구성 파일을 만들고 `package.json' 내부의 특정 npm 작업에서 대상으로 지정합니다.

## 코드 배포

`npm run build` 명령을 실행하면 프로젝트에 의존하는 다른 자산과 함께 `dist/bundle.min.js`에 있는 단일 번들로 코드가 빌드됩니다.

`dist` 폴더의 내용을 공개적으로 액세스할 수 있는 위치(예: `http://mycoolserver.com`)에 넣으면 `http://mycoolserver.com/index.html` 을 웹에서 열 수 있습니다.
