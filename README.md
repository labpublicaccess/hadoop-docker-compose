BASICS :

start terminal

ls (check for hadoop-docker-compose )
cd hadoop-docker-compose

./run.sh
init

-> #mode
ls - to see the files
hdfs dfs -mkdir /nameofdirectory

nano input.txt/py/scala/pig/csv - to create and enter into the file to write further codes

to exit nano file - CTRL +S , CTRL X OR CTRL 0 , ENTER , CTRL-X

rm name.txt - to remove the file

hdfs dfs -put file.txt /nameofdir 
hdfs dfs -ls / (to see all directories inside)

localhost:9870 - for streaming check - Utilities-FileSystem

??
./start-all.sh

?????
hdfs dfs -copyFromLocal your_local_path /user/your_username/your_directory/
hdfs dfs -cat /user/your_username/your_directory/your_file (print contents)
hdfs dfs -copyToLocal /user/your_username/your_directory/your_file your_local_path
hdfs dfs -mv /user/your_username/source_dir/your_file /user/your_username/destination_dir/(Move files within)
hdfs dfs -chmod 777 /user/your_username/your_directory/your_file (permissions)
hdfs dfs -getmerge /user/your_username/source_dir/ /your_local_path/combined_file






MAPREDUCE(NORMAL #MODE)  :

create input file and enter values
create mapper file as nano mapper.py 
create reducer as reducer.py

To Execute :

cat input.txt | python3 mapper.py
cat input.txt | python3 mapper.py | sort | python3 reducer.py

Streaming - 

mapred streaming -input /inputpathhdfs -output /outputpathhdfs -file /pathtomapper.py -mapper /pathtomapper.py -reducer /pathtoreucer.py -file/pathtoreducer.py

here -
inputpath should always be in hdfs directory
outpath can be /mydir/out - stores output in out inside hdfs directory 
/parthtomapper can be just mapper.py in local
/pathtoreducer can be just reducer.py in local

or both file and mapper/reducer





PIG(NORMAL #MODE) :

Create the text file using nano ip.txt - enter the code
use hdfs dfs -put (...) to transfer file to the directory you have made

create pigscript file using nano pigs.pig - enter the code -

NOW - mapreduce mode(file needs to be availabe in hdfs directory in pigscript code ) -
 
pig -x mapreduce pigscript.pig

but local mode -

pig -x local pigscript.pig

INSIDE-PIG-CODE: STORE AND LOAD INTO SHOULD BE MAINTAINED




SPARK(scala mode) :

*To enter scala mode -
spark-shell 

*OR ( if you dont want to enter the scala , line by line mode , you can just create scala file in #mode and run it using )-

create scala file using nano input.scala - fill the code 

*Run the code in #mode(but this executes in scala mode):

spark-shell -i name.scala

now further inside scala you can run your codes line by line as wish/code




PYSPARK(NORMAL #MODE):

create the nano name.py file and enter the code 

for which you will also have to create a nano data.csv file and enter values 


TO RUN :

python3 name.py





HIVE : 

HBASE:
