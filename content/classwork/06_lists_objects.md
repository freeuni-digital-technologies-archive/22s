# 06. მასივები, ობიექტები
ამ კვირას ხანის აკადემიის რამდენიმე სავარჯიშო განვავრცეთ და ქვემოთ, სავარჯიშოების ბმულების შემდეგ იქნება ეს ვარიანტები/მათი ამოხსნები.

ხანის აკადემიაზე გაკეთებული სავარჯიშოები **არ მოწმდება**, მაგრამ **აუცილებელია** აქ ჩამოთვლილი ყველა სავარჯიშო გაკეთებული გქონდეს, რადგან სხვა შემთხვევაში მომავალ მასალას, დავალებებს, გამოცდას ვერ გაიგებ. 

უმეტეს სავარჯიშოს გადავახტებით, ამიტომ ამ გვერდზე იქნება ჩამონათვალი (ბმულებით) მხოლოდ იმ სავარჯიშოების, რომლებიც აუცილებელია. შეიძლება 1-2 მაინც გამეპაროს და უბრალოდ დაიმახსოვრე, რომ რომელიმე სავარჯიშოში თუ შეგხვდა **draw()** ფუნქცია, ესეეგი სავალდებულო არ არის.

!!! tip "**გაძლიერებული ჯგუფი**"
	ამ ორი კვირის განმავლობაში გააკეთეთ ყველა სავარჯიშო ქვემოთ ჩამოთვლილ თემებში:

	- [თემა: შესავალი JavaScript-ში: ხატვა და ანიმაცია](https://ka.khanacademy.org/computing/computer-programming/programming)
	- [თემა: გაძლიერებული JS: თამაშები & გამოსახულებები](https://ka.khanacademy.org/computing/computer-programming/programming-games-visualizations)
	- [თემა: გართულებული JS: ბუნებრივი სიმულაციები](https://ka.khanacademy.org/computing/computer-programming/programming-natural-simulations)


### ამ კვირის სავარჯიშოები
თუ სავარჯიშოში ან სავარჯიშოს ნაწილში იყო mouseClick/ან ანიმაციის ფუნქცია, ის სავარჯიშო არ არის გასაკეთებელი
- [მასივები](https://ka.khanacademy.org/computing/computer-programming/programming/arrays/pt/intro-to-arrays)
- [ობიექტები](https://ka.khanacademy.org/computing/computer-programming/programming/objects/pt/intro-to-objects)
- [ობიექტზე ორიენტირებული დიზაინი](https://ka.khanacademy.org/computing/computer-programming/programming/object-oriented/pt/object-types)


### სავარჯიშოების გავრცობა
სავარჯიშოების ხანის აკადემიაზე გაკეთების **შემდეგ** შეგიძლიათ წაიკითხოთ პირობის/ამოხსნის სხვა ვარიანტები. 

## მასივები
### საყვარელი ცხოველები
while-ის მაგივრად for ცილკით ასე დაიწერებოდა:
```js
var favoriteAnimals = ["parrots", "cats", "dogs", "dolphin"];

fill(0, 0, 0);
for (var i=0; i<favoriteAnimals.length; i++) {
    text(favoriteAnimals[i], 200, 200+20*i);
}
```


### თანავარსკვლავედების შემქმნელი
მოდი ერთი გრძელი image() ხაზის მაგივრად, მისი არგუმენტები (x, y, star), ცალკე ცვლადებად გავიტანოთ. ასე კოდი უფრო წაკითხვადი ხდება. 
```js
var xPositions = [100, 200, 197];
var yPositions = [200, 30, 150];

var drawStars = function() {
    background(9, 5, 59);
    imageMode(CENTER);
    var star = getImage("space/star");
    for (var i = 0; i < yPositions.length; i++) {
        var x = xPositions[i];
        var y = yPositions[i];
        image(star, x, y, 30, 30);
    }
};
```


ახლა წინა კვირას რომ random() ფუნქცია შეგვხვდა, ეგ გამოვიყენოთ და ვარსკვლავები შემთხვევით შერჩეულ x/y კოორდინატებზე დაიხატება.

```js
var drawManyStars = function() {
    background(9, 5, 59);
    imageMode(CENTER);
    var star = getImage("space/star");
    for (var i = 0; i < 330; i++) {
        var x = random(0, 358);
        var y = random(0, 364);
        image(star, x, y, 20, 20);
    }
};

drawManyStars();

```

## ობიექტები
### ფილმის მიმოხილვა
დასაწყისისთვის, movies ცვლადში კიდევ 1-2 წიგნი ჩაამატე. მოდი, for ციკლში ჩასმამდე, არსებული კოდი ფუნქციად გადავაკეთოთ. დააკვირდი, რომელ ხაზებში გამოიყენება არგუმენტები

```js
function displayMovie(movie, yStart) {
    fill(84, 140, 209);
    textAlign(CENTER, CENTER);
    textSize(20);
    
    text(movie.title, 200, yStart);
    
    fill(0, 0, 0);
    textSize(13);
    
    text(movie.review, 151, yStart + 30);
}
```

ამის შემდეგ უფრო მარტივი იქნება ციკლში ჩასმა. თუ `88+98*i` არ გესმის რატომ წერია, დაუბრუნდი წინა კვირის სავარჯიშოებს.
```js
for (var i=0; i < movies.length; i++) {
    displayMovie(movies[i], 88 + 98*i);
}
```
