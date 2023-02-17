# ibooks-notes-exporter

> Highlights are stored in sqlite under
>
> `~/Library/Containers/com.apple.iBooksX/Data/Documents/AEAnnotation`
>
> the idea is to read from the sqlite, and parse in the form we need 

People remember less than 20% of what they read if they are not taking notes.
That's why it's always a good idea to take notes while you are reading.
But if you are reading in iBooks and taking notes there, it's very hard to get them out of that app.
You have to manually copy-paste quotes and your thoughts. ibooks-notes-exporter  solves
that problem. it's a little program that gets all your notes and highlights from iBooks and
exports them into markdown.

Note! **ibooks-notes-exporter** can only extract notes from EPUB files.

## Installation

```shell
cd ${project_dir}
go mod tidy
```

## Usage

First of all, you have to get a list of all your books with notes and highlights.

```shell
cd ${project_dir}
go run main.go books

+----------------------------------+-----------------+----------------------------------------------------------------------------------+
| SINGLEBOOK ID                    | NUMBER OF NOTES | TITLE AND AUTHOR                                                                 |
+----------------------------------+-----------------+----------------------------------------------------------------------------------+
| 4BAE5DA3C95788753173EAE8C63E6034 |               1 | Lorem impsum - John Doe                                                          |
| 7C3FA4F94689D97444BB4E0FD97D7197 |              54 | Hamlet - william shakespeare                                                     |
+----------------------------------+-----------------+----------------------------------------------------------------------------------+
```

And then you can export all your notes from the book into a markdown file.

```shell
go run main.go export 4BAE5DA3C95788753173EAE8C63E6034 > ./LoremImpsum.md
```
