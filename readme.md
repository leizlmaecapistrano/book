# Base class for all books with encapsulation
class Book:
    def __init__(self, title, author, genre):
        self._title = title  # Protected attribute
        self._author = author  # Protected attribute
        self._genre = genre  # Protected attribute
    
    # Getters to encapsulate access to attributes
    def get_title(self):
        return self._title
    
    def get_author(self):
        return self._author
    
    def get_genre(self):
        return self._genre
    
    # Abstract method to be implemented by subclasses
    def display_info(self):
        raise NotImplementedError("Subclasses must implement this method")

# Subclasses representing specific genres with polymorphism
class ClassicBook(Book):
    def __init__(self, title, author):
        super().__init__(title, author, "Classic")
    
    # Implementing the abstract method (polymorphism)
    def display_info(self):
        return f"Title: {self.get_title()}\nAuthor: {self.get_author()}\nGenre: {self.get_genre()}"

class FantasyBook(Book):
    def __init__(self, title, author):
        super().__init__(title, author, "Fantasy")

    def display_info(self):
        return f"Title: {self.get_title()}\nAuthor: {self.get_author()}\nGenre: {self.get_genre()}"

class FictionBook(Book):
    def __init__(self, title, author):
        super().__init__(title, author, "Fiction")

    def display_info(self):
        return f"Title: {self.get_title()}\nAuthor: {self.get_author()}\nGenre: {self.get_genre()}"

class DystopianBook(Book):
    def __init__(self, title, author):
        super().__init__(title, author, "Dystopian")

    def display_info(self):
        return f"Title: {self.get_title()}\nAuthor: {self.get_author()}\nGenre: {self.get_genre()}"

# Create instances of specific book types (with encapsulation and polymorphism)
books = [
    ClassicBook("The Great Gatsby", "F. Scott Fitzgerald"),
    FantasyBook("Harry Potter and the Sorcerer's Stone", "J.K. Rowling"),
    FictionBook("To Kill a Mockingbird", "Harper Lee"),
    DystopianBook("1984", "George Orwell"),
]

# Use polymorphism to display information about each book
for book in books:
    print(book.display_info())
