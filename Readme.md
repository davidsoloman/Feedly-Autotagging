# Feedly auto tagging
A simple proof of concept machine learning approach to automatically tag articles 
in [Feedly](http://www.feedly.com) based on the recent tagging activity.
The whole project is aimed to run on a Raspberry PI.

The only additional information needed is a valid API key which can be obtained
from https://feedly.com/v3/auth/dev .

The project also shows some nice usage of [Java8 Streams](http://www.oracle.com/technetwork/articles/java/ma14-java-se-8-streams-2177646.html).

# How to run
```
git clone https://github.com/locked-fg/Feedly-Autotagging.git feedly-tagger
```
Add a cron job that calles a shell script:
```
#/!bin/bash
set -e
cd ~/feedly-tagger
git pull origin master
mvn clean compile assembly:single
java -jar target/*.jar hereComesYourApiKey auto
```