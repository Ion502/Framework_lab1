# Framework_lab1

## Sarcina 1
1. Introducerea datelor incorecte
    1. Metoda POST folosita pentru a trimite cererea HTTP
    2. Anteturile trimise in cerere sunt: Accept, Accept-Encoding, Accept-Language, Connection, Content-Length, Content-Type, Host, Origin, Referer, Sec-GPC si User-Agent
    3. Parametri trimisi in cerere nu exista trimisi prin URL direct, dar avem Payload din corpul cererii care sunt: username=student&password=password
    4. Codul returnat in cerere a fost 401: Unauthorized (neautorizat)
    5. Anteturile folosite in raspuns sunt: Accept-Encoding, Referer, Origin, Accept-Language, Sec-GPC, Content-Type, User-Agent, Accept, Content-Lenght, Connection, Host
    6. Introducerea corecta a datelor
        1. Metoda POST folosita pentru a trimite cererea HTTP
        2. Anteturile trimise in cerere sunt: Accept, Accept-Encoding, Accept-Language, Connection, Content-Length, Content-Type, Host, Origin, Referer, Sec-GPC si User-Agent
        3. Parametri trimisi in cerere nu exista trimisi prin URL direct, dar avem Payload din corpul cererii care sunt: username=admin&password=password
        4. Codul returnat este 200 OK
        5. Anteturile folosite in raspuns sunt: Accept-Encoding, Referer, Origin, Accept-Language, Sec-GPC, Content-Type, User-Agent, Accept, Content-Lenght, Connection, Host

2. 
    1. curl -H "User-Agent: Tican Ion" http://sandbox.com
    2. 
    POST /cars HTTP/1.1  
    Host: sandbox.com  
    Content-Type: application/x-www-form-urlencoded  
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/126.0.6478.127 Safari/537.36  
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7  
    Accept-Language: en-US  
    Accept-Encoding: gzip, deflate, br  
        make=Toyota&model=Corolla&year=2020  
    3. 
    PUT /cars/1 HTTP/1.1  
    Host: sandbox.com  
    User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/126.0.6478.127 Safari/537.36  
    Accept-Language: en-US  
    Content-Type: application/json  
    Accept-Encoding: gzip, deflate, br  
    Connection: keep-alive  
    
        "make": "Toyota",

        "model": "Corolla",

        "year": 2021  
    4. 
        * 200: Avem raspunul OK, serverul a procesat cererea cu succes, dar nu avem o resursa noua, Serverul posibil sa fi acualizat o resursa deja existenta, deoarece la POST este asteptat raspusnul 201, dar pot aparea cazuri si de returnare la 200  
        * 201: resursa a fost creata cu succes cu datele transmise de catre noi  
        * 400: Solicitarea nu poate fi procesata din cauza unei erori de sintaxe in momentul transmiterii  
        * 401: Este necesare autentificarea pentru a crea acele date  
        * 403: Utilizatorul desi este autentificat nu are dreptul la acces la crearea/actualizarea datelor  
        * 404: Resursa pe care incercam sa o accesam nu exista sau URL este diferit/schimbat  
        * 500: A aparut pe server care ne impiedica procesarea cererii pana la final  
    5. 
    DELETE /cars/1 HTTP/1.1  
    Host: sandbox.com  
    User-Agent: Numele Prenumele  
    Content-Type: application/json  

    Folosim DELETE pentru ca astfel vom sterge datele care se afla pentru masinile care au id = 1  

3. La aceasta sarcina voi realiza 2 metode: Cea prin care trimit numele meu si voi indeplini sarcinile conform Moodle, folosind instrumentul curl, si a 2-a prin care voi folosi Burpsuite si curl pentru a nu folosi Numele meu, putand primi un id si tokenii necesari pentru completarea questului
    1. Metoda curl
        * curl -X POST http://sandbox.usm.md/quest -H "User-Agent: Tican Ion" id = 166278 token = HQgONQZFCwod
        * curl -X POST http://sandbox.usm.md/quest/login -H "Authorization: HQgONQZFCwod" id = 351304 token = KhQfOEddbF1dRA== ; id = 970853
        * curl -X PUT http://sandbox.usm.md/quest/age -H "Authorization: Bearer KhQfOEddbF1dRA==" -d "age=25"; id = KhQfOEddbF1dRB9CU1RSRldcQF95
        * curl -X GET "http://sandbox.usm.md/quest/secret?token=KhQfOEddbF1dRB9CU1RSRldcQF95" secret ==  CjkdGkpxTV1iUVlGUA==
    2. Metoda Burpsuite 
        Cuvantul secret extras cu Burpsuite: JCMVHwklAkp5T0RUTXYAIgsZEjpDKxhBRURLEVJsOB8Lf1debBlCQEwBKDwfGgAeBgcHCABbUBJeYlxARWEoLRgsOFhFTQAnClYiLAAOI0hUNw1TBiEKWVR7VUt8T0JAUhlHfV1BRRoCAy0THVtQEl5iXEBIe1M=
        * ![image1](C:\Users\royal\Desktop\Framework_lab1\3.2.1 ss.png)
        * ![image1](C:\Users\royal\Desktop\Framework_lab1\3.2.2 ss.png)
        * ![image1](C:\Users\royal\Desktop\Framework_lab1\3.2.3 ss.png)
        * ![image1](C:\Users\royal\Desktop\Framework_lab1\3.2.4 ss.png)
        * ![image1](C:\Users\royal\Desktop\Framework_lab1\3.2.5 ss.png)

