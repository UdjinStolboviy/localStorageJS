# localStorageJS

localStorage.setItem("number", 1); //Добавляем или изменяем значение:

console.log(localStorage.getItem("number")); //Выводим его в консоль:

localStorage.removeItem("number"); //удаляем:

localStorage.clear(); //очищаем все хранилище


window.addEventListener("DOMCotentLoaded", function () {
    
    let checkbox = document.getElementById('rememberMe'),
        change = document.getElementById("change"),
        form = document.getElementsByTagName("form")[0];
    
    if (localStorage.getItem("isChecked") === "true") {
        checkbox.checked = true;
    }

    if (localStorage.getItem("bg") === "changet") {
        form.style.backgroundColor = "#FF4766";
    }

    checkbox.addEventListener("click", function () {
        localStorage.setItem("isChecked", true); //Добавляем или изменяем значение:

    });

    change.addEventListener('click', function () {
        localStorage.setItem('bg', 'changed'); //Добавляем или изменяем значение:
        form.style.backgroundColor = "#FF4766";
    });

    let persone = { //создадим объект
        name: "Alex",
        age: 25,
        tech: ["mobile", 'notebook']
    };

    let serializedPersone = JSON.stringify(persone); //сериализуем его
    localStorage.setItem("Alex", serializedPersone); //запишем его в хранилище по ключу:

    console.log(JSON.parse(localStorage.getItem("Alex"))); //спарсим его обратно объект



});
