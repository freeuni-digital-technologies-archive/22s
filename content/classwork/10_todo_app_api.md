# 10. todo აპლიკაცია და api
ეს კოდი უბრალოდ წასაკითხად არ არის, ვერ გაიგებ თუ თვითონ არ დაწერე და ნახე რას აკეთებს. ამისთვის საწყის ფაილებზე მე-9 სემინარში ვმუშაობთ, მისი დასრულების შემდეგ შეგიძლია გადმოხვიდე. პროდუქტიული მუშაობისთვის, გამოიძახე ხოლმე ფუნქციები კონსოლში და ნახე, კონკრეტულად რას აბრუნებს/აკეთებს

## აპლიკაციის დასრულება
- id-ის დამატება
- counter-ის დამატება
- ღილაკზე markTaskAsDone მიბმა


## რეფაქტორინგი
index.js სემინარის ბოლოს ასე გამოიყურება. კომენტარებში აღწერილია თით`ეული ცვლილება
```js
/** addTask ეს ფუნქცია ცალკე გავიტანეთ, რომ 
თასქის დამატება პროგრამატულადაც შეგვეძლოს (input-ის წაკითხვის გარდა). მაგალითად, 
ფაილის ბოლოს
**/
function addTask() {
    let taskText = document.getElementById('task-input').value
    addTaskToPage(taskText)
}

function addTaskToPage(taskText) {
    let taskDiv = createTaskElem(taskText, TASKSCOUNTER)
    TASKSCOUNTER++
    let tasksElem = document.getElementById('tasks')
    tasksElem.appendChild(taskDiv)
}

function createTaskElem(taskText, id) {
    let taskDiv = document.createElement('div')

    let doneTaskButton = document.createElement('button')
    doneTaskButton.innerText = '☑️'
    doneTaskButton.onclick = function () {
        markTaskAsDone(id) // ეს ნიშნავს, ამ ფუნქციას ღილაკზე დაჭერისას გამოიძახებს (და არა ახლავე) 
    } 
    doneTaskButton.className = 'task-done-button'
    taskDiv.appendChild(doneTaskButton)

    let taskTextDiv = document.createElement('span')
    taskTextDiv.innerText = taskText
    taskTextDiv.id = 'task-'  + id // ამით შეგვიძლია markTaskAsDone ფუნქციაში ვიპოვოთ, რომელი თასქი უნდა შევცვალოთ
    taskTextDiv.className = 'task-text-div' // არ დაგავიწყდეს style თეგში ამ კლასისთვის მწვანე ფონის დამატება
    taskDiv.appendChild(taskTextDiv)
    
    return taskDiv
}
  

function markTaskAsDone(taskId) {
	document.getElementById('task-' + taskId).className = 'done-task'
}

addTaskToPage('my todo') // ეს ორი ხაზი იმისთვის, რომ ყოველ გადატვირთვაზე არ დაგვჭირდეს ახალი თასქების შექმნა ფუნქციონალის დასატესტად
addTaskToPage('my todo2')
```


## api-ს გამოყენება
ჩაამატე ეს ხაზები ფაილის ბოლოს. ამ თემას მომავალ კვირებში მოვუბრუნდებით.
```js
function addExistingTasks(tasks) {
	for (let i =0; i < tasks.length; i++) {
		addTask(tasks[i].title)
	}
}

fetch('https://jsonplaceholder.typicode.com/todos/')
 .then(response => response.json())
 .then(tasks => addExistingTasks(tasks))
```