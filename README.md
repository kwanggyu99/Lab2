# Lab2
쉘 스크립트 기본 문법

## 변수
변수에 넣는 모든 값은 문자열 (숫자를 입력해도 문자로 취급)


변수 이름은 대소문자로 구분 ($aa != $AA )


변수를 대입할 떄 '=' 좌우에는 공백이 없어야 한다.(a=Hello)


1. 입력과 출력

>'$'라는 문자가 들어간 글자는 ''로 묶거나 앞에 '\'를 붙여야한다.


>출력은 echo를 활용합니다. 

>echo "hello world"


2. 숫자 계산
>expr 활용하기


>괄호를 사용하려면 그 앞에 꼭 역슬래시(\) 붙여야한다.


>+,-,/와 달리 *는 앞에 역슬래시(\)를 붙여야한다.


>실수 연산을 위해서는 | bc 활용해야 한다.
```
num1=100
num2=`expr $num1 + 200`
echo $num2 -> 300
```

3.파라미터 변수


>명령어에 포함된 단어를 각자 $변수 형식으로 지정


>apt -y install gftp


명령 | apt | -y |install | gftp
------ | ---- | ---- | ---- | -----
피라미터 변수 | $0 | $1 | $2 | $3

## if문
```
#!/bin/sh
if [ "woo" == "woo" ]
then
   echo "참입니다."
else
  echo "거짓입니다."
fi
exit 0
```
> and는 &&, or은 ||을 활용하여 관계 연산자 사용 가능합니다.
## case문
```
#!/bin/sh
case "$1" in
  start)
    echo "시작";;
  stop)
    echo "중지";;
  restart)
    echo "다시 시작";;
  *)
    echo "뭔지 모름";;
esac
exit 0
```

## for문
```
for 변수 in 값1 값2 값3
do
   반복할 문장
done
``` 
## while문
```
#!/bin/sh
while [ 1 ]
do
  echo "우분투  20.04 LTS"
done
exit 0
```

## 사용자 정의 함수
```
함수 이름(){
  내용들
}
함수이름
