# Orafce

Orafce - Free and open source Oracle compatible function and operators sets.

web： https://pgxn.org/dist/orafce/
git（下载release的包）： https://github.com/orafce/orafce
blog： https://yq.aliyun.com/articles/230



### 配置使用步骤

0 安装依赖

yum -y install bison flex

1源码编译安装pg10
cd pg10
./configure --prefix=/home/postgres/pgdb10/ --with-openssl --with-libxml --with-libxslt --enable-thread-safety --with-zlib --without-selinux --enable-debug
make -j4; make install
cd contrib/
make -j4; make install

2安装orafce
unzip orafce-3.6.1.zip
cd orafce-3.6.1
export PATH=/home/postgres/pgdb10/bin/:$PATH
make; makeinstall

3初始化数据库并创建orafce扩展
```./initdb -D ../data```
./psql postgres
psql (10.5)
Type "help" for help.

postgres=# create extension orafce ;
CREATE EXTENSION

postgres=# \df                                                                                                            List of functions
 Schema |        Name         |      Result data type       |                                                                        Argument data types                                                                         |  Type  
--------+---------------------+-----------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------+--------
 public | bitand              | bigint                      | bigint, bigint                                                                                                                                                     | normal
 public | cosh                | double precision            | double precision                                                                                                                                                   | normal
 public | decode              | bigint                      | anyelement, anyelement, bigint                                                                                                                                     | normal
 public | decode              | bigint                      | anyelement, anyelement, bigint, anyelement, bigint                                                                                                                 | normal
 public | decode              | bigint                      | anyelement, anyelement, bigint, anyelement, bigint, anyelement, bigint                                                                                             | normal
 public | decode              | bigint                      | anyelement, anyelement, bigint, anyelement, bigint, anyelement, bigint, bigint                                                                                     | normal
 public | decode              | bigint                      | anyelement, anyelement, bigint, anyelement, bigint, bigint                                                                                                         | normal
 public | decode              | bigint                      | anyelement, anyelement, bigint, bigint                                                                                                                             | normal
 public | decode              | character                   | anyelement, anyelement, character                                                                                                                                  | normal
 public | decode              | character                   | anyelement, anyelement, character, anyelement, character                                                                                                           | normal
 public | decode              | character                   | anyelement, anyelement, character, anyelement, character, anyelement, character                                                                                    | normal
 public | decode              | character                   | anyelement, anyelement, character, anyelement, character, anyelement, character, character                                                                         | normal
 public | decode              | character                   | anyelement, anyelement, character, anyelement, character, character                                                                                                | normal
 public | decode              | character                   | anyelement, anyelement, character, character                                                                                                                       | normal
 public | decode              | date                        | anyelement, anyelement, date                                                                                                                                       | normal
 public | decode              | date                        | anyelement, anyelement, date, anyelement, date                                                                                                                     | normal
 public | decode              | date                        | anyelement, anyelement, date, anyelement, date, anyelement, date                                                                                                   | normal
 public | decode              | date                        | anyelement, anyelement, date, anyelement, date, anyelement, date, date                                                                                             | normal
 public | decode              | date                        | anyelement, anyelement, date, anyelement, date, date                                                                                                               | normal
 public | decode              | date                        | anyelement, anyelement, date, date                                                                                                                                 | normal
 public | decode              | integer                     | anyelement, anyelement, integer                                                                                                                                    | normal
 public | decode              | integer                     | anyelement, anyelement, integer, anyelement, integer                                                                                                               | normal
 public | decode              | integer                     | anyelement, anyelement, integer, anyelement, integer, anyelement, integer                                                                                          | normal
 public | decode              | integer                     | anyelement, anyelement, integer, anyelement, integer, anyelement, integer, integer                                                                                 | normal
 public | decode              | integer                     | anyelement, anyelement, integer, anyelement, integer, integer                                                                                                      | normal
 public | decode              | integer                     | anyelement, anyelement, integer, integer                                                                                                                           | normal
 public | decode              | numeric                     | anyelement, anyelement, numeric                                                                                                                                    | normal
 public | decode              | numeric                     | anyelement, anyelement, numeric, anyelement, numeric                                                                                                               | normal
 public | decode              | numeric                     | anyelement, anyelement, numeric, anyelement, numeric, anyelement, numeric                                                                                          | normal
 public | decode              | numeric                     | anyelement, anyelement, numeric, anyelement, numeric, anyelement, numeric, numeric                                                                                 | normal
 public | decode              | numeric                     | anyelement, anyelement, numeric, anyelement, numeric, numeric                                                                                                      | normal
 public | decode              | numeric                     | anyelement, anyelement, numeric, numeric                                                                                                                           | normal
 public | decode              | text                        | anyelement, anyelement, text                                                                                                                                       | normal
 public | decode              | text                        | anyelement, anyelement, text, anyelement, text                                                                                                                     | normal
 public | decode              | text                        | anyelement, anyelement, text, anyelement, text, anyelement, text                                                                                                   | normal
 public | decode              | text                        | anyelement, anyelement, text, anyelement, text, anyelement, text, text                                                                                             | normal
 public | decode              | text                        | anyelement, anyelement, text, anyelement, text, text                                                                                                               | normal
 public | decode              | text                        | anyelement, anyelement, text, text                                                                                                                                 | normal
 public | decode              | timestamp without time zone | anyelement, anyelement, timestamp without time zone                                                                                                                | normal
 public | decode              | timestamp without time zone | anyelement, anyelement, timestamp without time zone, anyelement, timestamp without time zone                                                                       | normal
 public | decode              | timestamp without time zone | anyelement, anyelement, timestamp without time zone, anyelement, timestamp without time zone, anyelement, timestamp without time zone                              | normal
 public | decode              | timestamp without time zone | anyelement, anyelement, timestamp without time zone, anyelement, timestamp without time zone, anyelement, timestamp without time zone, timestamp without time zone | normal
 public | decode              | timestamp without time zone | anyelement, anyelement, timestamp without time zone, anyelement, timestamp without time zone, timestamp without time zone                                          | normal
 public | decode              | timestamp without time zone | anyelement, anyelement, timestamp without time zone, timestamp without time zone                                                                                   | normal
 public | decode              | timestamp with time zone    | anyelement, anyelement, timestamp with time zone                                                                                                                   | normal
 public | decode              | timestamp with time zone    | anyelement, anyelement, timestamp with time zone, anyelement, timestamp with time zone                                                                             | normal
 public | decode              | timestamp with time zone    | anyelement, anyelement, timestamp with time zone, anyelement, timestamp with time zone, anyelement, timestamp with time zone                                       | normal
 public | decode              | timestamp with time zone    | anyelement, anyelement, timestamp with time zone, anyelement, timestamp with time zone, anyelement, timestamp with time zone, timestamp with time zone             | normal
 public | decode              | timestamp with time zone    | anyelement, anyelement, timestamp with time zone, anyelement, timestamp with time zone, timestamp with time zone                                                   | normal
 public | decode              | timestamp with time zone    | anyelement, anyelement, timestamp with time zone, timestamp with time zone                                                                                         | normal
 public | decode              | time without time zone      | anyelement, anyelement, time without time zone                                                                                                                     | normal
 public | decode              | time without time zone      | anyelement, anyelement, time without time zone, anyelement, time without time zone                                                                                 | normal
 public | decode              | time without time zone      | anyelement, anyelement, time without time zone, anyelement, time without time zone, anyelement, time without time zone                                             | normal
 public | decode              | time without time zone      | anyelement, anyelement, time without time zone, anyelement, time without time zone, anyelement, time without time zone, time without time zone                     | normal
 public | decode              | time without time zone      | anyelement, anyelement, time without time zone, anyelement, time without time zone, time without time zone                                                         | normal
 public | decode              | time without time zone      | anyelement, anyelement, time without time zone, time without time zone                                                                                             | normal
 public | dump                | character varying           | "any"                                                                                                                                                              | normal
 public | dump                | character varying           | "any", integer                                                                                                                                                     | normal
 public | dump                | character varying           | text                                                                                                                                                               | normal
 public | dump                | character varying           | text, integer                                                                                                                                                      | normal
 public | nanvl               | double precision            | double precision, character varying                                                                                                                                | normal
 public | nanvl               | double precision            | double precision, double precision                                                                                                                                 | normal
 public | nanvl               | numeric                     | numeric, character varying                                                                                                                                         | normal
 public | nanvl               | numeric                     | numeric, numeric                                                                                                                                                   | normal
 public | nanvl               | real                        | real, character varying                                                                                                                                            | normal
 public | nanvl               | real                        | real, real                                                                                                                                                         | normal
 public | nvarchar2           | nvarchar2                   | nvarchar2, integer, boolean                                                                                                                                        | normal
 public | nvarchar2_transform | internal                    | internal                                                                                                                                                           | normal
 public | nvarchar2in         | nvarchar2                   | cstring, oid, integer                                                                                                                                              | normal
 public | nvarchar2out        | cstring                     | nvarchar2                                                                                                                                                          | normal
 public | nvarchar2recv       | nvarchar2                   | internal, oid, integer                                                                                                                                             | normal
 public | nvarchar2send       | bytea                       | nvarchar2                                                                                                                                                          | normal
 public | nvarchar2typmodin   | integer                     | cstring[]                                                                                                                                                          | normal
 public | nvarchar2typmodout  | cstring                     | integer                                                                                                                                                            | normal
 public | nvl                 | anyelement                  | anyelement, anyelement                                                                                                                                             | normal
 public | nvl2                | anyelement                  | anyelement, anyelement, anyelement                                                                                                                                 | normal
 public | sinh                | double precision            | double precision                                                                                                                                                   | normal
 public | tanh                | double precision            | double precision                                                                                                                                                   | normal
 public | to_multi_byte       | text                        | str text                                                                                                                                                           | normal
 public | to_single_byte      | text                        | str text                                                                                                                                                           | normal
 public | varchar2            | varchar2                    | varchar2, integer, boolean                                                                                                                                         | normal
 public | varchar2_transform  | internal                    | internal                                                                                                                                                           | normal
 public | varchar2in          | varchar2                    | cstring, oid, integer                                                                                                                                              | normal
 public | varchar2out         | cstring                     | varchar2                                                                                                                                                           | normal
 public | varchar2recv        | varchar2                    | internal, oid, integer                                                                                                                                             | normal
 public | varchar2send        | bytea                       | varchar2                                                                                                                                                           | normal
 public | varchar2typmodin    | integer                     | cstring[]                                                                                                                                                          | normal
 public | varchar2typmodout   | cstring                     | integer                                                                                                                                                            | normal
