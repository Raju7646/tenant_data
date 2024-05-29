# tenant_data

create database Tenant
use Tenant

create TABLE Tenancy_histories(
id Int auto_increment,
profile_id Int,
house_id Int,
move_in_date date,
move_out_date date,
rent Int,
Bed_type varchar(255),
move_out_reason varchar(255),
PRIMARY KEY(id));


alter table Tenancy_histories
add FOREIGN KEY (profile_id,house_id)
REFERENCES Persons(PersonID);

select * from Profiles





FOREIGN KEY (profile_id) REFERENCES Profiles(profile_id),
FOREIGN KEY (house_id) REFERENCES Houses(house_id));


create TABLE Profiles ( 
profile_id int not null PRIMARY KEY auto_increment,
first_name varchar(255),
last_name varchar(255),
email varchar(255),
phone varchar(255),
city_hometown varchar(255),
pan_card varchar(255),
created_at date,
gender varchar(255),
referral_code varchar(255),
marital_status varchar(255));


create TABLE Houses(
house_id int primary KEY auto_increment,
house_type varchar(255),
bhk_details varchar(255),
bed_count int,
furnishing_type varchar(255),
Beds_vacant int);


create TABLE Addresses(
ad_id  int primary KEY auto_increment,
name varchar(255),
description text,
pincode int,
city varchar(255),
house_id int ,
FOREIGN KEY (house_id) REFERENCES Houses(house_id));



create TABLE Referrals(
ref_id int primary KEY auto_increment,
referrer_id int,
referrer_bonus_amount float,
referral_valid tinyint(1),
valid_from date,
valid_till date,
FOREIGN KEY (referrer_id) REFERENCES Profiles (profile_id));


select *from Referrals


create TABLE Employment_details (
id int primary KEY auto_increment,
profile_id int,
latest_employer varchar(255),
official_mail_id varchar(255),
yrs_experience int,
Occupational_category varchar(255),
FOREIGN KEY (profile_id) REFERENCES Profiles (profile_id));

select *from profiles
ALTER TABLE profiles
DROP COLUMN profile_id;

UPDATE profiles 
SET profile_id = not null
WHERE profile_id IS NULL

use profiles
use tenant


insert into profiles(first_name,last_name,email,phone,city_hometown,created_at,gender,referral_code,marital_status,profile_id) values (
("anusha","pariti","anusha.pariti@gmail.com",8105987404,"Bangalore",16-04-2015,"F",7L5FZW,"Y",1),
("Ashish","Singh","ashish.singh@gmail.com",9876890463,"Bangalore",23-05-2015,"M",KF34MF,"Y",2),
("Bhaskar","maheshwari","bhaskar.mah@gmail.com",9801834992,"Bangalore",01-05-2015,"M",5TYSHGF,"N",3),
("Garima","yadav","garima0191@gmail.com",81059237004,"Bangalore",20-10-2015,"F",5G5FQW,"N",4),
("Tanvi","mann","tanvi.mann1907@gmail.com",9178352769,"Bangalore",16-02-2015,"F",JSH48B,"N",5),
("Harish","sahai","harish294all@gmail.com",9876548763,"Bangalore",11-11-2015,"M",MKGI2W,"Y",6),
("Kamal","gera","kamal0094@gmail.com",8105987404,"Bangalore",31-10-2015,"M",MK34ER,"N",7),
("Tushar","kapoor","tushar.kapoor21@gmail.com",8926537154,"Pune",12-12-2015,"M",KLF12E,"N",8),
("Shivshankar","das","sankar.shiva730@gmail.com",9801834992,"Pune",06-10-2015,"M",3RE5TY,"Y",9),
("Aditi","jain","aditi.jain@sproxil.com",9873123456,"Pune",11-06-2015,"F",5TPL4E,"N",10),
("Deepa","sudhakar","sudhakar.deepa@gmail.com",7896785432,"Pune",15-09-2015,"F",4RTYUIO,"Y",11),
("Umang","parejiya","uparejiya@gmail.com",7896543674,"Pune",18-07-2015,"M",6TY4WE,"N",12),
("Mitali","gupta","mitali.gupta80@gmail.com",8796751238,"Pune",24-03-2015,"F",5RTYU3,"Y",13),
("Manisha","Yadav","maniyadav88@gmail.com",9867845182,"Pune",27-01-2015,"F",LKGHY6,"N",14),
("Shivani","godha","shivani_go@nid.edu",9878673428,"Pune",19-02-2015,"F",8NM4R,"Y",15),
("Rajan","pandey","raajanpandey@gmail.com",8987647811,"Pune",04-09-2015,"M",5TYUIO,"N",16),
("Roosena","manuel","roseenasimimanuel@gmail.com",9875623345,"Pune",13-04-2015,"F",6TYHU,"Y",17),
("Prabhjot","gill","prabhjotgill09@gmail.com",9800786688,"Pune",30-12-2015,"M",GHJK34,"N",18),
("Ankita","sharma","ankita.anku96@gmail.com",9988789656,"Pune",17-08-2015,"F",TH67TY,"Y",19),
("Karan","Singh","karan.singh@gmail.com",8976665768,"Pune",15-09-2015,"M",LRF34F,"N",20));



