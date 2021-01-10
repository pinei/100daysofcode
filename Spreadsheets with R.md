# Spreadsheets with R

Read, merge and write spreadsheets

```
# Excel libraries
library(readxl)
library(writexl)

# Tidyverse
library(dyplr)
library(magrittr)

# Spreadsheet with fields ISBN, TITLE
books <- read_excel('national_books.xls') 

# Spreadsheet ISBN, AUTHORID, NAME (discard duplicates)
authors <- read_excel('authors.xls') %>% unique()

# Normalize ISBN field ('0-345-24223-8' -> '0345242238')
n_isbn <- function(str) {
	str %>% str_remove_all("-") %>% substr(1, 10)
}

books$N_ISBN <- with(books, n_isbn(ISBN))
authors$N_ISBN <- with(authors, n_isbn(ISBN))

book_authors <- merge(x = books, y = authors, all.x = TRUE, all.y = FALSE, by.x = c("N_ISBN"), by.y = c("N_ISBN") %>%
   select("ISBN.x", "TITLE", "NAME") %>%
   rename("ISBN" = "ISBN.x", "AUTHOR_NAME" = "NAME")

write_xlsx(x = book_authors, path = "book_authors.xls", col_names = TRUE)
```