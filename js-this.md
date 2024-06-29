```javascript
// Metodda
const shaxs = {
    ism: 'John',
    salomlash: function() {
        console.log('Salom, ' + this.ism);
    }
};

shaxs.salomlash(); // Natija: Salom, John

// Yolg'iz
console.log(this); // Natija: [object Window] (brauzerda)

// Funksiyada
function ko'rsat() {
    console.log(this);
}

ko'rsat(); // Natija: [object Window] (qat'iy rejimda emas)
           // Natija: undefined (qat'iy rejimda)

// Voqeada
document.getElementById('btn').addEventListener('click', function() {
    console.log(this); // Natija: <button id="btn">...</button>
});

// call, apply, va bind ishlatish
const shaxs1 = {ism: 'Alice'};
const shaxs2 = {ism: 'Bob'};

function salomlash() {
    console.log('Salom, ' + this.ism);
}

salomlash.call(shaxs1); // Natija: Salom, Alice
salomlash.apply(shaxs2); // Natija: Salom, Bob

const salomlashAlice = salomlash.bind(shaxs1);
salomlashAlice(); // Natija: Salom, Alice
```
