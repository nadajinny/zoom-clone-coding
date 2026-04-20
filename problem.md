# Problem & Solve

목표 방향 : 에러 문구를 보고 무슨 에러인지 분석하고 해결방안을 제시하는 것으로 활용된다. 

### 1. 패키지 파일 미설치 

#### 문제 상황. localhost로 들어갈 때 에러 메시지 발생

```
Error: Cannot find module 'pug'
Require stack:
- /Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/view.js
- /Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/application.js
- /Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/express.js
- /Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/index.js
- /Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/src/server.js
    at Function._resolveFilename (node:internal/modules/cjs/loader:1365:15)
    at defaultResolveImpl (node:internal/modules/cjs/loader:1021:19)
    at resolveForCJSWithHooks (node:internal/modules/cjs/loader:1026:22)
    at Function._load (node:internal/modules/cjs/loader:1175:37)
    at TracingChannel.traceSync (node:diagnostics_channel:322:14)
    at wrapModuleLoad (node:internal/modules/cjs/loader:235:24)
    at Module.require (node:internal/modules/cjs/loader:1445:12)
    at require (node:internal/modules/helpers:135:16)
    at new View (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/view.js:81:14)
    at Function.render (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/application.js:552:12)
    at ServerResponse.render (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/response.js:923:7)
    at /Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/src/server.js:9:32
    at Layer.handleRequest (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/lib/layer.js:152:17)
    at next (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/lib/route.js:157:13)
    at Route.dispatch (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/lib/route.js:117:3)
    at handle (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/index.js:435:11)
    at Layer.handleRequest (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/lib/layer.js:152:17)
    at /Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/index.js:295:15
    at processParams (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/index.js:582:12)
    at next (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/index.js:291:5)
    at Function.handle (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/index.js:186:3)
    at Function.handle (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/application.js:177:15)
    at Server.app (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/express.js:38:9)
    at Server.emit (node:events:518:28)
    at Server.emit (node:domain:489:12)
    at parserOnIncoming (node:_http_server:1153:12)
    at HTTPParser.parserOnHeadersComplete (node:_http_common:117:17)
```

#### 문제 분석. Cannot find module 'pug' -> Express 서버 실행 중 view 렌더링 실패

Express에서 res.render() 사용 중에서 템플릿 엔진으로 pug를 쓰려고 했는데 pug 패키지가 설치 안되어 확인할 수 없는 상태

#### 해결 방법. 패키지 설치 (문제상황 해결)

> npm install pug


### 1. 경로 문제

#### 문제 상황. 실행시킬 때 에러 문구 발생

```
[nodemon] 3.1.14
[nodemon] to restart at any time, enter `rs`
[nodemon] watching path(s): *.*
[nodemon] watching extensions: js,mjs,cjs,json
[nodemon] starting `babel-node src/server.js`
/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/path-to-regexp/dist/index.js:108
                    throw new PathError(`Missing parameter name at index ${index}`, str);
                    ^

PathError [TypeError]: Missing parameter name at index 2: /*; visit https://git.new/pathToRegexpError for info
    at consumeUntil (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/path-to-regexp/src/index.ts:218:17)
    at parse (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/path-to-regexp/src/index.ts:262:24)
    at process (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/path-to-regexp/src/index.ts:466:52)
    at pathToRegexp (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/path-to-regexp/src/index.ts:478:3)
    at Object.match (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/path-to-regexp/src/index.ts:416:28)
    at matcher (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/lib/layer.js:86:23)
    at new Layer (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/lib/layer.js:93:62)
    at Function.route (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/router/index.js:428:17)
    at Function.route (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/application.js:257:22)
    at Function.get (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/express/lib/application.js:478:22)
    at Object.<anonymous> (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/src/server.js:12:5)
    at Module._compile (node:internal/modules/cjs/loader:1688:14)
    at Module._compile (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/pirates/lib/index.js:129:24)
    at node:internal/modules/cjs/loader:1820:10
    at Object.newLoader [as .js] (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/pirates/lib/index.js:134:7)
    at Module.load (node:internal/modules/cjs/loader:1423:32)
    at Function._load (node:internal/modules/cjs/loader:1246:12)
    at TracingChannel.traceSync (node:diagnostics_channel:322:14)
    at wrapModuleLoad (node:internal/modules/cjs/loader:235:24)
    at Function.runMain (node:internal/modules/run_main:171:5)
    at Object.<anonymous> (/Users/leejinsun/Desktop/Develop/personal/clonecoding/zoom/node_modules/@babel/node/src/_babel-node.ts:185:12)
    at Module._compile (node:internal/modules/cjs/loader:1688:14)
    at Object.<anonymous> (node:internal/modules/cjs/loader:1820:10)
    at Module.load (node:internal/modules/cjs/loader:1423:32)
    at Function._load (node:internal/modules/cjs/loader:1246:12)
    at TracingChannel.traceSync (node:diagnostics_channel:322:14)
    at wrapModuleLoad (node:internal/modules/cjs/loader:235:24)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:171:5)
    at node:internal/main/run_main_module:36:49 {
  originalPath: '/*'
}

Node.js v22.18.0
[nodemon] app crashed - waiting for file changes before starting...
```

#### 문제 분석. PathError: Missing parameter name at index 2: /*

"/*" 경로에서 *는 와일드카드인데 이걸 단독으로 쓰면 안 되고 이름이 필요하다는 것을 표시한다. 

app.get("/*"), (req, res) => 라는 코드가 존재하는데 과거에는 동작했지만 현재에는 에러가 발생한다. 
*가 파라미터처럼 취급되어 파라미터에 이름이 없으니까 에러가 발생하는 상황이 된다. 

#### 해결 방법. 패키지 설치 (문제상황 해결)

> app.get("*", (req, res) => 활용
> app.get("/*any", (req, res) => 활용
