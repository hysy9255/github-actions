# Github-Actions

Github Actions 일단 무작정 따라해보기 

해당 문서는 [생활코딩의 github actions](https://www.youtube.com/watch?v=uBOdEEzjxzE) 를 참고하였습니다. 


1. github에 새로운 repository를 생성한다.
2. Actions 탭으로 들어가서 <set up a workflow yourself>를 선택한다.
3. 그러면 <repository_name>/.github/workflows 내부에 어떤 yaml 파일을 생성할 수 있게끔 되어있다.

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
