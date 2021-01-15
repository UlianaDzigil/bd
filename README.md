# bd
Б-1.
2. ORAPWD)
3. 
CREATE SMALLFILE TEMPORARY TABLESPACE НАЗВА 
TEMPFILE 'ПОВНИЙ ШЛЯХ ДО ФАЙЛУ' SIZE 10000M 
AUTOEXTEND OFF
EXTENT MANAGEMENT LOCAL UNIFORM SIZE 1M
SEGMENT SPACE MANAGEMENT AUTO;


Б-2.
2. DBCA
3. 
CREATE ROLE role1;
GRANT COMMENT ANY TABLE TO role1;
GRANT DELETE ANY TABLE TO role1;
GRANT REFERENCES ON TABLE1 TO role1;
GRANT REFERENCES ON TABLE2 TO role1;
GRANT REFERENCES ON TABLE3 TO role1;
GRANT SELECT, UPDATE, DELETE ON VIEW1 TO role1;



Б-3.
2. LSNRCTL
3. 
CREATE ROLE role1 IDENTIFIED BY 5555;
GRANT SELECT ANY TABLE TO role1;
GRANT UPDATE ANY TABLE TO role1;
GRANT UPDATE, DELETE, ALTER ON TABLE1 TO role1;
GRANT INDEX ON TABLE2 TO role1;

Б-4.
2. NETCA
3. 
CREATE ROLE role1;
GRANT LOCK ANY TABLE TO role1;
GRANT CREATE, UPDATE, DELETE ANY USER TO role1;
GRANT INDEX ON TABLE1 TO role1;
GRANT EXECUTE ON FUNC1 TO role1; 
GRANT EXECUTE ON PROC1 TO role1; 

Б-5.
2.  клієнтського та серверного процесів
3.
CREATE ROLE role1 IDENTIFIED BY 777;
GRANT CREATE, UPDATE, DELETE ANY ROLE TO role1;
GRANT CREATE ANY TABLE TO role1;
GRANT ALTER ON SEQ1 TO role1; 
GRANT UPDATE, DELETE, ALTER ON TABLE1 TO role1;
4 фото
5)
select T1.ID, T1.NAME, T2.ID_S from T1
	right join T2 on T1.IDSpec = T2.ID_S
	where T2.ID_S=2 and T1.ID < 7(17 по условию);
  

Б-6.
2.  SGA
3.
REVOKE CREATE ANY TABLE TO user;
REVOKE ALTER ANY TABLESPACE TO user;
REVOKE UPDATE, DELETE, ALTER ON TABLE1 TO user;



Б-7.
2.  smallfile, bigfile
3.
REVOKE COMMENT ANY TABLE TO user;
REVOKE DELETE ANY TABLE TO user;
REVOKE REFERENCES ON TABLE1 TO user;
REVOKE REFERENCES ON TABLE2 TO user;
REVOKE REFERENCES ON TABLE3 TO user;
REVOKE SELECT, UPDATE, DELETE ON VIEW1 TO user;




Б-8.
2. в теории 32 вопрос


Б-45.
2.  ALL_USERS, DBA_USERS
3.
CREATE SMALLFILE TABLESPACE НАЗВА_ТАБЛИЧН_ПРОСТОРУ 
DATAFILE ‘ПОВНИЙ ШЛЯХ ФІЗИЧНОГО ФАЙЛУ З ДАНИМИМ’ SIZE 5M 
AUTOEXTEND ON NEXT 50M MAXSIZE UNLIMITED
LOGGING 
EXTENT MANAGEMENT LOCAL AUTOALLOCATE 
SEGMENT SPACE MANAGEMENT AUTO
DEFAULT COMPRESS FOR OLTP;



create table T1(
  2  ID number(10),
  3  NAME varchar2(10),
  4  IDSpec number(10)
  5  );
  
  create table T2(
  2  ID_S number(10),
  3  NAME_S varchar2(10)
  4  );
  
   insert into T2(ID_S, NAME_S) values (1, 'Спец1');

1 row created.

SQL> insert into T2(ID_S, NAME_S) values (2, 'Спец2');

1 row created.

SQL> insert into T2(ID_S, NAME_S) values (3, 'Спец3');

1 row created.

SQL> insert into T2(ID_S, NAME_S) values (4, 'Спец4');

1 row created.

SQL> insert into T2(ID_S, NAME_S) values (5, 'Спец5');

1 row created.

SQL> insert into T2(ID_S, NAME_S) values (6, 'Спец6');

1 row created.

SQL> insert into T2(ID_S, NAME_S) values (7, 'Спец7');

1 row created.

SQL> alter table T2 add constraint PK_T2 primary key (ID_S);

Table altered.

SQL> insert into T1(ID, NAME, IDSpec) values (11, 'N1', 1);

1 row created.

SQL> insert into T1(ID, NAME, IDSpec) values (12, 'N2', 2);

1 row created.

SQL> insert into T1(ID, NAME, IDSpec) values (13, 'N3', 2);

1 row created.

SQL> insert into T1(ID, NAME, IDSpec) values (14, 'N4', null);

1 row created.

SQL> insert into T1(ID, NAME, IDSpec) values (15, 'N5', 5);

1 row created.

SQL> insert into T1(ID, NAME, IDSpec) values (16, 'N6', 7);

1 row created.

SQL> insert into T1(ID, NAME, IDSpec) values (17, 'N7', 3);

1 row created.

SQL> alter table T1 add constraint PK_T1 primary key (ID);

Table altered.
