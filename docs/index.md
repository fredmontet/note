Note
====

Here are my personal cheat sheets for different technologies I use.
They are ordered by name (`git.md`), written in Markdown format with
a more or less consistent style.


Getting Started
---------------

This project runs on MkDocs. If you want to start it, clone it and run

     pipenv install
     pipenv shell
     mkdocs serve

That's it, otherwise the project is relatively simple. If you want to 
read the note directly in Markdown, just head to the `docs/note` directory.


Deploy
------

To deploy this project, push on `main` and Netlify will build and serve
the files.


Integrate Note in your everyday
-------------------------------

To complete and access to the notes on the day to day, I use a simple 
utility bash script called note. It's in my dotfiles and you can check it 
here :

     https://github.com/fredmontet/dotfiles/blob/master/bin/note     

It's an 'improved' alias to open notes in `vim` with command such as `note git`.

License
-------

[MIT](https://choosealicense.com/licenses/mit/)