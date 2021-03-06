SysmonHunter：一個簡單的基於ATT&CK的Sysmon日誌狩獵工具

SysmonHunter使用ElasticSearch和Neo4j來儲存異常的威脅物件及其之間的關係，用python pandas庫完成資料的清洗和統計工作，最終以web介面形式呈現。

![img](https://mdimg.wxwenku.com/getimg/ccdf080c7af7e8a10e9b88444af983938283e90d3d101af77cbb1f5cc63d0c8f50d493d8ab8ed0dbfbb2f35cc0e44453.jpg)



#從VM中開啟ova檔案並且從虛擬機器中找到SysmonHunter的虛擬IP

![image](https://github.com/qwq1358qwq/Final-homework-Sysmonhunter/blob/main/image-20210621223837865.png)

#執行Elasticsearch(成功的畫面)

![image](https://github.com/qwq1358qwq/Final-homework-Sysmonhunter/blob/main/image-20210617184455417.png)

#執行Neo4j(成功的畫面)

![image](https://github.com/qwq1358qwq/Final-homework-Sysmonhunter/blob/main/image-20210617185132968.png)



#Elasticsearch,winlogbeat,neo4j的位置

![image](https://github.com/qwq1358qwq/Final-homework-Sysmonhunter/blob/main/image-20210621224004888.png)

es_host=http://localhost:9200 -> Elasticsearch位置

neo4j_host=bolt://localhost:7687 -> neo4j位置

attack_yaml=misc/attack.yaml- > 攻擊比對



#winlogbeat

https://www.elastic.co/downloads/beats/winlogbeat ->安裝winlogbeat



#Winlogbeat設定，主機送到Elasticsearch的位置

![image](https://github.com/qwq1358qwq/Final-homework-Sysmonhunter/blob/main/image-20210621225348437.png)



#Elasticsearch-Head，主機觀察Elasticsearch的資料
![image](https://github.com/qwq1358qwq/Final-homework-Sysmonhunter/blob/main/image-20210621223724425.png)

#Elasticsearch-Head



#從Elasticsearch-Head中的6/22 05:36 User的LOG

![image](https://github.com/qwq1358qwq/Final-homework-Sysmonhunter/blob/main/image-20210622181918391.png)



#把CSV檔案轉道ElasticSearch的資料庫(從Chrome ElasticSearch-Head可觀察到)![image](https://github.com/qwq1358qwq/Final-homework-Sysmonhunter/blob/main/image-20210622234709659.png)

python agent.py -c conf/example.conf -t csv -i test/empire.csv