INSERT INTO Profiles (first_name, last_name, email, phone, city_hometown, created_at, gender, referral_code, marital_status, profile_id) 
VALUES 
("anusha", "pariti", "anusha.pariti@gmail.com", 8105987404, "Bangalore", '2015-04-16', "F", "7L5FZW", "Y", 1),
("Ashish", "Singh", "ashish.singh@gmail.com", 9876890463, "Bangalore", '2015-05-23', "M", "KF34MF", "Y", 2),
("Bhaskar", "maheshwari", "bhaskar.mah@gmail.com", 9801834992, "Bangalore", '2015-05-01', "M", "5TYSHGF", "N", 3),
("Garima", "yadav", "garima0191@gmail.com", 81059237004, "Bangalore", '2015-10-20', "F", "5G5FQW", "N", 4),
("Tanvi", "mann", "tanvi.mann1907@gmail.com", 9178352769, "Bangalore", '2015-02-16', "F", "JSH48B", "N", 5),
("Harish", "sahai", "harish294all@gmail.com", 9876548763, "Bangalore", '2015-11-11', "M", "MKGI2W", "Y", 6),
("Kamal", "gera", "kamal0094@gmail.com", 8105987404, "Bangalore", '2015-10-31', "M", "MK34ER", "N", 7),
("Tushar", "kapoor", "tushar.kapoor21@gmail.com", 8926537154, "Pune", '2015-12-12', "M", "KLF12E", "N", 8),
("Shivshankar", "das", "sankar.shiva730@gmail.com", 9801834992, "Pune", '2015-10-06', "M", "3RE5TY", "Y", 9),
("Aditi", "jain", "aditi.jain@sproxil.com", 9873123456, "Pune", '2015-06-11', "F", "5TPL4E", "N", 10),
("Deepa", "sudhakar", "sudhakar.deepa@gmail.com", 7896785432, "Pune", '2015-09-15', "F", "4RTYUIO", "Y", 11),
("Umang", "parejiya", "uparejiya@gmail.com", 7896543674, "Pune", '2015-07-18', "M", "6TY4WE", "N", 12),
("Mitali", "gupta", "mitali.gupta80@gmail.com", 8796751238, "Pune", '2015-03-24', "F", "5RTYU3", "Y", 13),
("Manisha", "Yadav", "maniyadav88@gmail.com", 9867845182, "Pune", '2015-01-27', "F", "LKGHY6", "N", 14),
("Shivani", "godha", "shivani_go@nid.edu", 9878673428, "Pune", '2015-02-19', "F", "8NM4R", "Y", 15),
("Rajan", "pandey", "raajanpandey@gmail.com", 8987647811, "Pune", '2015-09-04', "M", "5TYUIO", "N", 16),
("Roosena", "manuel", "roseenasimimanuel@gmail.com", 9875623345, "Pune", '2015-04-13', "F", "6TYHU", "Y", 17),
("Prabhjot", "gill", "prabhjotgill09@gmail.com", 9800786688, "Pune", '2015-12-30', "M", "GHJK34", "N", 18),
("Ankita", "sharma", "ankita.anku96@gmail.com", 9988789656, "Pune", '2015-08-17', "F", "TH67TY", "Y", 19),
("Karan", "Singh", "karan.singh@gmail.com", 8976665768, "Pune", '2015-09-15', "M", "LRF34F", "N", 20);

use tenant
INSERT INTO Houses (house_type, bhk_details, bed_count, furnishing_type, Beds_vacant, house_id)
VALUES 
("Apartment", "3BHK", 5, "unfurnished", 2, 1),
("Apartment", "3BHK", 3, "unfurnished", 1, 2),
("Apartment", "3BHK", 6, "fully-furnished", 4, 3),
("Apartment", "2BHK", 2, "fully-furnished", 0, 4),
("Independent", "4BHK", 4, "fully-furnished", 2, 5),
("Apartment", "3BHK", 3, "semi furnished", 1, 6),
("Apartment", "3BHK", 3, "semi furnished", 0, 7),
("Apartment", "2BHK", 4, "fully-furnished", 1, 8),
("Independent", "1BHK", 2, "unfurnished", 0, 9),
("Independent", "3BHK", 3, "fully-furnished", 1, 10),
("Apartment", "1BHK", 1, "unfurnished", 0, 11),
("Independent", "1BHK", 2, "unfurnished", 1, 12),
("Independent", "2BHK", 4, "unfurnished", 2, 13),
("Apartment", "3BHK", 3, "fully-furnished", 0, 14),
("Independent", "1BHK", 2, "unfurnished", 1, 15),
("Apartment", "3BHK", 3, "fully-furnished", 0, 16),
("Independent", "3BHK", 3, "fully-furnished", 1, 17),
("Independent", "2BHK", 2, "fully-furnished", 1, 18),
("Independent", "3BHK", 3, "fully-furnished", 1, 19),
("Independent", "1BHK", 2, "unfurnished", 2, 20);




INSERT INTO Addresses (name, description, city, pincode, house_id)
VALUES 
('Zaanz apartment', 'Sterling BrookSide, Opp. Kundalahalli Colony, ITPL Main Rd', 'Bangalore', 560037, 1),
('Stag Saptgiri', 'No.44, Ground floor, 20th cross, Sector 2 HSR Layout, Bangalore.', 'Bangalore', 560102, 2),
('Sri Sai Enclave', 'No.44, First floor, 20th cross, Sector 2 HSR Layout.', 'Bangalore', 560102, 3),
('Orchids Building', 'D-208, Balaji Pristine Whitefield Main Road', 'Bangalore', 560066, 4),
('Fella Homes', '#11, Annaiya Reddy Rd, Narayana Reddy Layout, Phase 2, Electronic City', 'Bangalore', 560100, 5),
('Juniper Apartments', '#595/1, 1st Floor, 1st A main, Domlur Layout', 'Bangalore', 560038, 6),
('UDB Building', 'Flat No: T1 Deccan Field Apartment Kunadanhalli main road', 'Bangalore', 560037, 7),
('Apoorva Society', 'Flat No-202, Apoorva Apartment No-296 Vyalikaval House Building Cooperative Society Ltd Nagavara', 'Delhi', 561202, 8),
('Stag Saptgiri', 'Flat No-202, Stag Saptgiri No-26 phase2 Cooperative Society', 'Delhi', 560045, 9),
('VaK Residency', '302, #473 VAK Residency, B-Block, AECS Layout Kundalahalli', 'Delhi', 456738, 10),
('Sunshine Hills', 'Flat no 3, water ville apartment R.galli', 'Delhi', 100234, 11),
('Sri Sai Apartment', '2nd House, No-80/289, Sri Hari Darshan Nilaya, Ground Floor, Bellandur', 'Delhi', 560107, 12),
('Barvika Residency', 'B105, 1st floor, B block, Barvika Residency', 'Delhi', 5610023, 13),
('Nestaway Building', '#157, 4th Cross, 1st Main Road, Lower Palace Orchard', 'Delhi', 546783, 14),
('Windsor Plaza', '#301, Windsor Plaza, ITPL', 'Pune', 560025, 15),
('Indira Society', 'No. 502, Indira Meadows, Arunodaya Colony', 'Pune', 302017, 16),
('Sri Krishna Society', 'Flat No-211 Sri Krishna Sai Enclave, Hoodi village, beside Vivekananda Ashram, Mahadevapura post', 'Pune', 560048, 17),
('Uniworld', 'D1-1201, Uniworld Garden 2', 'Pune', 543678, 18),
('Vinayaka Residency', '49, House 1 lathangi 2nd main vinayaka housing layout, RMV 2nd stage bhoopasandra', 'Pune', 560094, 19),
('Sun City Apartments', 'Majeera Diamond Towers, Malad-West', 'Pune', 5600263, 20);


