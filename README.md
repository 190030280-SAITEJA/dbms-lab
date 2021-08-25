# dbms-lab
dbms lab


create database labexam;
use labexam;
create table if not exists customer( c_id int primary key,c_name varchar(20), photo_identity char(1), ph_no int,dob date,state varchar(20), city varchar(20),pincode int,street varchar(20),d_no int,v_id int,constraint cfk_key foreign key(v_id) references vehicle(v_id)); 
insert into customer values(41,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(42,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(43,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(44,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(45,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(46,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(47,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(48,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(49,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(50,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);


create database labexam;
use labexam;
create table if not exists vehicle( v_id int primary key,v_type varchar(20), v_name varchar(20), v_number varchar(20));
create table if not exists dealer( d_id int primary key,d_name varchar(20), state varchar(20), city varchar(20), pincode int,street varchar(15), d_no int,ph_int int);
create table if not exists edu_bus( e_id int primary key,e_name varchar(20), ph_no int,state varchar(20), city varchar(20), pincode int, street varchar(20), d_no int);
create table if not exists customer( c_id int primary key,c_name varchar(20), photo_identity char(1), ph_no int,dob date,state varchar(20), city varchar(20),pincode int,street varchar(20),d_no int,v_id int,constraint cfk_key foreign key(v_id) references vehicle(v_id)); 
create table if not exists branch(b_id int primary key, b_name varchar(20), state varchar(20), city varchar(20), pincode int,street varchar(20), d_no int,phno1 int, phno2 int, c_id int, v_id int, e_id int,constraint bvfk_key foreign key(v_id) references vehicle(v_id), constraint bcfk_key foreign key(c_id) references customer(c_id), constraint befk_key foreign key(e_id) references e_bus(e_id)); 
create table if not exists renewal(b_id int,c_id int,check_license_period int,constraint rbfk_key foreign key(b_id) references branch(b_id), constraint rcfk_key foreign key(c_id) references customer(c_id)); 
create table if not exists registration(c_id int,v_id int, d_id int, date date,primary key(c_id,v_id,d_id),constraint vfk_key foreign key(v_id) references vehicle(v_id), constraint cefk_key foreign key(c_id) references customer(c_id), constraint dfk_key foreign key(d_id) references dealer(d_id)); 
create table if not exists contract_permission(v_id int,b_id int,no_of_days int, amount_per_seat int,constraint fk foreign key(v_id) references vehicle(v_id), constraint ffk foreign key(b_id) references branch(b_id));


create table if not exists customer( c_id int primary key,c_name varchar(20), photo_identity char(1), ph_no int,dob date,state varchar(20), city varchar(20),pincode int,street varchar(20),d_no int,v_id int,constraint cfk_key foreign key(v_id) references vehicle(v_id)); 
insert into customer values(41,'raju',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,'y',3);
insert into customer values(42,'hari',19-06-2016,'perambur','mylapur','tamil nadu',500211,1122334455,20,'n',2);
insert into customer values(43,'giri',20-01-1995,'hyderabad','sr nagar','telangana',500079,8877665544,30,'y',4);
insert into customer values(44,'ramu',17-07-1996,'vijayawada','benz circle','andhra pradesh',512345,765456321,40,'y',5);
insert into customer values(45,'rahul',08-12-1995,'guntur','raju nagar','andhra pradesh',523022,9999999999,50,'y',7);
insert into customer values(46,'gopi',13-08-1979,'hyderabad','gachiboeli','telangana',567089,7787777775,10,'n',1);
insert into customer values(47,'karthik',15-01-2004,'guntur','chandra mouli nagar','andhra pradesh',546789,7788776633210,'n',6);
insert into customer values(48,'gopal',06-12-2000,'hyderabad','amerpet','telangana',500023,6734556345,30,'y',8);
insert into customer values(49,'dinesh',10-12-2001,'hyerabads','kondapur','telangana',502033,6794537212,30,'n',10);
insert into customer values(50,'suresh',25-03-1999,'vijaywada','poranki','andhra pradesh',512022,7896543233,20,'y',9);

create table if not exists customer1( c_id int primary key,c_name varchar(20), photo_identity char(1), dob date, city varchar(20),street varchar(20),state varchar(20),pincode int,ph_no int,d_no int,v_id int,constraint cfk_key foreign key(v_id) references vehicle(v_id)); 
insert into customer1 values(41,'raju','y',13-09-1996,'guntur','ramgopal','andhra pradesh',500213,9123456789,10,3);
insert into customer1 values(42,'hari','n',19-06-2016,'perambur','mylapur','tamil nadu',500211,1122334455,20,2);
insert into customer1 values(43,'giri','y',20-01-1995,'hyderabad','sr nagar','telangana',500079,8877665544,30,4);
insert into customer1 values(44,'ramu','y',17-07-1996,'vijayawada','benz circle','andhra pradesh',512345,765456321,40,5);
insert into customer1 values(45,'rahul','y',08-12-1995,'guntur','raju nagar','andhra pradesh',523022,9999999999,50,7);
insert into customer1 values(46,'gopi','n',13-08-1979,'hyderabad','gachiboeli','telangana',567089,7787777775,10,1);
insert into customer1 values(47,'karthik','n',15-01-2004,'guntur','chandra mouli nagar','andhra pradesh',546789,7788776633210,6);
insert into customer1 values(48,'gopal','y',06-12-2000,'hyderabad','amerpet','telangana',500023,6734556345,30,8);
insert into customer1 values(49,'dinesh','n',10-12-2001,'hyerabads','kondapur','telangana',502033,6794537212,30,10);
insert into customer1 values(50,'suresh','y',25-03-1999,'vijaywada','poranki','andhra pradesh',512022,7896543233,20,9);
