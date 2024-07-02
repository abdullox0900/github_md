# Hoisting nima va qanday ishlaydi?

**Hoisting** JavaScript-ning asosiy kontseptsiyalaridan biri bo'lib, bu atama dastur ishlashidan oldin o'zgaruvchilar va funktsiyalarning deklaratsiyasi kodning yuqoriga ko'tarilishi (hoist) ma'nosini anglatadi. Bu shuni anglatadiki, o'zgaruvchilar va funksiyalar dastur ichida istalgan joyda deklaratsiya qilingan bo'lsa ham, ularning deklaratsiyalari avtomatik ravishda kodning boshiga ko'tariladi.

## Misol

Quyidagi misolda hoisting qanday ishlashini ko'rish mumkin:

```javascript
console.log(myVar) // undefined

var myVar = 5

console.log(myVar) // 5
```

## Funktsiyalar uchun hoisting

Funktsiyalar ham hoisting qilinadi, lekin funktsiya deklaratsiyalari to'liq hoisting qilinadi:

```javascript
myFunction() // "Hello, world!"

function myFunction() {
	console.log('Hello, world!')
}
```

## Hangoma

Bir kun JavaScript ismli dasturning ichida Ali va Vali ismli ikki do'st kod yozayotgan ekan. Ali kod yozishda qiziqarli usul ishlatgan ekan:

```javascript
console.log(myVar) // undefined

var myVar = 5

console.log(myVar) // 5
```

Vali hayron bo’lib so’radi: “Ali, sen nima qilyapsan? O’zgaruvchining qiymatini belgilamasdan avval uni chaqiryapsan-ku!”

Ali kulib dedi: “Bu JavaScript-da hoisting deb ataladi. JavaScript dastur boshlanishidan oldin o’zgaruvchilar va funksiyalarni kodning yuqorisiga ko’taradi. Mana, qanday ishlashini ko’ring.”

**JavaScript dasturi kodni shunday ko’radi:**

```javascript
var myVar // O'zgaruvchi hoist qilingan
console.log(myVar) // undefined

myVar = 5 // Endi qiymati belgilangan
console.log(myVar) // 5
```

Vali yana bir qiziq narsa ko’ribdi:

```javascript
myFunction() // "Hello, world!"

function myFunction() {
	console.log('Hello, world!')
}
```

Vali: “Bu qanday ishlaydi?”

Ali: “Bu ham hoisting! JavaScript funksiyalarni ham kodning yuqorisiga ko’taradi.”

Dastur bu kodni shunday ko’radi:

```javascript
function myFunction() {
	console.log('Hello, world!')
}

myFunction() // "Hello, world!"
```

Ammo, Vali yana bir tajriba o’tkazibdi:

```javascript
myFunction() // TypeError: myFunction is not a function

var myFunction = function () {
	console.log('Hello, world!')
}
```

Ali kulib dedi: “Bu safar sen hamma narsani to’g’ri qilding! Funksiya ifodalari (function expressions) hoisting qilinmaydi.”

Vali xursand bo’lib tushundi: “Demak, biz JavaScriptda sehrli hoistingdan foydalanamiz, lekin faqat deklaratsiyalarda! Function expressions esa hoisting qilinmaydi.”

**Intervyuda berilish ehtimoli**

Hoisting JavaScript-ning muhim kontseptsiyalaridan biri bo’lgani uchun, intervyularda bu savol 60-70% hollarda tushishi mumkin.
