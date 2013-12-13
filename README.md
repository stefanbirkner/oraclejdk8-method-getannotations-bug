oraclejdk8-method-getannotations-bug
====================================

[![Build Status](https://secure.travis-ci.org/stefanbirkner/oraclejdk8-method-getannotations-bug.png)](https://travis-ci.org/stefanbirkner/oraclejdk8-method-getannotations-bug)

Example for a regression bug introduced in JDK 8. I created a bug report: http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=9008626 (Will be available when it is accepted.)

I created a package private class `Super` that has a public annotated method `methodOfSuper`. The public class `Sub` extends the class `Super`. `Sub.class.getMethod("methodOfSuper").getAnnotations().length` returns  `0` with JDK 7 and `1` with JDK 8.

This is the cause for junit-team/junit#749.

(Maybe of interest, too: http://bugs.sun.com/bugdatabase/view_bug.do?bug_id=6815786 ) 
