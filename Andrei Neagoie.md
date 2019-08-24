# ملخص الدرس 115
## هيكلة البيانات في الكائن والمصفوفة
### الكائن OOP
الكائن هو عبارة عن مجموعة خصائص و قيمة لهذي الخصائص

```javascript
var a ={
name:"John", // نص
age:26, // رقم
Hobby:"Soccer", // نص
isMarried:false, // قيمة منطقية
spells:["shazam","boo"],  // مصوفة داخل الكائن
shout:function(){  //دالة داخل الكائن وتسمى ميثود method
		console.log("AHH");}
	};
```
### الاستدعاء
```javascript
a.name // استدعاء خاصية
a.spells[] // استدعاء مصفوفة من داخل الكائن
a.shout() // استدعاء الميثود من دخال الكائن
```

### المصفوفة array
```javascript
var list = [ {
		username:"andy",
		password:"123456",}
	{	username:"Jess",
		password:"abc123",}
		];
```
### الاستدعاء
```javascript
list[0].passwrod; // استدعاء كلمة المرور للكائن الي في موقع العنصر الاول من المصفوفة
```
### يمكن للكائن ان يحمل مصفوفة ويمكن للمصفوفة ان تحمل كائن
---
# ملخص درس 118
## function declaration
  ```javascript
function  newFnction(){
}
```
## function expression
```javascript
var  function  =  function  name(){
}
//دالة معرفة غير مجهولة اسمها name
```
or
```javascript
var  function  =  function(){
}
//دالة مجهولة ليس لها اسم
```
معنى expression : انها تقدم او تتنج قيمة
---
# ملخص الدرس 119
## التكرار Loop
### for
```javascript
var todos=[ "Clean room",
			"Brush teeth",
			"Exercise",
			"Eat healthy",
			"Study javascript"]
for (var i = 0; i < todos.length; i++){ // todos.length يعني ترار بطول المصفوفة
		console.log(todos[i] + "!");} // نريد اظافة ! في الاخير نستخدم + للربط
```
### while
```javascript
var counterOne = 0;
while (counterOne < 10){
		console.log(counterOne);
		counterOne++}
```
### do
```javascript
var counterTwo = 10
do {
		console.log(counterTwo);
		conuterTwo--;
	}
while (conuterTwo > 10);
// do سوف تعمل على الاقل مرة واحدة ثم تحق من الشريط
```
### foreach
```javascript
todos.foreach(function(todos, i){ // i يعني الفهرسة // todos الباراميتر الي يقراء عناصر المصفوفة
		consol.log(todos,i);}
```
or
```javascript
function logtodos(todo, i){
		console.log(todo, i);}  
todos.foreach(logtodos); // استدعاء الدلة
```
---
# الدرس رقم 120 تطبيق على عملي انشاء مدونة مع شاشة تسجيل دخول
```javascript
var database = [{
        username: "andrei",
        password: "secret"
    },
    {
        username: "ingreid",
        password: "777"
    },
    {
        username: "bobby",
        password: "123"
    },
];
// مصفوفة فيها بيانات تسجيل دخول المستخدمين
```

```javascript
var newsfeed = [{
        username: "bobby",
        timeline: "i am so tired 🤢🤢🤢🤢🤢🤢"
    },
    {
        username: "sally",
        timeline: "have some fun 🎂🎂🎂"
    },
    {
        username: "mitch",
        timeline: "JavaScript (/ˈdʒɑːvəˌskrɪpt/),[8] often abbreviated as JS, is a high-level, interpreted scripting language that conforms to the ECMAScript specification. JavaScript has curly-bracket syntax, dynamic typing, prototype-based object-orientation, and first-class functions.🎅🎅🎅🎅🎅"
    },
];
// مصفوفة فيها اسماء المستخدمين مع مدوناتهم
```

```javascript
function isuservaild(username, password) { // دالة تتحقق من اسم المستخدم وكلمة المرور
    for (var i = 0; i < database.length; i++) {  // جملة تكرار تحقق من وجود اسم المستخدم وكلمة المرور في قاعدة البيانات
        if (database[i].username === username && database[i].password === password) { //  تحقق من توافق اسم المستخدم وكلمة المرور
            return true; // نرجع صح اذا كانت اسم المستخدم وكلمة المرور صحيح
        }

    }
    return false; // نرجع خطا اذا كان اسم المستخدم وكلمة المرور خطا
}
```
```javascript
function singIn(username, password) { // دالة لستجيل الدخول
    if (isuservaild(username, password)) { // تمرير بيانات الدخول الى دالة التحقق من اسم المستخدم وكلمة المرور
        console.log("seccss loging");
        for (var l = 0; l < newsfeed.length; l++) { // جملة تكرار تعرض اسم المستخدمين ولمنشور المستخدمين
            document.write("<h1>" + newsfeed[l].username + "</h1>");
            document.write("<h3>" + newsfeed[l].timeline + "</h3>" + "<br>");
        }
    } else { // اذا كان المستخدم غير موجود او كلمة المرور خطا
        alert("Sorry, user not vaild");

    }
}
```
```javascript
// نطلب من المستخدم ادخل البيانات
var usernameprompt = prompt("enter username:");
var passwrodprompt = prompt("enter passwrod:");
singIn(usernameprompt, passwrodprompt); // تمرير البيانات الى دالة تسجيل الدخول
```
