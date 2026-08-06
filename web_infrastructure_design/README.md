Web infrastructure design
 Novice
 By: Sylvain Kalache
 Weight: 1
 Manual QA review must be done (request it when you are done with the project)
Description
Quiz
For this project, we expect you to look at these concepts:

Network basics
Server
Web Server
DNS
Load balancer
Monitoring

Resources
Read or watch:

Network basics concept page
Server concept page
Web server concept page
DNS concept page
Load balancer concept page
Monitoring concept page
What is a database
What’s the difference between a web server and an app server?
DNS record types
Single point of failure
How to avoid downtime when deploying new code
High availability cluster (active-active/active-passive)
What is HTTPS
What is a firewall
Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

General
You must be able to draw a diagram covering the web stack you built with the sysadmin/devops track projects
You must be able to explain what each component is doing
You must be able to explain system redundancy
Know all the mentioned acronyms: LAMP, SPOF, QPS
Requirements
General
A README.md file, at the root of the folder of the project, is mandatory
For each task, once you are done whiteboarding (on a whiteboard, piece of paper or software or your choice), take a picture/screenshot of your diagram
This project will be manually reviewed:
As each task is completed, the name of that task will turn green
Upload a screenshot, showing that you completed the required levels, to any image hosting service (I personally use imgur but feel free to use anything you want).
For the following tasks, insert the link from of your screenshot into the answer file
After pushing your answer file to GitHub, insert the GitHub file link into the URL box
You will also have to whiteboard each task in front of a mentor, staff or student - no computer or notes will be allowed during the whiteboarding session
Focus on what you are being asked:
Cover what the requirements mention, we will explore details in a later project
Keep in mind that you will have 30 minutes to perform the exercise, you will get points for what is asked in requirements
Similarly in a job interview, you should answer what the interviewer asked for, be careful about being too verbose - always ask the interviewer if going into details is necessary - speaking too much can play against you
In this project, again, avoid going in details if not asked
Tasks
0. Simple web stack
mandatory
A lot of websites are powered by simple web infrastructure, a lot of time it is composed of a single server with a LAMP stack.

On a whiteboard, design a one server web infrastructure that hosts the website that is reachable via www.foobar.com. Start your explanation by having a user wanting to access your website.

Requirements:

You must use:
1 domain name foobar.com configured with a www record that points to your server IP 8.8.8.8
1 server (containing the following)
1 web server (Nginx)
1 application server
1 application files (your code base)
1 database (MySQL)
You must be able to explain some specifics about this infrastructure:
What is a server
What is the role of the domain name
What type of DNS record www is in www.foobar.com
What is the role of the web server
What is the role of the application server
What is the role of the database
What is the server using to communicate with the computer of the user requesting the website
You must be able to explain what the issues are with this infrastructure:
SPOF
Downtime when maintenance needed (like deploying new code web server needs to be restarted)
Cannot scale if too much incoming traffic
Please, remember that everything must be written in English to further your technical ability in a variety of settings.

Repo:

GitHub repository: holbertonschool-system_engineering-devops
Directory: web_infrastructure_design
File: 0-simple_web_stack
0/20 pts
1. Distributed web infrastructure
mandatory
On a whiteboard, design a three server web infrastructure that hosts the website www.foobar.com.

Requirements:

You must add:
1 load-balancer (HAproxy)
2 servers (each containing the following)
1 web server (Nginx)
1 application server
1 set of application files (your code base)
1 database (MySQL)
You must be able to explain some specifics about this infrastructure:
For every additional element, why you are adding it
What distribution algorithm your load balancer is configured with and how it works
Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both
How a database Primary-Replica (Master-Slave) cluster works
What is the difference between the Primary node and the Replica node in regard to the application
You must be able to explain what the issues are with this infrastructure:
Where are SPOF
Security issues (no firewall, no HTTPS)
No monitoring
Please, remember that everything must be written in English to further your technical ability in a variety of settings.

Repo:

GitHub repository: holbertonschool-system_engineering-devops
Directory: web_infrastructure_design
File: 1-distributed_web_infrastructure
0/10 pts
2. Secured and monitored web infrastructure
mandatory
On a whiteboard, design a three server web infrastructure that hosts the website www.foobar.com, it must be secured, serve encrypted traffic, and be monitored.

