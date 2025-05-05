--BİRDEN FAZLA TABLO ÜZERİNDEN SORGULAR
--1.	Satış yapılan müşterilerin isimlerini listelemek için gerekli SQL ifadesini yazınız.
--JOIN
SELECT (m.mAdi+ ''+mSoyadi)as satis_yapilanlar 
FROM Satislar s
INNER JOIN MUSTERI m ON  s.mNo = m.mNo
--ALT SORGU
SELECT (mAdi+ '' + mSoyadi)as satis_yapilanlar
FROM MUSTERI WHERE mNo
IN(select mNo from Satislar)

--2.	Hangi müşteriden hangi aracın alındığını listelemek için gerekli SQL ifadesini yazınız.

SELECT * FROM alislar a 

INNER JOIN MUSTERI m on a.mNo= m.mNo
INNER JOIN ARACLAR ar on ar.aracno = a.aracNo

--3.	Her bir müşteriden alınan araçların sayısını listelemek için gerekli SQL ifadesini yazınız.


select count(alislar.mNo) from alislar 
join MUSTERI on alislar.mNo = MUSTERI.mNo


select count(mNo) from MUSTERI where mNo in(  select mNo from alislar )

--4.	Satılan araçların marka ve modelini bulmak için gerekli SQL ifadesini yazınız.-

SELECT ARACLAR.marka ,ARACLAR.model from Satislar
JOIN ARACLAR on ARACLAR.aracno=Satislar.aracNo

--5.	Toplam satış ve toplam alım tutarlarını ve bunların farkını bulmak için gerekli SQL ifadesini yazınız.

select (SELECT SUM(satisFiyati) FROM Satislar) - (select sum(alisFiyati) from alislar) as CikarilanTutar

SELECT (select SUM(satisFiyati) FROM Satislar as ToplamSatis) as ToplamSatis,
(select sum(alisFiyati) from alislar) as ToplamAlis,
(SELECT SUM(satisFiyati) FROM Satislar) - (select sum(alisFiyati) from alislar) as CikarilanTutar

--6.soru (join)

select *  from ARACLAR
join Satislar on Satislar.aracNo =ARACLAR.aracno where not exists(select Satislar.aracNo)

select * from ARACLAR where aracno
not in(select aracno from Satislar)


--7.	Her aracın ortalama satış tutarını bulmak için gerekli SQL ifadesini yazınız.
select AVG(Satislar.satisFiyati) from Satislar 
JOIN ARACLAR on Satislar.aracNo = ARACLAR.aracno

--8.	Alımı ve satışı yapılan tüm araçların marka, model ve alım-satış sayısını listelemek için gerekli SQL ifadesiniz yazınız.
SELECT *FROM ARACLAR WHERE aracno
IN (select aracno from alislar where aracno IN (select aracno from Satislar))


--9.	20000’den fazla tutara satılan araçları kimlerin hangi aracı aldığını bulmak için gerekli SQL ifadesini yazınız
select * from Satislar 
join ARACLAR on ARACLAR.aracno = Satislar.aracNo
join MUSTERI on MUSTERI.mNo = Satislar.mNo
where satisFiyati > 20000

--10.	Tokatta bulunan müşterilere satışı yapılan araçları listelemek için gerekli SQL ifadesini yazınız.
select * from Satislar
join MUSTERI on MUSTERI.mNo = Satislar.mNo
join ARACLAR on ARACLAR.aracno = Satislar.aracNo
where MUSTERI.mAdres = 'TOKAT'
