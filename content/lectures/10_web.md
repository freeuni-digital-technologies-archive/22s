# 10. ვები, ნაწილი 2
ამ ლექციაში მოცემული ტერმინების განმარტებები ერთ-ერთი ყველაზე მნიშვნელოვანია მთლიანი საგნის და მომავალი ლექციების გაგებისთვის. მათი აღქმა ასევე არის ძალიან **ცირკულარული**. ვგულისხმობ იმას, რომ ტერმინები ერთი მეორეს განმარტავენ. მაგალითად, back end აპლიკაციას უკეთ გაიგებ თუ იცი რა არის სერვერი, თუმცა თავად სერვერის განმარტება back end აპლიკაციას მოიცავს. ამიტომ, მნიშვნელოვანია ლექციას ორჯერ მაინც გადახედო, რადგან მოგვიანებით მიღებული მაგალითები საწყისი ტერმინების გაგებაში ხელს შეგიწყობს. ასევე **არსებითად აუცილებელია** მაგალითების გაკეთება, რადგან მხოლოდ სიტყვიერი ახსნით მასალას ვერ გაიგებ.

## web აპლიკაციის კომპონენტები
### რა არის სერვერი
სერვერის ფუნქცია და განსაზღვრება საკმაოდ მრავალმხრივია და ბევრმა პროგრამისტმაც არ იცის ყველა მათგანი. მე სამს გამოვარჩევდი:

#### აპლიკაცია
back end, მონაცემთა ბაზა, მეილ სერვერი და ა.შ.

#### კომპიუტერი
რომელიც განკუთვნილია სერვერ პროგრამებისთვის. ჩვეულებრივი კომპიუტერისგან არსებითად არ განსხვავდება, გარდა იმისა, რომ როგორც წესი უფრო მძლავრია და gui (graphical user interface) ელემენტები არ აქვს.

#### ოპერატიული სისტემა 
ოპერატიული სისტემის ვერსია, განკუთვნილი სერვერ კომპიუტერისთვის. ამ ვერსიაში, მაგალითად, არ არის ფანჯრები და მაუსი, რადგან ამ კომპიუტერს ყოველთვის დისტანციურად ვუკავშირდებით. ასევე წინასწარ არის გამზადებული ის ხელსაწყოები და კონფიგურაციები, რაც კომპიუტერს ინტერნეტში ჩასართავად ჭირდება. ინტერნეტში ჩართვაში იგულისხმება არა ინტერნეტთან კავშირი გამავალი მოთხოვნებით და რესურსების **browsing**, არამედ შემომავალი მოთხოვნების მიღება, დამუშავება და რესურსების მიწოდება ბევრი სხვადასხვა კლიენტისთვის (ბრაუზერი, აპლიკაცია და ა.შ). 


#### front end აპლიკაცია
html/css/javascript, რომელიც მოდის ჩვენს ბრაუზერში (ან იწერება აპლიკაციაში). ამ ყველაფერსაც ვიღებთ სერვერიდან, თუმცა მიღებულ კოდს ბრაუზერი კითხულობს და ასრულებს. html კოდი შეიძლება იდოს სერვერზე ფაილის სახით, თუმცა შეიძლება გენერირდებოდეს სხვა პროგრამის მიერ. თანამედროვე web ხელსაწყოებით პროგრამისტები უფრო და უფრო ხშირად ირჩევენ, რომ სერვერიდან მინიმალური html გამოგზავნონ და გვერდის გენერირება მთლიანად მიღებულ javascript კოდზე იყოს დამოკიდებული. 

#### javascript-ის ლიმიტები
საიტის ყოველი ჩატვირთვა ყველა ფაილს ახლიდან კითხულობს, რაც ნიშნავს, რომ ყველა ცვლადი თუ dom მოდიფიკაციის შედეგად შექმნილი ელემენტი უბრუნდება საწყის (ფაილში მოცემულ) ვერსიას. ასევე, შეუძლებელია ერთ კომპიუტერზე გახსნილი საიტის მეხსიერება სხვა კომპიუტერმა წაიკითხოს, ამიტომ ყველა მოდიფიკაცია ლოკალურია. მონაცემების შესანახად და გასაზიარებლად აუცილებელია მათი გაგზავნა/მიღება სერვერ კომპიუტერზე.

#### back end აპლიკაცია
სერვერის აპლიკაცია, დაწერილი ნებისმიერ ენაში, რომელსაც უკავშირდება front end და მისგან იღებს/უგზავნის მონაცემებს. ერთ-ერთი ასეთი აპლიკაციის მაგალითი პითონში წინა კვირას განვიხილეთ. 


## მეტი http პროტოკოლზე
**ყველაფერი**, რაც ვებით შენს კომპიუტერამდე (ძირითადად ბრაუზერამდე) იგზავნება, არის **რესურსი**

- მედია ფაილები (სურათი, ვიდეო, დოკუმენტი) 
- გენერირებული საიტი (html)
- პროგრამა (ანუ ჯავასკრიპტის კოდი), რომელიც საიტს აგენერირებს
- მესიჯი/ინფორმაცია/მონაცემები

რესურსის მოთხოვნა და გაგზავნა თითქმის ყოველთვის http პროტოკოლით ხდება. **request** ანუ **მოთხოვნა** იგზავნება ყოველთვის სერვერთან, კლიენტის ან სხვა სერვერის მხრიდან, ხოლო სერვერიდან მოდის **პასუხად** რესურსი - **response**. ზოგჯერ შეიძლება მოთხოვნასაც ახლდეს რესურსი - მაგალითად, როდესაც ტვირთავ სურათს, ან ქმნი ახალ ინფორმაციას (აგზავნი მესიჯს, რეგისტრირდები საიტზე და ა.შ)

