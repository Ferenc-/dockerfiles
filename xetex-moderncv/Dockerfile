FROM danieletorelli/xetex

RUN apt-get update && apt-get install -y wget unzip texlive-fonts-recommended

RUN wget http://mirrors.ctan.org/macros/latex/contrib/moderncv.zip \
    && unzip moderncv.zip \
    && mv moderncv /usr/share/texmf/tex/latex/
