# Github-Actions

Github Actions 일단 무작정 따라해보기 

해당 문서는 [생활코딩의 github actions](https://www.youtube.com/watch?v=uBOdEEzjxzE) 를 참고하였습니다. 

1. github에 새로운 repository를 생성한다.
2. 해당 repo를 local에 연결 시키고 hello.txt 파일을 생성 후 간단한 글을 적고 remote에 push 한다. 
3. Actions 탭으로 들어가서 <set up a workflow yourself>를 선택한다.
4. 그러면 <repository_name>/.github/workflows 내부에 어떤 yaml 파일을 생성할 수 있게끔 되어있다.


### json vs. yaml
```
json: 
  - rigid
  - better for data interchange
object: 
  - key: value
    array:
      - null_value: null
      - boolean: true
content: hello  
```
  
```
{
  "json": [
    "rigid",
    "better for data interchange"
  ],
  "object": [
    {
      "key": "value",
      "array": [
        {
          "null_value": null
        },
        {
          "boolean": true
        },
      ]
    }
  ],
  "content": "hello",
}
```
  
4. main.yaml 파일에 아래와 같이 작성한다. 
  
```
name: Hello World

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v2
    - name: Run pwd
      run: pwd
    - name: Run ls -al
      run: ls -al
    - name: Cat hello.txt
      run: cat hello.txt
```
* 해당 workflow의 이름은 Hello World 이고 
* 해당 repo에 push 라는 이벤트가 있을 시 
* jobs에 해당되는 커맨드들이 runner라는 컴퓨터 위에서 실행된다. 
* 또한 actions/checkout@v2 라는 액션을 사용하여 해당 레포에 있는 코드들을 runner에 가져와서 사용할 수 있다. 
* 기존에 hello.txt를 repo에 push 해놓았다면 runner 위에도 hello.txt가 있을테니 cat 커맨드가 정상적으로 실행될 수 있다. 
* actions에 대해서 부연 설명을 하자면 actions 탭에 marketplace라는 것이 존재하고 그곳에 다른 사람들이 만들어 놓은 액션들이  
* 존재하는데 여기서 본인에게 필요한 액션들을 가져와서 사용할 수 있다. 
  
