### 1. 2 ქ

ქვემოთ ჩამოთვლილი ელემენტებიდან, რომელს შეეცვლება სტილი მოცემული css-ით?

```html
<style>
	#myid {
		background: gray;
	}
</style>
<div>
	<p id="#myid" class="myclass">paragraph</p>
	<span class="myid">some span</span>
	<h1 class="#myid">heading</h1>
	<h2 id="#myid" class=".myid">another heading</h2>
	<h3 id="myid">heading3</h3>
</div>
```

- [ ] span და h3
- [ ] ყველას
- [ ] არცერთს
- [ ] span, h1, h2
- [x] h3
- [ ] არცერთი პასუხი არ არის სწორი


### 2. 2ქ
გვსურს დავწეროთ ფუნქცია, რომელიც იპოვის გადაცემული id-ის მქონე ელემენტს და დაგვიბრუნებს მასში დაწერილ ტექსტს.  რომელი ფუნქცია შეასრულებს ამ პირობას?
```js 
function f1(id) {
	var v = document.getElementById(id)
	v.innerText
}

function f2(id) {
	var v = document.getElementById(id)
	v
}

function f3(id) {
	document.getElementById(id).innerText
}
```
- [ ] ყველა
- [ ] f1 და f3
- [ ] f1
- [ ] f3
- [x] არცერთი
- [ ] არცერთი პასუხი არ არის სწორი


	### 3. 1ქ
რას დაბეჭდავს მოცემული ფუნქცია კონსოლში გამოძახების შემდეგ?
```js
function f1() {
	var l = [3, 4, 8]
	var k = 0
	for (var i = 0; i < l.length; i++) {
		k = k + l[i]
	}
	console.log(k)
}
```

- [ ] 3
- [ ] 4
- [ ] 8
- [ ] 0
- [x] არცერთი პასუხი არ არის სწორი

### 4. 2ქ
რა არის document, console ცვლადები DOM ჯავასკრიპტში?
- [ ] რიცხვი
- [ ] ტექსტი
- [x] ობიექტი
- [ ] სია
- [ ] boolean
- [ ] არცერთი


### 5. 1ქ
რა დაიბეჭდება ამ ხაზებით კონსოლში?
```js
var i = ["my", "name", "is"]
console.log(i[2])
```

- [ ] my
- [ ] name
- [x] is
- [ ] არცერთი
- [ ] undefined
- [ ] null

### 6. 1ქ
აქედან რომელია add ფუნქციის არგუმენტი/პარამეტრი?
```js
function add(a) {
	var sum = a + 2
	return sum
}
```


- [ ] return
- [ ] sum
- [ ] ყველა
- [ ] add
- [x] a
- [ ] 2
- [ ] არცერთი
