# ideas related to LuaJIT

### LPEG syntax builder

the arcane syntax of lpeg is difficult for me to remember and keep it all straight in my head, so I want to be able to build the arcane syntax using different steps or sequences through the creation process:
1. find "static"
2. jump past whitespace
3. find ["function", "class", ...]
4. match ($name):
    a. [0-9] followed by
    b. [a-zA-Z0-9]+
5. matchMany ($params):
    a. ensure+skip '('
        a. [a-zA-Z0-9]+
        b. (optional) ','
        c. jump past whitespace
    c. ensure+skip ')'
...

something like that, where I can then test text against the matcher, point it at a file, and then prolly save a unittest or something; to really lock it in. lol.

in my code editor, these lpeg statements would show up as a symbol, and when zooming/activating it, I can see those steps (and if I really want to look at the code for those steps, I can just read the text -- cause all bytecode gets rendered into some *real* language like js,c,c++,d,lua,etc. so just look at the syntax for that language)

;
