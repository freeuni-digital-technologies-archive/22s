# 12. cloud

## რა არის საჭირო ვებ აპლიკაციისვის 

![](https://www.menerga.com/fileadmin/_processed_/6/a/csm_Serverroom_with_servers_on_the_left_and_right_side_fbba06e05b.jpg)

<!-- n -->
კოდი მხოლოდ ძალიან პატარა ნაწილია იმ ყველაფრის, რაც აუცილებელია ნამდვილი პროგრამებისთვის.

### servers
- ფიზიკური, დაცული ოთახი 
- მძლავრი სერვერ კომპიუტერები
- სერვერ კომპიუტერებზე ოპერატიული სისტემის გამართვა
- ოპერატიული სისტემის და პროგრამების ახალი ვერსიების დაყენება (აუცილებელია უსაფრთხოებისთვის)

### network 
- მაღალი სიჩქარის და მძლავრი router ინტერნეტში მაღალი სიჩქარით ჩასართავად
- load balancing შემომავალი traffic-ის განაწილება, რომ სერვერ აპლიკაცია არ გადაიტვირთოს/გაიჭედოს
- სერვერების და სერვისების დაკავშირება ერთმანეთთან, ფიზიკური კაბელებით
- სხვადასხვა სერვერების ოპერატიული სისტემების კონფიგურაცია ერთმანეთთან დასაკავშირებლად

### devops
- აპლიკაციისთვის საჭირო პროგრამების დაყენება სერვერზე
- სხვადასხვა სერვერზე სხვადასხვა პროგრამების (backend, frontend, database, microservices) განაწილება
- კოდისგან აპლიკაციის უახლესი ვერსიის შექმნა და სერვერზე გადატანა
- ოპერატიული სისტემის გარემოს კონფიგურაცია 
- უზრუნველყოფა, რომ ყველა სერვერზე აპლიკაციის ახალი ვერსიის დაყენებისას 
- backup - მონაცემების ასლის გაკეთება


### scaling
აპლიკაციების მომხმარებლების ზრდასთან ერთად საჭიროა მეტი სერვერი, კონფიგურაცია და ა.შ


## cloud solutions
მიზანი: on premise საჭიროებების ავტომატური უზრუნველყოფა და სერვისების გაქირავება

### 

![](https://www.visual-paradigm.com/servlet/editor-content/tw/guide/cloud-services-architecture/what-is-aws-architecture/sites/7/2018/09/cloud-computing-an-overview.png)



### მაგალითები
- ინფრასტრუქტურა - სერვერები, ქსელები
- პლათფორმა - მონაცემთა ბაზები, git ჰოსტინგი, აპლიკაციების ჰოსტინგი
- აპლიკაცია - google docs/drive/apps, microsoft teams, dropbox, API სერვისები


## cloud vs on-premise


![](https://coservit.com/servicenav/wp-content/uploads/sites/3/2018/07/http-coservit-com-servicenav-wp-content-uploads-1-3.png)



### სხვა უპირატესობები
- რესურსების მაქსიმალური გამოყენება
- ავტომატური scaling

<!-- ნ -->
შეიძლება არსებობს დღეში რამდენიმე საათი ან წელიწადში რამდენიმე დღე, როცა კონკრეტულ აპლიკაციას მეტი დატვირთვა აქვს. ეს ნიშნავს, რომ ფულს იხდი ტექნიკაში, რომელიც უმეტესად გამოუყენებელია. როდესაც ინფრასტრუქტურას რამდენიმე სხვადასხვა კომპანია ქირაობს, ყველა მხოლოდ იმდენს იყენებს, რამდენიც ჭირდება

მომხმარებლების გაზრდასთან ერთად ავტომატურად დაემატება ან მოაკლდება რესურსები ვირტუალურ სერვერს.

მაგალითად, გამქირავებელს აქვს 16 ბირთვიანი სერვერი, რომელზეც შექმნის რამდენიმე ვირტუალურ სერვერს, რომელსაც რამდენიმე აპლიკაცია გამოიყენებს.

თუ იქირავე 4 ბირთვიანი ვირტუალური სერვერი და მხოლოდ 2-ს იყენებ უმეტესად, დანარჩენი 2 ბირთვი სხვა აპლიკაციას შეხვდება. მეტი საჭიროების გაჩენის შემთხვევაში მომენტალურად მოგენიჭება 2 დამატებითი ბირთვი. ანალიტიკების წყალობით შესაძლებელია ვირტუალური სერვერების სხვადასხვა ფიზიკურ სერვერებზე გადანაწილება ისე, რომ ერთ ფიზიკურ სერვერზე რესურსების გამოყენება სტაბილურად მაქსიმალური იყოს.
