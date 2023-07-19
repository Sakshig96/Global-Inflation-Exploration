SELECT*
FROM GlobalInflation

SELECT*
FROM CountriesEconomy

---1---Global Exploration Of Inflation Per Series Name----
      ---....Global Headline Consumer Price Inflation Rates Comparison.....

SELECT Country, Inflation_Series_Name, Year2018, Year2019, Year2020, Year2021, Year2022
FROM GlobalInflation
WHERE Inflation_Series_Name= 'Headline Consumer Price Inflation'
ORDER BY Country


      ---....Global Energy Consumer Price Inflation Rates Comparison.....

SELECT Country, Inflation_Series_Name, Year2018, Year2019, Year2020, Year2021, Year2022
FROM GlobalInflation
WHERE Inflation_Series_Name= 'Energy Consumer Price Inflation'
ORDER BY Country

     ---....Global Food Consumer Price Inflation Rates Comparison.....

SELECT Country, Inflation_Series_Name, Year2018, Year2019, Year2020, Year2021, Year2022
FROM GlobalInflation
WHERE Inflation_Series_Name= 'Food Consumer Price Inflation'
ORDER BY Country



     ---....Global Producer Price Inflation Rates Comparison.....

SELECT Country, Inflation_Series_Name, Year2018, Year2019, Year2020, Year2021, Year2022
FROM GlobalInflation
WHERE Inflation_Series_Name= 'Producer Price Inflation'
ORDER BY Country


     ---....Global Official Core Consumer Price Inflation Rates Comparison.....

SELECT Country, Inflation_Series_Name, Year2018, Year2019, Year2020, Year2021, Year2022
FROM GlobalInflation
WHERE Inflation_Series_Name= 'Official Core Consumer Price Inflation'
ORDER BY Country


------2-------Analaysis Of Countries & Regions Inflation------

    -----Regions With Highest Inflation Rates Before Covid19----

SELECT DISTINCT CtryEcs.Region, GlobInfl.Inflation_Series_Name, MAX(GlobInfl.Year2018) AS MaxInflation
FROM GlobalInflation AS GlobInfl
JOIN CountriesEconomy AS CtryEcs ON GlobInfl.Country = CtryEcs.Country
GROUP BY CtryEcs.Region, GlobInfl.Inflation_Series_Name
ORDER BY MaxInflation DESC

    -----Countries With Highest Inflation Rates Before Covid19----

SELECT TOP 10 Country, Inflation_Series_Name, Year2018
FROM GlobalInflation
ORDER BY Country DESC

  -----Malawi's Inflation Rates Before Covid19---- 
SELECT Country, Inflation_Series_Name, Year2018
FROM GlobalInflation
WHERE Country= 'Malawi'


 -----3----Productivity, Literacy And Other Factors With Inflation-------

    -----Industry, Agriculture & Service Vs Highest Producer Price Inflation Per TOP 10 Countries In The Past 4years---

	
SELECT TOP 10 CtryEcs.Country, CtryEcs.Industry, CtryEcs.Agriculture, CtryEcs.Service, GlobInfl.Inflation_Series_Name, GlobInfl.Year2018, GlobInfl.Year2019, GlobInfl.Year2020, GlobInfl.Year2021, GlobInfl.Year2022
FROM GlobalInflation AS GlobInfl
JOIN CountriesEconomy AS CtryEcs 
ON GlobInfl.Country = CtryEcs.Country
WHERE GlobInfl.Inflation_Series_Name = 'Producer Price Inflation'
ORDER BY (GlobInfl.Year2018 + GlobInfl.Year2019 + GlobInfl.Year2020 + GlobInfl.Year2021 + GlobInfl.Year2022) DESC


 -----Industry, Agriculture & Service Vs Highest Producer Price Inflation Per TOP 10 Countries In The Past 4years---


SELECT TOP 10 CtryEcs.Country, CtryEcs.Industry, CtryEcs.Agriculture, CtryEcs.Service, GlobInfl.Inflation_Series_Name, GlobInfl.Year2018, GlobInfl.Year2019, GlobInfl.Year2020, GlobInfl.Year2021, GlobInfl.Year2022
FROM GlobalInflation AS GlobInfl
JOIN CountriesEconomy AS CtryEcs 
ON GlobInfl.Country = CtryEcs.Country
WHERE GlobInfl.Inflation_Series_Name = 'Official Core Consumer Price Inflation'
ORDER BY (GlobInfl.Year2018 + GlobInfl.Year2019 + GlobInfl.Year2020 + GlobInfl.Year2021 + GlobInfl.Year2022) DESC


 -----The relationship between thefood consumer price inflation & percentage of GDP contributed by the agriculture sector

 SELECT TOP 10 CtryEcs.Country, CtryEcs.Agriculture, GlobInfl.Inflation_Series_Name, GlobInfl.Year2018, GlobInfl.Year2019, GlobInfl.Year2020, GlobInfl.Year2021, GlobInfl.Year2022
FROM GlobalInflation AS GlobInfl
JOIN CountriesEconomy AS CtryEcs 
ON GlobInfl.Country = CtryEcs.Country
WHERE GlobInfl.Inflation_Series_Name = 'Food Consumer Price Inflation'
ORDER BY (GlobInfl.Year2018 + GlobInfl.Year2019 + GlobInfl.Year2020 + GlobInfl.Year2021 + GlobInfl.Year2022) DESC


------The relationship between thefood consumer price inflation & percentage of GDP contributed by the agriculture sector in Malawi in 2022--

 SELECT CtryEcs.Country, CtryEcs.Agriculture, GlobInfl.Inflation_Series_Name, GlobInfl.Year2022
FROM GlobalInflation AS GlobInfl
JOIN CountriesEconomy AS CtryEcs 
ON GlobInfl.Country = CtryEcs.Country
WHERE GlobInfl.Inflation_Series_Name = 'Food Consumer Price Inflation' AND GlobInfl.Country= 'Malawi'



SELECT CtryEcs.Country,CtryEcs.GDP_per_capita,GlobInfl.Inflation_Series_Name, GlobInfl.Year2018, GlobInfl.Year2019, GlobInfl.Year2020, GlobInfl.Year2021, GlobInfl.Year2022
FROM GlobalInflation AS GlobInfl
JOIN CountriesEconomy AS CtryEcs 
ON GlobInfl.Country = CtryEcs.Country
WHERE GlobInfl.Inflation_Series_Name IN ('Food Consumer Price Inflation', 'Official Core Consumer Price Inflation', 'Producer Price Inflation', 'Headline Consumer Price Inflation', 'Energy Consumer Price Inflation')
AND GlobInfl.Country= 'Malawi'
ORDER BY (GlobInfl.Year2018 + GlobInfl.Year2019 + GlobInfl.Year2020 + GlobInfl.Year2021 + GlobInfl.Year2022) DESC
