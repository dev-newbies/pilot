# 까만 창(Mac-터미널, Windows-명령 프롬프트(cmd.exe)) 익숙해지기
첫 시간에 `Node.js`를 설치해봤습니다. 무작정 따라하기 세션이긴 했지만, 잠깐 살펴봤듯 까만 창(이하 CLI)에서 명령어를 실행해 봤었는데요.  
간단히 CLI에서의 경로와 경로 이동 방법, node 명령어 실행 방법을 살펴보도록 하겠습니다.

## 1. 경로
경로는 특정 폴더나 파일의 위치를 나타내며, Mac에서는 `/` 윈도우즈에서는 `₩` 기호로 폴더를 구분합니다. 이런 기호를 경로 구분자(Path Separator)라고 합니다.  

### 최상위 폴더
- Mac: `/`
- Win: `드라이브 기호:₩` - 예) C드라이브: `C:₩`

### 사용자의 홈 폴더
맥이나 윈도우즈는 모두 사용자가 기본적으로 사용하는 폴더가 있습니다. 이 폴더 안에 해당 사용자가 사용하는 Document, Downloads, Desktop 등의 폴더가 위치합니다.
- Mac: 맥의 사용자 홈 폴더는 `/Users` 아래에 위치합니다. 
    - `/Users/사용자이름`: `/Users/newt.off`
- Win: 윈도우즈는 버전별로 상이하지만 10에서는 `C:₩Users` 아래에 위치합니다.
    - `C:₩Users₩사용자이름`: `C:₩Users₩newt.off`

### 현재 경로 확인
- Mac: `pwd`
    - Print Working Directory를 줄인 명령어이며, 현재 위치해 있는 경로를 출력(Print) 합니다.
- Win: `cd`
    - CD 명령어는 디렉토리를 이동하는 명령어이지만, 현재 디렉토리를 확인하는 용도로도 쓰입니다.
    
## 2. 폴더 만들기
폴더는 CLI에서는 디렉토리(Directory)라고 하며, 줄여서 dir로 표현하기도 합니다. 
- Mac: `mkdir 만들디렉토리의이름`
- Win: `md 만들디렉토리의이름`

## 3. 디렉토리 이동하기
파인더나 탐색기에서 폴더를 더블 클릭하여 안으로 들어가는 것처럼 명령어로도 가능합니다.  
맥과 윈도우즈에서 디렉토리를 이동할 때는 동일하게 `cd`(Change Directory) 명령어를 사용합니다.
- Mac: `cd 이동할디렉토리이름`
- Win: `cd 이동할디렉토리이름`

### 상위 디렉토리로 이동하기
상위 디렉토리는 `..` 으로 표현합니다. 참고로 현재 디렉토리는 `.` 으로 표현합니다.
- Mac: `cd ..`
- Win: `cd ..`

## 4. 실습하기
사용자 홈 폴더 아래에 `workspace` 라는 디렉토리를 생성하고, 다시 `workspace` 디렉토리 안에 `javascript` 디렉토리를 만들어 `javascript` 디렉토리 안으로 이동해 봅시다.
```
/
  ㄴ Users
    ㄴ newt.off
      ㄴ workspace
        ㄴ javascript <- 디렉토리를 만들고 이동하기
```

## 5. 상대 경로와 절대 경로
현재 위치한 디렉토리 안에 있는 디렉토리로 이동하거나, 상위 디렉토리로 이동할 때는 `cd 디렉토리이름`의 형식으로 사용합니다.  
이와 같이 현재 위치를 기준으로 한 경로를 **상대경로**라고 하고, 최상위 경로(루트, 맥은 `/`, 윈도우즈는 `C:₩`)를 기준으로 표현한 경로를 절대 경로라고 합니다.  
집의 위치를 표현할 때 내가 살고 있는 집을 기준으로 `왼쪽 집, 옆집, 앞집` 등과 같이 **상대적**으로 표현할 수도 있고,  
지번 또는 도로명 주소를 이용하여 우리집과 상관없이 **절대적**인 위치로 표현할 수 있는 것과 같이 생각할 수 있습니다.  
  
실습으로 만든 `javascript` 디렉토리의 경로를 표현해본다면, 현재 위치가 `newt.off` 디렉토리에 있을 때(여러분은 `newt.off`가 아니라 각자의 사용자 아이디겠죠?)
```
C:₩
  ㄴ Users
    ㄴ newt.off <- 현재 위치
      ㄴ workspace
        ㄴ javascript <- newt.off를 기준으로 상대/절대 경로로 표현해보면?
```
- 상대 경로
    - Mac: `./workspace/javascript` 또는 `workspace/javascript`
    - Win: `.₩workspace₩javascript` 또는 `workspace₩javascript`
- 절대 경로
    - Mac: `/Users/newt.off/workspace/javascript`
    - Win: `C:₩Users₩newt.off₩workspace₩javascript`
  
`cd` 명령어를 이용할 때는 상대 경로와 절대 경로 모두 사용할 수 있습니다.
- 절대 경로로 이동
    - Mac: `cd workspace/javascript`
    - Win: `cd workspace/javascript`
- 상대 경로로 이동
    - Mac: `cd /Users/newt.off/workspace/javascript`
    - Win: `cd C:₩Users₩newt.off₩workspace₩javascript`
  
## 6. 현재 디렉토리에서 파인더/탐색기 열기
- Mac: `open .`
- Win: `explorer .`

## 7. Node.js 실행
- Mac: `node` 또는 `node 실행할_자바스크립트_파일이름`
- Win: `node` 또는 `node 실행할_자바스크립트_파일이름`
