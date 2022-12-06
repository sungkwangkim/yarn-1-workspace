# yarn-1-workspace


https://classic.yarnpkg.com/en/docs/workspaces#toc-how-to-use-it

# 1. root package.json 설정
`package.json`
```json
{
  "private": true,
  "workspaces": ["packages/*"]
}
```


# 2. pacakges 폴더 하위에 workspace 생성
이 파일을 만든 후 packages 폴더 하위에 두 개의 새 하위 폴더를 만듭니다.
common, server 각각에 package.json다음 내용으로 다른 파일을 만듭니다 . 

```shell
mkdir packages
mkdir ./packages/common
mkdir ./packages/server
```

`./packages/common/package.json`

```json
{
  "name": "@study/common",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT"
}
```

`./packages/server/package.json`

```json
{
  "name": "@study/server",
  "version": "1.0.0",
  "main": "index.js",
  "license": "MIT"
}
```


# 3. server 폴더에서 common 프로젝트를 의존성을 주입하려면?

(귀찮게 버전까지 꼭 써야함.)
```shell
yarn workspace @study@server add @study@common@1.0.0  
```



server 실행
```shell
yarn workspace @study@server dev
```



## 참고
- https://classic.yarnpkg.com/blog/2017/08/02/introducing-workspaces/
