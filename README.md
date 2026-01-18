# PythonOOPLibrarySystem
blah blah blah im bored of this

class Book:
    def __init__(self, title, author, is_borrowed=False):
        self.title = title
        self.author = author
        self.is_borrowed = is_borrowed

    def borrow(self):
        if not self.is_borrowed:
            self.is_borrowed = True
        else:
            print("Unable to borrow book. Already borrowed.")

    def return_book(self):
        if self.is_borrowed:
            self.is_borrowed = False
        else:
            print("Book not borrowed. Cannot return.")

    def __str__(self):
        status = "Borrowed" if self.is_borrowed else "Available"
        return f"'{self.title}' by {self.author} ({status})"

#%%
book1 = Book("harry potter", "JK Rowling", False)
#%%
book1.borrow()
#%%
book1.return_book()
#%%
print(book1)
#%% md
Library Class:
#%%
class Library:
    def __init__(self):
        self.books = []

    def add_book(self, book):
        self.books.append(book)

    def list_available_books(self):
        for book in self.books:
            print(book)

    def find_book_by_title(self, title = ""):
        title = title.lower()
        for book in self.books:
            if book.title.lower() == title:
                print("Book found.")    # return book
            else:
                print("Book not found.")

    def remove_book(self, book):
        if self.books.__contains__(book):
            self.books.remove(book)
        else:
            print("Book not found.")


#%%
myLibrary = Library()
#%%
myLibrary.list_available_books()

#%%
myLibrary.find_book_by_title("harry potter")
#%%
myLibrary.add_book(book1)
#%%
myLibrary.remove_book(book1)
