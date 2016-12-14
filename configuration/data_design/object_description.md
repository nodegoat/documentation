### Object Description

Object Descriptions are static fields that describe intrinsic aspects of an Object. In this context, static means a 'non-changing' aspect of an Object.

Examples of static fields are the name of a person, the title of a book or the type of paint used for a painting. Obviously, descriptions are rarely 'non-changing' as personal names or geographical labels might mutate over time. If these changes are of importance for your research question, you should store these in Sub-Objects (see below).

The following Object Descriptions can be created:

*   String – a single line string with a maximum of 5000 characters.

    **Example**: The first name of a person, 'Jacob'. The title of a book: 'Herfsttij der Middeleeuwen'.

*   Type – a relation to another Object in the same or a different Type. One Object Description can contain multiple relations to the referenced Type.

    **Example**: The author of a book is a relation from one Object in the Type 'Book' to one Object in the Type 'Person'. The sender of a letter is a relation from one Object in the Type 'Letter' to one Object in the Type 'Person'. Images that illustrate an article are a relation from one Object in the Type 'Article' to one or more Objects in the Type 'Image'.
*   Classification – a relation to a Category in a Classification (see below). One Object Description can contain multiple relations to one Classification.
*   Integer – an integer (whole number, no decimals) up to a length of 11 digits.
*   Text – non-formatted text field up to 65535 characters.
*   Text (layout) – formatted text field up to 65535 characters. In this field, words can be related to other Objects.
*   True/False – a true/false field.
*   Date – a date field, using the following date formats:
    *   y (1687)
    *   -y (-800)
    *   m-y (03-1687 / 3-1687)
    *   m--y (03--800 / 3--800)
    *   -m-y (-03-800 / -3-800)
    *   d-m-y (09-03-1687 / 9-3-1687)
    *   d-m--y (09-03--800 / 9-3--800)
    *   -d-m-y (-09-03-800 / -9-3-800)
*   Media – upload any kind of media (i.e. png, pdf, mp3).
*   Media (External) – link to external media resources (e.g. http://url.com/map.png or http://youtu.be/jm1os4VzTgA).
*   External – an external relation using URIs. URIs can be plain URLs, or can be retrieved by connecting to the nodegoat Linked Data module to dynamically query SPARQL/API resources like VIAF or Wikipedia.