Requirements:

You must add:
3 firewalls
1 SSL certificate to serve www.foobar.com over HTTPS
3 monitoring clients (data collector for Sumologic or other monitoring services)
You must be able to explain some specifics about this infrastructure:
For every additional element, why you are adding it
What are firewalls for
Why is the traffic served over HTTPS
What monitoring is used for
How the monitoring tool is collecting data
Explain what to do if you want to monitor your web server QPS
You must be able to explain what the issues are with this infrastructure:
Why terminating SSL at the load balancer level is an issue
Why having only one MySQL server capable of accepting writes is an issue
Why having servers with all the same components (database, web server and application server) might be a problem
Please, remember that everything must be written in English to further your technical ability in a variety of settings.

Repo:

GitHub repository: holbertonschool-system_engineering-devops
Directory: web_infrastructure_design
File: 2-secured_and_monitored_web_infrastructure
0/12 pts
3. Scale up
mandatory
Readme

Application server vs web server
Requirements:

You must add:
1 server
1 load-balancer (HAproxy) configured as cluster with the other one
Split components (web server, application server, database) with their own server
You must be able to explain some specifics about this infrastructure:
For every additional element, why you are adding it
Please, remember that everything must be written in English to further your technical ability in a variety of settings.

Repo:

GitHub repository: holbertonschool-system_engineering-devops
Directory: web_infrastructure_design
File: 3-scale_up

# add explain

0-simple_web_design

Addım-addım izah (imtahanda danışa biləcəyin)

İstifadəçi sorğusu: Browser www.foobar.com yazır.

DNS: www.foobar.com A record vasitəsilə IP 8.8.8.8-ə çevrilir.

Web server (Nginx): HTTP/HTTPS sorğusunu qəbul edir, statik faylları qaytarır və ya application server-ə yönləndirir.

Application server: Dinamik kodları icra edir və lazım gələrsə MySQL-dən məlumat alır.

Database (MySQL): Məlumatları saxlayır və application server-ə cavab verir.

Cavab browser-ə göndərilir: HTML, CSS, JS istifadəçinin kompüterində göstərilir.

 Problemlər / çatışmazlıqlar

SPOF: Tək server varsa, düşəndə sayt dayanır.

Downtime: Kod yeniləməsi və ya restart zamanı sayt müvəqqəti əlçatmaz olur.

Miqyaslanma problemi: Tək server çox trafik gəldikdə performansı qaldıra bilmir.


1-distributed_web_infrastructure

Addım-addım izah
a) Load balancer (HAproxy)

Rolu: İstifadəçi sorğularını 2 server arasında paylayır.

Paylama alqoritmləri:

Round Robin: Sorğuları növbə ilə hər serverə göndərir.

Least Connections: Daha az bağlı istifadəçisi olan serveri seçir.

Active-Active vs Active-Passive:

Active-Active: Hər iki server eyni anda sorğu qəbul edir.

Active-Passive: Bir server aktivdir, digər standby vəziyyətdədir, yalnız birinci düşəndə işləyir.

b) Serverlər

Hər bir serverdə:

Web server (Nginx): Statik faylları qaytarır, dinamik sorğuları application server-ə yönləndirir.

Application server: Kod bazasını icra edir, biznes məntiqini yerinə yetirir.

Application files: Saytın kodları.

Database:

Server 1 → Primary (yazma və oxuma)

Server 2 → Replica (yalnız oxuma)

Database replication: Primary-dən Replica-ya məlumatlar sinxronizasiya olunur.

c) Primary vs Replica

Primary: Yazma və oxuma əməliyyatlarını qəbul edir.

Replica: Sadəcə oxuma əməliyyatları üçün istifadə olunur, Primary-dən məlumat alır.

d) Əsas problemlər / risklər

SPOF (Single Point of Failure)

Load balancer düşərsə → bütün sayt əlçatmaz olur.

Təhlükəsizlik:

Əgər firewall və HTTPS yoxdursa → məlumatlar şifrəsiz ötürülür, icazəsiz giriş riski var.

Monitoring yoxdur:

Serverlərin vəziyyəti izlənmir → problem yarananda xəbərdar olma imkanı yoxdur.

