# About
This is a website project that allows users to browse a list of books.
It is done using HTML, CSS, and JavaScript.



## Features

*the front page contains a list of books, displayed in a table by author, title and genre
*the list is organized alphabetically by author
*the page contains a search bar
*users can search by author, title, or genre
*the page is dynamic

### Technical Features

*the book list is displayed from the JSON file 'listofbooks.json'

*the book list is styled using CSS (styles.css file) and follows the BEM naming methodology

*the list is displayed by two JavaScript functions: displayList(), and displaySearch()

*the list is sorted by the folowing JavaScript function:
```
function sort(list) {
    return list.sort(function(a, b){
        let x = a.author.toLowerCase();
        let y = b.author.toLowerCase();
        if (x < y) {return -1;}
        if (x > y) {return 1;}
        return 0;
    })
}
```

*the search results are given with the following function:
```
 function search(searchQuery, list) {
            if(searchQuery == "")
                displayList();
            else {
                searchQuery = searchQuery.toLowerCase()
                console.log(searchQuery)
                return list.filter(book => {
                    if(book["author"].toLowerCase().includes(searchQuery) ||
                       book["title"].toLowerCase().includes(searchQuery) ||
                       book["genre"].toLowerCase().includes(searchQuery))
                        return true;
                    else
                        return false;
                });
            }
        }
```