თითოეული რესურსი, ტრანსპორტის შრის ჩათვლით, მხოლოდ რიცხვების მიმდევრობაა. იმისთვის, რომ მათი **ენკოდირება** გასაგები იყოს მიმღებისთვის, რესურსს თან ახლავს ფაილის ტიპის ველი. network tab-ში შეგიძლია დაათვალიერო 

### uri/url
ქსელის შრეზე აუციელებელია უნიკალური იდენთიფიკატორი **IP**, http-ის შემთხვევაში ამ იდენთიფიკატორს ემატება სხვა კომპონენტები

#### domain name
example.com ან IP მისამართი

#### პორტი
ერთ სერვერზე შეიძლება (და ხშირად ასე ხდება) რამდენიმე http აპლიკაცია იყოს. იმისთვის, რომ კომპიუტერმა იცოდეს, რომელს მიაწოდოს შემოსული მოთხოვნა (request), გამოიყენება პორტის იდენთიფიკატორები. ერთ პორტზე მხოლოდ ერთი აპლიკაციაა გაშვებული.

ასევე, სხვადასხვა პორტი გამოიყენება სხვადასხვა ტიპის აპლიკაციებისთვის. მაგალითად, backend აპლიკაციისთვის არის ხოლმე პორტი 3000 ან 5000, სხვა არის მონაცემთა ბაზისთვის და ა.შ. ასეთი კონვენციებით ყოველთვის იცი რომელი პორტი მიანიჭო შენს აპლიკაციას.

საიტის მისამართის ჩაწერისას პორტს არ ვწერთ ხოლმე, იმის გამო, რომ არსებობს უნივერსალურად შეთანხმებული პორტი: 80. ამ პორტზე განთავსებულია ხოლმე html ფაილები (ან მათი მაგენერირებელი front end აპლიკაცია).

#### path/endpoint
Desktop/freeuni/leqcia.pdf

ჯამში, url იდენთიფიკატორი ასე გამოიყურება:

www.example.com:1234/posts/2

### json
იშიფრება, როგორც **j**ava**s**cript **o**bject **n**otation. ჯავასკრიპტ ობიექტის **ტექსტში ენკოდირების** ფორმატი. რისთვის არის საჭირო? ინტერნეტით ცვლადს ვერ გავაგზავნით, რადგან მხოლოდ რიცხვების/ტექსტის გაგზავნა შეგვიძლია. json-ის მეშვეობით შეგვიძლია მონაცემები (მაგალითად, პოსტები, კომენტარები, ანგარიშის ინფორმაცია) ინტერნეტის მეშვეობით ტექსტურად გავაგზავნოთ, მიმღები კი გააკეთებს ობიექტის **რეკონსტრუქტირებას** და შეძლებს მის გამოყენებას ჯავასკრიპტის კოდში. 

გახსენი ეს მისამართი: <https://jsonplaceholder.typicode.com/todos/>. გვერდზე ჩატვირთული მონაცემები შეგვიძლია ჯავასკრიპტიდან მოვითხოვოთ, წავიკითხოთ და შემდეგ გვერდზე გამოვაჩინოთ (ამას სემინარში იხილავ). თუ რომელიმე კონკრეტული თასქი გვაინტერესებს, შეგვიძლია path-ში id-იც ჩავწეროთ <https://jsonplaceholder.typicode.com/todos/1>.

### API
ბუნებრივია, front end აპლიკაციამ უნდა იცოდეს რომელ url-ზე რა ტიპის მონაცემი მოუვა back end-სგან, რა ატრიბუტები ექნება ჯავასკრიპტის ობიექტს და ა.შ. ამ სტრუქტურას api ეწოდება. მაგალითად, ზემოთა მაგალითში /todos/ endpoint-ზე მოგვდის task ობიექტების სია, ხოლო /todos/:n endpoint-ზე მოდის n id-ის მქონე თასქი. API ეწოდება როგორც endpoint-ების სტრუქტურას, არამედ back end აპლიკაციის იმ შრეს, რომელიც API პასუხისმგებლობას ასრულებს (მომავალ კვირებში უფრო დეტალურად ვისაუბრებთ ამაზე).


## Developer tools: network
ერთი საიტის ჩასატვირთად საჭირო უამრავი მოთხოვნის სადემონსტრაციოდ შედი google.com-ზე და გახსენი development tools (inspect element). კონსოლის მარჯვნივ არის network tab. აქ გადასვლის შემდეგ ჩატვირთე გვერდი თავიდან (reload) და დაათვალიერე სხვადასხვა რესურსები, რომელიც ბრაუზერმა მოითხოვა სერვერებისგან. 

ახლა ასეთი ექსპერიმენტი ჩაატარე: გაფილტრე რესურსები "fetch/xhr" ღილაკით და საძიებო ველში დაიწყე რაიმე სიტყვის ჩაწერა (მაგალითად 'weather'). პირველი სიმბოლოს დაწერის შემდეგ ახალი რესურსი გამოჩნდება /complete endpoint-დან. მასზე დაჭერისას შეგიძლია ნახო search suggestion-ები, რომელიც ახლა საძიებო ველის ქვეშ ჩანს. 
