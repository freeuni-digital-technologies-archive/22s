
# 04. ინფორმაციის ენკოდირება ბაიტებში
### 
ამ ლექციის საკვანძო ტერმინები
- ენკოდირება/დეკოდირება
- პიქსელი, რეზოლუცია
- ფაილის ფორმატი
- კომპრესირება/დეკომპრესირება

<!-- n -->
ჩვენ ვისწავლეთ, რომ კომპიუტერში ინფორმაცია ბიტებში ინახება და მუშავდება, მაგრამ ჯერ შეუძლებელია იმის აღქმა, თუ როგორ გადაითარგმნება სხვადასხვა სახის ინფორმაცია (სურათი, ვიდეო, აუდიო, ტექსტი) ბიტებში.

ამ ლექციაში შევეცდებით კარგად გავიგოთ, რას ნიშნავს, როდესაც ვამბობთ რომ კომპიუტერში ყველაფერი არის რიცხვი. როგორ შეიძლება, რომ მხოლოდ და მხოლოდ ციფრების მიმდევრობით მუშაობდეს ყველა ციფრული პროგრამა, რომელსაც ვიყენებთ?

## სურათები
დავიწყოთ ყველაზე პრიმიტიული მაგალითით.


### პიქსელი

![](https://futureeverythingmsf.files.wordpress.com/2015/02/image.png)

<!-- ნ -->
თითო უჯრას **პიქსელი** ეწოდება. როგორ გავაუმჯობესოთ სურათის ხარისხი?


### პიქსელების რაოდენობა - რეზოლუცია
![](https://kronos-images.schoolmouv.fr/2-fnx-snt-c15-img01.png)
### ბაიტების რაოდენობა
 თუ თითო პიქსელი ერთი ბაიტი იქნება, მაშინ 255 ფერს გამოვსახავთ (ნაცრისფერის ტონები) 
 
![](https://seis.bristol.ac.uk/~ggjlb/teaching/ccrs_tutorial/tutorial/graphics/content/pixel.gif)

### ფერები
ციფრულ ფორმატში ფერები გამოისახება **rgb** მნიშვნელობის გამოყენებით. თითო საბაზისო ფერისთვის (წითელი, მწვანე, ლურჯი) გამოყოფილია ერთი ბაიტი - ანუ ერთი პიქსელისთვის სამ ბაიტს ვინახავთ.

![](https://i.pinimg.com/736x/59/57/57/59575781b130706a7d2ce27ebd0e019f.jpg)

<!-- n -->
სურათის პიქსელებად შენახვა ზუსტად შეესაბამება იმ პრინციპს, როგორც ახლა ეს გამოსახულება შენს ეკრანზეა შექმნილი. 
ყველა ეკრანს აქვს **რეზოლუცია**, მაგალითად, Full HD - 1920x1080. ეს ნიშნავს, რომ ეკრანზე არის 2,073,600 კვადრატი, რომელშიც თავის მხრივ 3-3 მართკუთხედია - ლურჯის, წითელის და მწვანესთვის. rgb მნიშვნელობა სწორედ ასე გამოისახება.

### კომპრესირება
- ასეთი ენკოდირებით ერთი fhd სურათის ზომა 6,220,800 ბაიტი ანუ 6 MB (მეგაბაიტი) იქნება.
- ზომის შემცირება რაც შეიძლება "ეფექტურად" უნდა მოხდეს

<!-- n -->
შეიძლება ცალკე აღებულად არც ისე დიდი ზომაა, მაგრამ ზოგჯერ ამ ზომის შემცირება გვჭირდება (ჩვენ ან სხვას). წარმოიდგინეთ, რამდენი სურათი იპოსტება/იგზავნება სოციალურ მედიაში ყოველ წამს. ისიც გეცოდინებათ, რომ მესენჯერში გაგზავნისას სურათი "ხარისხს კარგავს". 
სურათის ზომის შემცირება ერთი შეხედვით მარტივი, მაგრამ არც ისე პრიმიტიული პრობლემაა. რა ლოგიკით გადავწყვიტოთ, რომელი პიქსელები ამოვაგდოთ? ჩვენ უბრალოდ ზომის (ანუ ბაიტების რაოდენობის) შემცირება ხომ არ გვინდა - გვსურს ეს ისე გავაკეთოთ, რომ მნიშვნელოვანი ინფორმაცია არ დაიკარგოს. ამ პროცესს კომპრესირება ეწოდება და სურათების შენახვის გარდა ბევრ სხვა ფაილშიც გამოიყენება.

#### მაგალითი

![](https://cdn.geckoandfly.com/wp-content/uploads/2016/12/lossy-compression-ratios.jpg)

<!-- ნ -->
კონკრეტული სიგანის (მაგალითად 2) კვადრატებზე "საშუალოს" აღება და ამ 4 (2x2) პიქსელის მაგივრად 1 მნიშვნელობის ჩაწერა

### სურათის შენახვის ფორმატები
- jpg
- png
- raw

<!-- ნ -->
raw ფორმატი გამოიყენება ფოტოგრაფიაში. კამერის სენსორის ინფორმაცია კომპრესირების გარეშე ინახება, რაც ბევრად დიდი ზომის ფაილს ქმნის, თუმცა დიდი რაოდენობით ინფორმაციას ინახავს რომელსაც კომპრესირება დაკარგავდა - ეს ფოტოს დამუშავების უფრო ხარისხიან საშუალებას გაძლევს (რის შემდეგადაც შეგიძლია გამოაქვეყნო კომპრესირებული).

კიდევ რა კონტექსტში გაგიგიათ პიქსელების რაოდენობა?

### ციფრული ფოტოს შექმნა
![](https://www.notebookcheck.net/fileadmin/Notebooks/News/_nc2/galaxy_s7_camera_dual_pixel_t04032016.jpg)


## ვიდეოები
როგორ მიიღება ვიდეო? ბევრი სურათის (frame) სწრაფად (30/60-ჯერ წამში) ჩვენებით (**fps**/frames per second)

### ვიდეოს მოსალოდნელი ზომა
- ერთი კადრი 6 მეგაბაიტამდეა
- წამში 60 კადრი, 360 მეგაბაიტი
- 4 წამი - 1GB ვიდეო

<!-- n -->
მოდი უხეშად დავითვალოთ, რამდენი მეგაბაიტი გამოვა ერთ წუთიანი ვიდეო. რადგან ერთი კადრი 6 მეგაბაიტამდეა, ხოლო თითო წამში 60 კადრია, ერთი წამი 360 მეგაბაიტი გამოდის. ზუსტად ოთხი წამი იქნება საჭირო, რომ გეგაბაიტამდე ავიდეთ! ანუ საშუალო 32 გეგაბაიტიანი ტელეფონი ვიდეოს ორ წუთსაც ვერ ჩაიწერს. რა თქმა უნდა ეს ასე არ არის და სხვადასხვა ფორმატის ვიდეოს (mp4, mov...) შენახვისას გამოიყენება სხვადასხვა კომპრესირების ალგორითმები, რომლებიც ვიდეოს ზომას ამცირებს. შეიძლება წამში 60 კადრია, მაგრამ მათი უმრავლესობა მხოლოდ რამდენიმე პიქსელით განსხვავდება ერთმანეთისგან - მოდი, შევინახოთ მხოლოდ ის პიქსელები, რომლებიც შეიცვალა. 


### კომპრესირების ალგორითმი
ჩაიწერება **პიქსელების რეგიონების** გადაადგილება.

![](https://www.edn.com/wp-content/uploads/media-1067095-mar04fig4motion.gif)

## ტექსტი
### ascii ფორმატი
- 1 ბაიტი
- სხვადასხვა მნიშვნელობა სხვადასხვა ანბანისთვის

![ascii table](https://miro.medium.com/max/3284/1*DHEm7FO7ZATjvH19dmKwoA.png)

<!-- n -->
ascii ფორმატი ძალიან ეკონომიური იყო და სხვა გზა არც ქონდათ - თავდაპირველ კომპიუტერებში მართლა თითოეული ბაიტი ძალიან ძვირი ჯდებოდა. ამიტომ, ეს 255 ციფრი ყველა ქვეყანამ თავისთვის მოირგო - ზოგგან ლათინურ სიმბოლოებს ნიშნავდა, ზოგგან კირილიცას ასოები იყო ჩაწერილი, იაპონელებს თავიანთი იეროგლიფების ენკოდირებაზე მოუხდათ თავის მტვრევა. საბოლოოდ კი ეს ფაილები ბაბილონის გოდოლს გავდა - ერთი ქვეყნის კომპიუტერი ვერაფერს გაუგებდა მეორისას. ამიტომ (ნებაყოფლობით) შეიქმნა  კომისია, რომელიც შეთანხმდა უფრო ფართო - 8 ბაიტიან ფორმატზე, სადაც ყველა ანბანი ჩაეტეოდა.

### utf-8 ფორმატი
- 8 ბაიტი
- მოიცავს სხვადასხვა ანბანის სიმბოლოებს

## არქივები (zip, rar)
გამოიყენება დირექტორიის ფაილად გადასაქცევად
![](https://jakewharton.com/static/post-image/zip_layout@2x.png)

<!-- ნ -->
ფაილებზე ოპერაციას აქვს ფიქსირებული დანახარჯი ერთ ფაილზე. მაგალითად, თუ ვაკოპირებთ ათ ცალ 100MB ფაილს, ეს პროცესი უფრო დიდ დროს წაიღებს, ვიდრე ერთი ცალი 1000MB ფაილი. ეს ფიქსირებული დანახარჯები არის, მაგალითად, გადაკოპირების ადგილას იმის შემოწმება, არის თუ არა ფაილისთვის საკმარისი ადგილი. შემდეგ გადაკოპირების ადგილას სპეციალური ცხრილის შეცვლა, რომ იმ ფოლდერში ახალი ფაილი ემატება და ა.შ. ეს დიდი პრობლემა ხდება, როდესაც საქმე ასობით ან ათასობით ფაილს ეხება. გადაწყვეტა არის ფაილების დროებით ერთმანეთზე მიკერება - დაარქივება, თითქოს ერთი ფაილი იყოს. თავდაპირველი განცალკევების დასაბრუნებლად ვაკეთებთ ამოარქივებას.


### ზოგადი კომპრესირება
![](https://img.favpng.com/11/19/0/run-length-encoding-data-compression-algorithm-lossless-compression-png-favpng-3ePnEaWDhezsnPH0vessmF1UF.jpg)

<!-- ნ -->
არქივების კიდევ ერთ პასუხისმგებლობა არის **ბაიტების** კომპრესირება - იმის ცოდნის გარეშე, თუ რა ფორმატის/ენკოდირების ფაილია. სურათის მაგალითზე ჩანს, რომ ბაიტების რაოდენობა ამ პროცესში რამდენჯერმე მცირდება. **დეკომპრესირებისას** ფაილი უბრუნდება თავდაპირველ ზომას.

ამ ორივე პროცესის შებრუნებას - ამოარქივებას და დეკომპრესირებას - სჭირდება გამოთვლა და შესაბამისად დრო - ფაილის ყოველ ჯერზე გასახსნელად არ გამოდგება. არქივებს იყენებენ გასაგზავნად, გადასაკოპირებლად ან გრძელვადიანი შენახვისთვის