INSERT INTO Employment_details (profile_id, latest_employer, official_mail_id, yrs_experience, Occupational_category)
VALUES
    (1, 'Sabre', 'mehdi.hasan@sabre.com', 1, 'Working'),
    (2, 'Hindustan Unilever', 'rags.ramgas@gmail.com', 2, 'Working'),
    (3, 'Technicolor', 'jigna.thacker@technicolor.com', 1, 'Working'),
    (4, NULL, NULL, NULL, 'Student'),
    (5, 'GE Healthcare', 'ruchita.save@ge.com', 3, 'Working'),
    (6, 'Aditya Birla', 'shubhi.bajpai@adityabirla.com', 3, 'Working'),
    (7, NULL, NULL, NULL, 'Student'),
    (8, NULL, NULL, NULL, 'Student'),
    (9, NULL, NULL, NULL, 'Student'),
    (10, 'Huawei Technologies', 'gunjan19wadhwa@gmail.com', 4, 'Working'),
    (11, NULL, NULL, NULL, 'Student'),
    (12, 'Centurylink India', 'PreetInder.Sodhi@centurylink.com', 2, 'Working'),
    (13, 'SAP Labs India', 'udit.singh@sap.com', 2, 'Working'),
    (14, 'NestAway', 'deepak@nestaway.com', 1, 'Working'),
    (15, NULL, NULL, NULL, 'Student'),
    (16, NULL, NULL, NULL, 'Student'),
    (17, 'Microsoft', 't-akmeh@microsoft.com', 2, 'Working'),
    (18, 'Cognizant', 'bhavranjan.pandey@cognizant.com', 2, 'Working'),
    (19, NULL, NULL, NULL, 'Student'),
    (20, 'Tiny Mogul Games', 'sanchit@hike.in', 3, 'Working');
    
    INSERT INTO Referrals (referrer_id, referrer_bonus_amount, referral_valid, valid_from, valid_till)
VALUES
    (2, 2500, 1, '2015-07-05', '2015-09-05'),
    (3, 2500, 1, '2015-07-05', '2015-09-05'),
    (5, 1000, 0, '2015-12-13', '2016-02-13'),
    (6, 2500, 0, '2016-04-25', '2016-06-24'),
    (10, 1000, 1, '2015-07-01', '2015-09-01'),
    (12, 2500, 1, '2015-05-12', '2015-07-12'),
    (13, 2500, 0, '2015-08-05', '2015-10-05'),
    (20, 1000, 1, '2016-02-05', '2016-04-05'),
    (2, 2500, 0, '2015-08-12', '2015-09-12'),
    (5, 1000, 1, '2016-02-18', '2016-04-18'),
    (20, 1500, 1, '2016-06-19', '2016-08-19'),
    (9, 2500, 0, '2015-11-15', '2016-01-15'),
    (13, 1000, 1, '2016-02-01', '2016-04-01'),
    (5, 1000, 1, '2016-04-25', '2016-06-24');
    
    
    INSERT INTO Tenancy_histories (profile_id, house_id, move_in_date, move_out_date, rent, Bed_type, move_out_reason)
VALUES
    (1, 5, '2015-02-12', '2016-04-30', 7500, 'bed', 'MOVE_OUT'),
    (2, 2, '2015-06-05', NULL, 11000, 'room', NULL),
    (3, 4, '2015-10-28', '2016-11-28', 12000, 'room', 'RENT_CHANGE'),
    (4, 1, '2015-04-26', NULL, 8000, 'bed', NULL),
    (5, 3, '2015-05-15', '2015-12-27', 9000, 'bed', 'MOVE_OUT'),
    (6, 8, '2015-12-25', NULL, 10200, 'room', NULL),
    (7, 6, '2015-11-20', NULL, 6500, 'bed', NULL),
    (8, 7, '2015-11-10', '2016-12-31', 7200, 'bed', 'MOVE_OUT'),
    (9, 9, '2015-10-15', NULL, 7500, 'bed', NULL),
    (10, 10, '2015-06-20', NULL, 7500, 'bed', NULL),
    (11, 19, '2015-08-29', '2016-06-14', 8000, 'bed', 'INTERNAL_TRANSFER'),
    (12, 15, '2015-02-24', NULL, 11000, 'room', NULL),
    (13, 12, '2015-02-25', NULL, 12000, 'room', NULL),
    (14, 18, '2016-01-07', '2016-12-30', 13500, 'room', 'MOVE_OUT'),
    (15, 13, '2015-04-07', NULL, 6500, 'bed', NULL),
    (16, 17, '2015-04-23', NULL, 6500, 'bed', NULL),
    (17, 14, '2015-02-10', NULL, 10500, 'room', NULL),
    (18, 16, '2015-10-16', '2016-09-04', 8000, 'bed', 'MOVE_OUT'),
    (19, 20, '2015-09-26', NULL, 7500, 'bed', NULL),
    (20, 11, '2015-09-30', NULL, 9500, 'bed', NULL);



