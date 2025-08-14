# Читаю

```dataviewjs
	let booksCSS = "";

	let booksData = dv.pages('"Просвещение/Книги"').where(page => {
		if (page.читаю) return page;
	});
	
	for (let book of booksData) {
		booksCSS += `<div class="book">
			<div>${book.Название}</div>
			<div>${book["Автор(ы)"]}</div>
			<a href="${book.file.path}" class="internal-link" aria-label="${book.Название}"><img src="${book.Картинка}" /></a>
			<div>${book.Прогресс}</div>
			<div>${book.ISBN}</div>
		</div>`
	}
	
	dv.el("div", booksCSS, {cls: "books"})
```

---

# К прочтению

```dataviewjs
	let booksCSS = "";

	let booksData = dv.pages('"Просвещение/Книги"').where(page => {
		if (page.читаю == false && page.прочитано == false) return page;
	});
	
	for (let book of booksData) {
		booksCSS += `<div class="book">
			<div>${book.Название}</div>
			<div>${book["Автор(ы)"]}</div>
			<a href="${book.file.path}" class="internal-link" aria-label="${book.Название}"><img src="${book.Картинка}" /></a>
			<div>${book.Прогресс}</div>
			<div>${book.ISBN}</div>
		</div>`
	}
	
	dv.el("div", booksCSS, {cls: "books"})
```

---

# Прочитано

```dataviewjs
	let booksCSS = "";

	let booksData = dv.pages('"Просвещение/Книги"').where(page => {
		if (page.прочитано) return page;
	});
	
	for (let book of booksData) {
		booksCSS += `<div class="book">
			<div>${book.Название}</div>
			<div>${book["Автор(ы)"]}</div>
			<a href="${book.file.path}" class="internal-link" aria-label="${book.Название}"><img src="${book.Картинка}" /></a>
			<div>${book.Прогресс}</div>
			<div>${book.ISBN}</div>
		</div>`
	}
	
	dv.el("div", booksCSS, {cls: "books"})
```

