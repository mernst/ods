
sources=$(wildcard ods/*.java)

classes=$(sources:.java=.class)

all: 
	javac ods/*.java
	jar cvf ods.jar ods/*.class

ods.jar:  $(classes)
	jar cvf ods.jar ods/*.class

%.class : %.java
	javac -Xlint $< 

clean :
	rm -f ods.jar ods/*.class

check-index:
	${CHECKERFRAMEWORK}/checker/bin/javac ${sources} -processor index -AprintErrorStack -Xmaxerrs 10000 -Xmaxwarns 10000