2-secured_and_monitored_web_infrastructure

Addım-addım izah
a) Firewalls

3 firewall əlavə olunur:

İnternet → Load Balancer

Load Balancer → Serverlər

Serverlər → Monitoring / Backend

Rolu: Qeyri-icazəli trafiki bloklayır, təhlükəsizliyi artırır.

b) HTTPS (SSL sertifikatı)

Rolu: Trafik şifrələnir → istifadəçi məlumatları təhlükəsiz ötürülür.

Niyə lazımdır: Şifrlənmə olmadan məlumatlar ələ keçirilə bilər.

c) Monitoring

Monitoring clients: Hər serverdə agent quraşdırılır (Sumologic və ya digər).

Rolu: Serverlərin performansını, CPU, RAM, QPS, səhvləri və digər metrikləri toplayır.

QPS (Query Per Second) izləmək: Web server logları və ya Nginx statistikaları agent vasitəsilə toplanır.

d) Serverlər

Hər serverdə:

Web server (Nginx)

Application server

Kod bazası

MySQL: Server 1 → Primary (yazma və oxuma), Server 2 → Replica (yalnız oxuma)

Monitoring client

3️⃣ Problemlər / risklər

Terminating SSL at Load Balancer:

Load balancer SSL-i açır → trafikin serverə qədər şifrələnməsi bitir, daxili şəbəkədə məlumat açıq ötürülə bilər.

Tək MySQL yazma serveri:

Əgər Primary server düşərsə → yazma əməliyyatları dayanar.

Hər serverdə eyni komponentlər (DB + Web + App):

Server düşərsə → həm veb, həm app, həm də DB əlçatmaz olur.

Miqyaslama çətinləşir, SPOF riski qalır.


3-scale_up

Addım-addım izah
a) Yeni server əlavə olunur

Məqsəd: Hər komponenti ayrı serverə yerləşdirmək → SPOF və performans riskini azaltmaq.

b) Load Balancer Cluster (HAproxy)

2 load balancer Active-Active konfiqurasiyada → yükü bölüşdürür və SPOF-u azaldır.

Hər biri bütün serverlərə sorğu göndərə bilir.

c) Component separation

Hər komponent öz serverində:

Web server → statik fayllar və HTTP sorğularını application server-ə yönləndirir.

Application server → biznes məntiqini icra edir.

Database → Primary/Replica modeli ilə yazma və oxuma əməliyyatlarını ayırır.

d) Monitoring

Hər serverdə agentlər → performans, CPU/RAM, səhvlər və QPS izlənir.

3️⃣ Problemlər / diqqət etməli məqamlar

Hələ də Primary MySQL server SPOF riskini daşıyır.

SSL termination və firewall məsələlərini həll etmək tövsiyə olunur.

Daha çox server əlavə etməklə horizontal miqyaslama mümkündür.

# General short explain

0. Ümumi tələblər (General)

Hər layihə üçün README.md faylı olmalıdır və layihənin kök qovluğunda yerləşməlidir.

Hər tapşırığı whiteboard-da həll etdikdən sonra (kağız, whiteboard, proqram vs.) diagramın şəklini çəkməlisən.

1. Ümumi ideya

Domain: www.foobar.com

Load balancer (HAproxy): Trafiki 2 server arasında paylayır

2 server: Hər birində:

Nginx web server

Application server

Application files (kod bazası)

MySQL database (Primary / Replica)

Bu dizayn yükü paylamaq, SPOF-u azaltmaq və yüksək mövcudluğu təmin etmək üçün hazırlanıb.

2. Bu infrastruktur: təhlükəsiz (firewall + HTTPS), monitorlu (agentlər + Sumologic), yük balanslı.

Hələ də Primary MySQL və SSL termination məsələləri diqqət tələb edir.

Monitoring sayəsində performans, səhvlər və QPS izlənir.

3. Bu dizayn component separation + load balancer cluster + monitoring ilə performansı artırır və SPOF-u azaldır.

Hər komponent öz serverində → server düşdükdə digər komponentlər işləməyə davam edə bilər.

İnfrastruktur müasir, miqyaslana bilən veb infrastrukturuna çevrilir.

