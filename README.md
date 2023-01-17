# jdk-xalan-issue-reproducer
This is a simple reproducer for JDK Xalan issue When generating tranlet classes by giving package name.

```
javac Main.java
java Main test.xsl
```

It outputs `test/org/acme/die_verwandlung.class`

But it should be `test/org/acme/MyTranslet.class` and I think it is an issue in JDK Xalan which has the default `_packageName` with `die.verwandlung`.
The potenial fix could be https://github.com/zhfeng/jdk11u-dev/commit/7e6cad7737d15644600efbbdd8fb1f6be46a672e

