# Reading Notes 16

### What are DTOs?
- Data transfer object.
- They are used to:
    - Remove circular references
    - Hide particular props that clients should not see when sending them.
    - Flatten object graphs that contain nested objs to make them more convenient for clients.

Solid example:
``` js
namespace BookService.Models
{
    public class BookDto
    {
        public int Id { get; set; }
        public string Title { get; set; }
        public string AuthorName { get; set; }
    }
}

namespace BookService.Models
{
    public class BookDetailDto
    {
        public int Id { get; set; }
        public string Title { get; set; }
        public int Year { get; set; }
        public decimal Price { get; set; }
        public string AuthorName { get; set; }
        public string Genre { get; set; }
    }
}
```

Think of DTOs as a way to "package" data going from one end to the next.


