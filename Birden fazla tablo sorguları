a={1,2,4,8}
b={1,2,3,7}

select * from a
inner join b on a.sayi=b.sayi // 1,2

select * from a
left outer join b on a.sayi=b.sayi //1,2,4,8,1,2,null,null

select * from b
left outer join a on a.sayi=b.sayi //1,2,3,7,1,2,null,null

select * from b
right outer join a on a.sayi=b.sayi //1,2,4,8,1,2,null,null

select * from a
right outer join b on a.sayi=b.sayi //1,2,3,7,1,2,null,null


use galeri
create table musteri(
Mno int primary key identity(1,1),
Madi nvarchar(50),
Msoyadi nvarchar(50),
Madres nvarchar(50),
Mtelefon nvarchar(50)
);

create table araclar(
Aracno int identity(1,1) primary key,
yil int,
model nvarchar(50),
marka nvarchar(50),
plaka nvarchar(50),
fiyat float
);

create table satislar(
satisNo int primary key not null,
MNo int foreign key (Mno) references musteri(Mno),
AracNo int foreign key (Aracno) references araclar(Aracno),
SatisTarihi datetime,
Fiyat float
);

create table alislar(
alisNo int primary key not null,
MNo int foreign key (Mno) references musteri(Mno),
AracNo int foreign key (Aracno) references araclar(Aracno),
AlisTarihi datetime,
Fiyat float
);

insert into musteri 
values('Fatma Nur','Kılıçkaya','Kayseri','45667')
insert into musteri 
values('Sıla','Aydoğdu','Ankara','12354')
insert into musteri 
values('İbrahim','Metin','İstanbul','78652')
insert into musteri 
values('Mustafa','Erdoğan','İzmir','75525')
insert into musteri 
values('Furkan','Altıntop','Manisa','48963')


insert into araclar values ( '2002' , 'GLA' ,'mercedes', '38G12', '65000');
insert into araclar values ( '2020' , 'M5' ,'BMW', '47S21', '185000');
insert into araclar values ( '2025' , 'EGEA' ,'Fiat', '36Z10', '1800000');
insert into araclar values ( '2023' , 'COROLLA' ,'toyota', '58A14', '85000');
insert into araclar values ( '2024' , 'A8' ,'audi', '30B84', '95000');


insert into satislar values(1,1,1,'2024','800000');
insert into satislar values(2,2,3,'2023','500000');
insert into satislar values(3,3,5,'2022','20000000');
insert into satislar values(4,4,2,'2024','30000000');

select * from alislar
insert into alislar values(3,1,2,'2025','882000');
insert into alislar values(5,1,5,'2024','800034');
insert into alislar values(2,1,4,'2023','8820003');
insert into alislar values(4,1,1,'2021','88200034');
