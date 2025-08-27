
[[Полезные сайты и ссылки (Powerful Websites — Usefull links)]]
	- https://coddy.tech/
	- https://javarush.com/ 
	- https://www.codewars.com/
	- https://www.codingame.com/

---

- [[Обучающий материал]]
- [[Обучение математике 5 класс]]
- [[roadmap/Работа с умеренным темпом|Работа с умеренным темпом]]
- [[roadmap/Идеи для дополнительного дохода|Идеи для дополнительного дохода]]

---

Новые слова и/или выражения (без привязки к языку)
- [[Просвещение/Словарь/А капелла (итал. a cappella)|А капелла (итал. a cappella)]]
- [[Просвещение/Словарь/Словарь - значения, понятия и определения слов (Dictionary - meanings, concepts and definitions of words)|Словарь - значения, понятия и определения слов (Dictionary - meanings, concepts and definitions of words)]]

---

```dataviewjs

	let booksData;
	let bookClass;
	let bookFooter;
	let booksCSS = "";
	
	await dv.header(1, "<div id='filters'><div data-f='reading'>Читаю</div><div data-f='listening'><img src='https://pics.freeicons.io/uploads/icons/png/16957942291681979128-512.png'/> Слушаю</div></div>");

	booksData = dv.pages('"Просвещение/Книги" or "Просвещение/Аудиокниги"').where(page => {
		if (page.читаю || (page.Слушаю)) return page;
	});
	
	for (let book of booksData) {
		// book.Читает ? bookFooter = `Читает: ${book.Читает}` : bookFooter = book.ISBN;
		
		if (book.Читает) bookClass = "listening";
		else bookClass = "reading";
		
		booksCSS += `<div class="book ${bookClass}">
			<div class="bookHeader">
				<div class="title">${book.file.name}</div>
				<div class="author">${book.Автор}</div>
			</div>
			<div class="bookCover">
				<a href="${book.file.path}" class="internal-link" aria-label="${book.Название}"><img src="${book.Обложка}" alt="" /></a>
			</div>
			<div class="bookFooter">
				<progress max='${book.ПрогрессMax}' value='${book.Прогресс}'></progress>
				<div>
					<div>${book.Прогресс}</div>
					<div>${book.Год} год</div>
					<div>${book.ПрогрессMax}</div>
				</div>
			</div>
		</div>`
	}
	
	let test = document.querySelector("#filters").addEventListener("click", event => {
		let filterClass = event.target.dataset['f'];
		
		document.querySelectorAll('.' + filterClass).forEach(item => {		
			if (item.classList.contains('hide')) {
				event.target.style.color = "green";
				item.classList.remove('hide');
			} else {
				event.target.style.color = "gray";
				item.classList.add('hide');
			}
		});			
	});
	
	dv.el("div", booksCSS, {cls: "books"});
		
```