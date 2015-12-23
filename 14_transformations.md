# Трансформации

Cвойство transform модифицирует объект
http://www.w3schools.com/cssref/css3_pr_transform.asp  (пробуем оранжевую кнопку play it)

transform:rotate(45deg); // повернет блок на 45 градусов

div {
    -ms-transform: rotate(7deg); /* IE 9 */
    -webkit-transform: rotate(7deg); /* Chrome, Safari, Opera */
    transform: rotate(7deg);
}
Сейчас свойство transform работает во всех современных браузерах, но для обеспечения работы в более ранних версих необходимо ставить префикс. Запись, указанная выше обеспечивает работу как в ранних версиях, так и в поздних

transform:translate(100px,200px);  // перемещает объект на 100 пикселей вправо, на 200 пикселей вниз


transform: scale(2,3);  // увеличивает в два раза по горизонтали, в три раза по вертикали

transform: skew(20,10);  //деформирует наш блок

Если нам необходимо применить несколько трансформаций к объекту, это можно сделать через запятую. Например,

transform: scale(2,3), skew(20,10)

Перспектива

transition 

transition позволяет добавить плавность в изменение свойств.

Например 
div {
	width:200px;
height:200px;
background:lime;
transition:transform 2s;
}

div:hover {
	transform:rotate(45deg)
}

Добавит нам плавность в повороте при наведении курсора

В случае, если нам нужно задать transition для нескольких свойств это делается через запятую

transition: top 2s,left 2s;




