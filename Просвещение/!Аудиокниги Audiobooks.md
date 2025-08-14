# Слушаю

```dataviewjs
	let booksCSS = "";

	let booksData = dv.pages('"Просвещение/Аудиокниги"').where(page => {
		if (page.Слушаю) return page;
	});
	
	for (let book of booksData) {
		booksCSS += `<div class="book">
			<div>${book.Название}</div>
			<div>${book["Автор(ы)"]}</div>
			<a href="${book.file.path}" class="internal-link" aria-label="${book.Название}"><img src="${book.Обложка}" /></a>
			<div>${book.Прогресс}</div>
			<div>Озвучивает: ${book.Озвучивает}</div>
		</div>`
	}
	
	dv.el("div", booksCSS, {cls: "books"})
```

---

# Для прослушивания

```dataviewjs
	let booksCSS = "";

	let booksData = dv.pages('"Просвещение/Аудиокниги"').where(page => {
		if (page.Слушаю == false && page.Прослушано == false) return page;
	});
	
	for (let book of booksData) {
		booksCSS += `<div class="book">
			<div>${book.Название}</div>
			<div>${book["Автор(ы)"]}</div>
			<a href="${book.file.path}" class="internal-link" aria-label="${book.Название}"><img src="${book.Обложка}" /></a>
			<div>${book.Прогресс}</div>
			<div>Озвучивает: ${book.Озвучивает}</div>
		</div>`
	}
	
	dv.el("div", booksCSS, {cls: "books"})
```

---

# Прослушано

```dataviewjs
	let booksCSS = "";

	let booksData = dv.pages('"Просвещение/Аудиокниги"').where(page => {
		if (page.Прослушано) return page;
	});
	
	for (let book of booksData) {
		booksCSS += `<div class="book">
			<div>${book.Название}</div>
			<div>${book["Автор(ы)"]}</div>
			<a href="${book.file.path}" class="internal-link" aria-label="${book.Название}"><img src="${book.Обложка}" /></a>
			<div>${book.Прогресс}</div>
			<div>Озвучивает: ${book.Озвучивает}</div>
		</div>`
	}
	
	dv.el("div", booksCSS, {cls: "books"})
```

