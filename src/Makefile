RECIPIANT="user@domain"
REVISION=`svnversion`
OBJS="../obj/"
.PHONY: clean release view

${OBJS}/main.pdf: main.tex 
	pdflatex -output-directory=../obj/ main.tex
	pdflatex -output-directory=${OBJS} main.tex

release: ${OBJS}/main.pdf
	pdflatex -output-directory=../obj/ "\def\recipiant{${RECIPIANT}} \def\revision{${REVISION}} \include{main}"
	pdflatex -output-directory=${OBJS} "\def\recipiant{${RECIPIANT}} \def\revision{${REVISION}} \include{main}"

view: ${OBJS}/main.pdf
	@open ${OBJS}/main.pdf

clean:
	@rm ${OBJS}/*.dvi ${OBJS}/*.aux ${OBJS}/*.log ${OBJS}/*.pdf ${OBJS}/*.toc	
