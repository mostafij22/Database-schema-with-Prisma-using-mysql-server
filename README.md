
What is Prisma?
=============== 
Prisma hosse akta ORM. ORM means Database manage korar akta system. Ja javaScript Eco-system e hoi.
Object–relational mapping (ORM, O/RM, and O/R mapping tool) in computer science is a programming
technique for converting data between a relational database.

Database manage korar akta nijesso system hosse ORM. jemon laravel er modhe Query builder ase,
.aspnet er jonno NTT framwork ase, thik temoni NextJs framwork e database manage korar jonno 
Prisma  akta ORM. Prisma diye jekono database manage kora jai, onno ORM diye ta jai na, fixed 
thake, Mongodb manage korar ORM hosse mongoose.

Prisma diye aki sate database operation(CRUD) chalano jai and database design kora jai.
Prisma ORM javaScript er jekono eco-system er satei kaj kore.

Prisma ORM er 3ta part ase 1.Migrate= database design 2.client=query operation 
    3.Studio= database view

Prisma ORM er feature hosse 2ta 
 1. Migrate= database design kora jai, database table toiri kora jai, akta table er sate onno 
    table er relation kora jai. 
 2. client = Query kora(database operation-CRUD) 

package
-------
0. VS code Extention-prisma install for easily coding
1. npm install prisma --save-dev
2. npx prisma init --datasource-provider mysql
3. XAMPP- install for mysql database server 

http://localhost/phpmyadmin/ = for open GUI
database create in mysql server naming - mydb
default database er name hosse = root

.env file
=========
//DATABASE_URL="mysql://johndoe:randompassword@localhost:3306/ostad"
default database hosse -root and password set na thakle just , : 
DATABASE_URL="mysql://root:@localhost:3306/ostad"

mysql server e akta database = ostad create kore connection kora holo. akhon 


schema.prisma
==============
schema.prisma file e => model/table/entity design korbo code likhe . a e file e table niye
kaj korbo/ database er schema likhbo , ja automatically mysql server e database e table create
korbe.


schema= database table er je shape thake setai schema
        database table er je colum thake tar onek gulu data type thake. exam: int, varchar/string,text/string. 

        model hosse table , kono nam diye model likha means table create kora database e.

        model User{
            id Int @id @default(autoincrement())
            name String
            email String @unique
        }

3. npx prisma migrate dev 





Relational database er protita table a akta kore primary key thake. 





protita Relational database e akta  primary key thake. 
primary key k sadharonto id name deye thake , but jekono nam deya jai

database table/model e je onnek gulu column kora hoi, sei column er data gulu 
kemon hobe tar onek gulu type thake. exam: Int, String, varchar, text, date etc.
varchar and text ak dhoroner String data.
bivinno dhoroner data , database table e thakte pare. 

|| = one 

0 = not

--
--  = many  
--

primary key create
------------------
id Int @id @default(autoincrement())

Prisma te primary key declare kori, @id 
sql/mysql e primary key auto increment hoi, @default(autoincrement())
@db.Unsigned = id value kokhono nagetive hobe na, always positive value hobe

Prisma te data type String deya means database e varchar hobe

createdAT = jokhon database table e insert hobe , aumatically created date add hoye jabe.
updatedAt = jokhon database table e update hobe , aumatically updated date add hoye jabe. 
 
enum data
=========
enum data type means = dropdown , fixed kisu value , ae fixed value bahire kono data insert hobe na.


one to many Relational sese = [] sign dite hoi.  
 kono model er sate [] likhle one to many bujai, aki catagory onek gulu product er vitor thakte 
 pare.

one to one Relational sese = ? sign dite hoi.

primary and foreign key
=====================
products  products   @relation(fields: [product_id], references: [id], onDelete: Restrict, 
onUpdate: Cascade)

fields: [product_id] = primary key
references: [id] = foreign key


