JFLAGS = -g
JLIB = -classpath ".;sqlite-jdbc-3.7.2.jar"
JC = javac
JVM= java
.SUFFIXES: .java .class
.java.class:
		$(JC) $(JFLAGS) $*.java

CLASSES = \
		Request.java \
		Response.java \
		FormatterWebServer.java \
		ThreadServer.java \
		Server.java \
		SMTPServer.java \
		SMTPClient.java \
		SQLiteJDBC.java 

MAIN = Server
SMTPSERVER = SMTPServer
SMTPCLIENT = SMTPClient
SQLite = SQLiteJDBC

default: classes

classes: $(CLASSES:.java=.class)

run: $(MAIN).class
		$(JVM) $(MAIN) $(ARGS)

clean:
		del *.class
		del logs/*
		del SMTP_SERVER.db

smtpserver: $(SMTPSERVER).class
		$(JVM) $(JLIB) $(SMTPSERVER)

smtpclient: $(SMTPCLIENT).class
		$(JVM) $(JLIB) $(SMTPCLIENT)

exampleDB: $(SQLite).class
		$(JVM) $(JLIB) $(SQLite)