ALTER TABLE tenant.addresses 
ADD CONSTRAINT house_id
  FOREIGN KEY (house_id)  REFERENCES .houses (house_id):
  
  
  
  ON DELETE NO ACTION
  ON UPDATE NO ACTION;

use tenant

describe addresses

SELECT 
    profile_id,
    CONCAT(first_name," ",last_name) AS full_name ,
    phone
FROM 
    Profiles
WHERE 
    DATEDIFF(move_in_date, move_out_date) = (
        SELECT 
            MAX(DATEDIFF(move_in_date, move_out_date))
        FROM 
            Tenancy_histories;
    
    /*select first_name+first_name as full_name from profiles
SELECT 
    CONCAT(first_name," ",last_name) AS full_name 
FROM 
    profiles;*/
    
    
 /*Write a query to get Profile ID, Full Name and Contact Number of the tenant who has stayed.
with us for the longest time period in the past*/
    

SELECT
    p.profile_id,
    CONCAT(p.first_name, ' ', p.last_name) AS full_name,
    p.phone AS contact_number,
    DATEDIFF(MAX(th.move_out_date), MIN(th.move_in_date)) AS duration_of_stay
FROM
    Profiles p
JOIN
    Tenancy_histories th ON p.profile_id = th.profile_id
GROUP BY
    p.profile_id
HAVING
    duration_of_stay >0
ORDER BY
    duration_of_stay desc;
    
    use tenant
    select * from profiles
    
    /*ite a query to get the Full name, email id, phone of tenants who are married and paying.
rent > 9000 using subqueries*/

SELECT 
    CONCAT(p.first_name, ' ', p.last_name) AS full_name,
    p.email AS email_address,
    p.phone AS contact_number
FROM 
    profiles p
WHERE 
    p.marital_status = 'y'
    AND p.profile_id IN (
        SELECT th.profile_id
        FROM Tenancy_histories th
        WHERE th.rent > 9000
    );



SELECT 
    CONCAT(p.first_name, ' ', p.last_name) AS full_name,
    p.email AS email_address,
    p.phone AS contact_number,
    th.rent
    FROM
    Profiles p
JOIN
     Tenancy_histories th ON p.profile_id = th.profile_id
WHERE 
    th.rent > 9000 AND p.marital_status = 'y';

/*Write a query to display profile id, full name, phone, email id, city, house id, move_in_date , move_out date, rent, total number of referrals made,
 latest employer and the occupational category of all the tenants living in Bangalore or Pune in the time period of jan 2015 to jan 2016 sorted by their rent in descending order*/
select *from Referrals
SELECT 
	profile_id
    CONCAT(p.first_name, ' ', p.last_name) AS full_name,
    p.email AS email_address,
    p.phone AS contact_number,
    city(hometown)
    house_id
    move_in_date
    move_out_date
    th.rent
    latest_employer
    FROM
    Profiles p
JOIN
     Tenancy_histories th ON p.profile_id = th.profile_id
WHERE 
    th.rent > 9000 AND p.marital_status = 'y';



SELECT 
    p.profile_id,
    CONCAT(p.first_name, ' ', p.last_name) AS full_name,
    p.phone,
    p.email,
    p.city_hometown AS city,
    th.house_id,
    th.move_in_date,
    th.move_out_date,
    th.rent,
    COALESCE((SELECT COUNT(*) FROM Referrals WHERE referrer_id = p.profile_id), 0) AS total_referrals,
    ed.latest_employer,
    ed.Occupational_category
FROM 
    Profiles p
JOIN 
    Tenancy_histories th ON p.profile_id = th.profile_id
right join
    Employment_details ed ON p.profile_id = ed.profile_id
WHERE 
    p.city_hometown IN ('Bangalore', 'Pune')
    AND th.move_in_date BETWEEN '2015-01-01' AND '2016-01-31'
ORDER BY 
    th.rent DESC;
    
    


/*ite a sql snippet to find the full_name, email_id, phone number and referral code of all
the tenants who have referred more than once.
Also find the total bonus amount they should receive given that the bonus gets calculated only for valid referrals.

The WITH ROLLUP modifier adds an extra row at the end of the result set which shows the total rent generated across all cities. */

SELECT 
    CONCAT(p.first_name, ' ', p.last_name) AS full_name,
    p.email AS email_id,
    p.phone AS phone_number,
    p.referral_code,
    COUNT(r.ref_id) AS total_referrals,
    SUM(CASE WHEN r.referral_valid = 1 THEN r.referrer_bonus_amount ELSE 0 END) AS total_bonus_amount
FROM 
    Profiles p
JOIN 
    Referrals r ON p.profile_id = r.referrer_id
GROUP BY 
    p.profile_id
HAVING 
    COUNT(r.ref_id) > 1;
    /Write a query to find the rent generated from each city and also the total of all cities./
    
    SELECT
    city,
    SUM(rent) AS total_rent
FROM
    Tenancy_histories th
JOIN
    Houses h ON th.house_id = h.house_id
JOIN
    Addresses a ON h.house_id = a.house_id
GROUP BY
    city
WITH ROLLUP;


WITH CityRent AS (
    SELECT
        city,
        SUM(rent) AS total_rent
    FROM
        Tenancy_histories th
    JOIN
        Houses h ON th.house_id = h.house_id
    JOIN
        Addresses a ON h.house_id = a.house_id
    GROUP BY
        city
)
SELECT
    city,
    total_rent
FROM
    CityRent

UNION ALL

SELECT
    'Total' AS city,
    SUM(total_rent) AS total_rent
FROM
    CityRent;
/Create a view 'vw_tenant' find profile_id,rent,move_in_date,house_type,beds_vacant,description and city of tenants who shifted on/after 30th april 2015 and are living in houses having vacant beds and its address./


CREATE VIEW vw_tenant AS
SELECT 
    th.profile_id,
    th.rent,
    th.move_in_date,
    h.house_type,
    h.Beds_vacant,
    a.description,
    a.city
FROM 
    Tenancy_histories th
JOIN 
    Houses h ON th.house_id = h.house_id
JOIN 
    Addresses a ON h.house_id = a.house_id
WHERE 
    th.move_in_date >= '2015-04-30' AND
    h.Beds_vacant > 0;
    
    
    select *from vw_tenant
    
/*Write a code to extend the valid_till date for a month of tenants who have referred more
than one time*/
UPDATE Referrals
SET valid_till = DATE_ADD(valid_till, INTERVAL 1 MONTH)
WHERE referrer_id IN (
    SELECT referrer_id
    FROM Referrals
    GROUP BY referrer_id
    HAVING COUNT(referrer_id) > 1
);


/Write a query to get Profile ID, Full Name, Contact Number of the tenants along with a new column 'Customer Segment' wherein if the tenant pays rent greater than 10000, tenant falls in Grade A segment, if rent is between 7500 to 10000, tenant falls in Grade B else in Grade C/


SELECT 
    p.profile_id AS "Profile ID",
    CONCAT(p.first_name, ' ', p.last_name) AS "Full Name",
    p.phone AS "Contact Number",
    CASE 
        WHEN t.rent > 10000 THEN 'Grade A'
        WHEN t.rent BETWEEN 7500 AND 10000 THEN 'Grade B'
        ELSE 'Grade C'
    END AS "Customer Segment"
FROM 
    Profiles p
JOIN 
    Tenancy_histories t
ON 
    p.profile_id = t.profile_id;

/*Write a query to get Fullname, Contact, City and House Details of the tenants who have not
referred even once*/


    SELECT 
    CONCAT(p.first_name, ' ', p.last_name) AS Fullname,
    p.phone AS Contact,
    p.city_hometown AS City,
    h.house_type AS HouseType,
    h.bhk_details AS BHKDetails,
    a.name AS Address
FROM 
    Profiles p
JOIN 
    Tenancy_histories th ON p.profile_id = th.profile_id
JOIN 
    Houses h ON th.house_id = h.house_id
JOIN 
    Addresses a ON h.house_id = a.house_id
LEFT JOIN 
    Referrals r ON p.profile_id = r.referrer_id
WHERE 
    r.referrer_id IS NULL;
    
    
    
    SELECT h.*
FROM Houses h
INNER JOIN (
    SELECT house_id
    FROM Tenancy_histories
    GROUP BY house_id
    ORDER BY COUNT(*) DESC
    LIMIT 1
) th ON h.house_id = th.house_id;

/Write a query to get the house details of the house having highest occupancy/

SELECT house_id, COUNT(*) AS occupancy_count
FROM Tenancy_histories
GROUP BY house_id
ORDER BY occupancy_count DESC
LIMIT 1;