(88 rows)

postgres=# \dv
         List of relations
 Schema | Name | Type |    Owner    
--------+------+------+-------------
 public | dual | view | liuyuanyuan
(1 row)

postgres=# \d+ dual
                                  View "public.dual"
 Column |       Type        | Collation | Nullable | Default | Storage  | Description 
--------+-------------------+-----------+----------+---------+----------+-------------
 dummy  | character varying |           |          |         | extended | 
View definition:
 SELECT 'X'::character varying AS dummy;

postgres=# \dn
      List of schemas
     Name     |    Owner    
--------------+-------------
 dbms_alert   | liuyuanyuan
 dbms_assert  | liuyuanyuan
 dbms_output  | liuyuanyuan
 dbms_pipe    | liuyuanyuan
 dbms_random  | liuyuanyuan
 dbms_utility | liuyuanyuan
 oracle       | liuyuanyuan
 plunit       | liuyuanyuan
 plvchr       | liuyuanyuan
 plvdate      | liuyuanyuan
 plvlex       | liuyuanyuan
 plvstr       | liuyuanyuan
 plvsubst     | liuyuanyuan
 public       | liuyuanyuan
 utl_file     | liuyuanyuan
(15 rows)

postgres=# \df dbms_alert.*
                                                            List of functions
   Schema   |      Name      | Result data type |                              Argument data types                              |  Type   
------------+----------------+------------------+-------------------------------------------------------------------------------+---------
 dbms_alert | _signal        | void             | name text, message text                                                       | normal
 dbms_alert | defered_signal | trigger          |                                                                               | trigger
 dbms_alert | register       | void             | name text                                                                     | normal
 dbms_alert | remove         | void             | name text                                                                     | normal
 dbms_alert | removeall      | void             |                                                                               | normal
 dbms_alert | set_defaults   | void             | sensitivity double precision                                                  | normal
 dbms_alert | signal         | void             | _event text, _message text                                                    | normal
 dbms_alert | waitany        | record           | OUT name text, OUT message text, OUT status integer, timeout double precision | normal
 dbms_alert | waitone        | record           | name text, OUT message text, OUT status integer, timeout double precision     | normal
(9 rows)







