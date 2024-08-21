# W10D3
> Day 3 of Docker


## MYSQL
> docker run -d -p [포트번호]:[포트번호] --name [컨테이너명] -e MYSQL_ROOT_PASSWORD=[비밀번호] mysql
> > 해당 포트번호가 이미 사용중 일 경우 오류가 발생하므로<br> 앞의 포트번호를 중복되지않은 포트번호로 사용하면 된다.
>
> docker exec -it [mysql 컨테이너명] mysql -u root -p
> > bash 명령어가 아닌 바로 mysql명령어를 입력할 수 있다.
>
> ### MYSQL 사용법
> > 1. TEMP
