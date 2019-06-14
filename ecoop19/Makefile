# Automatically generate unformatted HTML files for the six conference
# days and add code to load JavaScript source files to them 

SCHEDULE=schedule.xml
PYTHON=python2.7
DEST = .
SCRIPT_SRC = ..

INSERTION = 'NR==5{print "<script src=\"jquery-3.0.0.min.js\"></script>\n<script src=\"palette.js\"></script>\n<script src=\"$@.js\"></script>"}1'

all: monday tuesday wednesday thursday friday

${SCHEDULE}:
	wget "https://2019.ecoop.org/dataexport/45121c45-850e-41cb-a6d5-61180d3290e1/acmdlxml.xml" -O ${SCHEDULE}

monday: ${SCHEDULE}
	${PYTHON} $(SCRIPT_SRC)/main.py ${SCHEDULE} 0 | awk $(INSERTION) > $(DEST)/$@.html

tuesday: ${SCHEDULE}
	${PYTHON} $(SCRIPT_SRC)/main.py ${SCHEDULE} 1 | awk $(INSERTION) > $(DEST)/$@.html

wednesday: ${SCHEDULE}
	${PYTHON} $(SCRIPT_SRC)/main.py ${SCHEDULE} 2 | awk $(INSERTION) > $(DEST)/$@.html

thursday: ${SCHEDULE}
	${PYTHON} $(SCRIPT_SRC)/main.py ${SCHEDULE} 3 | awk $(INSERTION) > $(DEST)/$@.html

friday: ${SCHEDULE}
	${PYTHON} $(SCRIPT_SRC)/main.py ${SCHEDULE} 4 | awk $(INSERTION) > $(DEST)/$@.html
