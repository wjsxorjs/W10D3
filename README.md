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
> > 1. create database [DB명] default character set utf8;
> > 2. show databses;로 생성 확인
> > 3. use [Db명];로 DB 사용
> > 4. show tables; 로 테이블 확인
> > 5. create user [유저명]@[호스트범위] identified by [비밀번호];
> > 6. grant all privileges on [DB명].* to [유저명]@[호스트범위] with grant option;
> > 7. flush privileges;
> > 8. exit로 나간 후 docker exec -it [mysql 컨테이너명] mysql -u [유저명] -p로 접속
> > 9. use [DB명];
> > 10. create table [테이블명](<br>
> >  -> idx bigint auto_increment,<br>
> >  -> title varchar(20),<br>
> >  -> CONSTRINT PRIMARY KEY(idx)<br>
> >     );<br>
> > 11. show tables;로 테이블 생성 확인
