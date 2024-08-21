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
> > 12. INSERT INTO [테이블명] VALUES ([데이터]);로 데이터 생성
> > 13. SELECT * FROM [테이블명];으로 데이터 생성 확인
> > 14. commit;으로 테이블 수정 적용
> 
> ### MYSQL 저장 위치 및 VOLUME
> > 1. docker exec -it [mysql 컨테이너명] bash
> > 2. bash에서 cd ./var/lib/mysql
> > 3. 해당 위치는 mysql의 DB가 저장되는 위치
> > 4. exit로 bash에서 빠져나오기
> > 5. docker run -d -p [연결하는 포트]:[연결할 포트] -v [Volume 저장위치]:[DB 저장위치]<br> -e MYSQL_ROOT_PASSWORD=[비밀번호] --name [컨테이너명] mysql:8.0
> > 6. docker exec -it [mysql 컨테이너명] mysql -u root -p
> > 7. " MYSQL 사용법 " 반복
> > 8. docker stop/rm [컨테이너명] : 컨테이너 정지 후 삭제
> > 9. " 5, 6번 항목 " 반복
> > 10. DB와 Table이 저장되어있는지 확인
