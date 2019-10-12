# Find

> walk a file hierarchy


- find . 

- find . -type f/d

- find . -name  \*.pdf 

- find . -name '\*.pdf' -exec mv -nv {} ../images \;

- find . -name '\*.pdf' -or -name '\*.doc' -exec mv -nv {} ../docs \; --exec sleep 3 \;