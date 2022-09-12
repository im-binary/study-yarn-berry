# study-yarn-berry

1. `yarn create next-app --typescript` -> Next.js, typescript

2. 최신 버전의 yarn(berry) 사용 설정
   `yarn set version stable`
   `.yarnrc.yml`, `.yarn/releases`, `yarn-버전명.cjs` 파일이 생성된다.

3. yarn

4. node_modules가 생긴다면 package.json에 아래 내용 추가
   `"packageManager": "yarn@3.1.1",`

5. `.yarnrc.yml` 파일에서 `'nodeLinker: "pnp"'` 로 변경

6. typescript 관련 플러그인 설정

   ```
   # yarn typescript 플러그인 설정
   yarn plugin import typescript
   yarn add -D typescript
   yarn

   # 타입/모듈 추론을 위한 yarn berry의 vscode 세팅
   yarn dlx @yarnpkg/sdks vscode

   # 개발모드로 띄워보기
   yarn dev
   ```

7. zero install을 위하여 `.gitignore`에 아래 내용 추가하면 다음부터 clone 받을 때 빠른 설치 가능

   ```
   .yarn/*
   !.yarn/cache
   !.yarn/patches
   !.yarn/plugins
   !.yarn/releases
   !.yarn/sdks
   !.yarn/versions
   ```

- yarn berry는 PnP 기능을 통해서 의존성 관리

  zipfsExtension 은 PnP를 사용하는 프로젝트에서 의존성 파일을 기존 방식처럼 쉽게 열어줄 수 있는 역할을 한다.
