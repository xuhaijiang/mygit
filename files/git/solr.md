### [Lucene](http://lucene.apache.org/)
Lucene是目前最受欢迎的Java全文搜索框架，准确地说，它是一个全文检索引擎的架构，提供了完整的查询引擎和索引引擎，部分文本分析引擎。Lucene为开发人员提供了相当完整的工具包，可以非常方便地实现强大的全文检索功能。

### [Apache Solr](http://lucene.apache.org/solr/)
Solr也是基于Java实现的，并且是基于Lucene实现的，Solr的主要特性包括：高效、灵活的缓存功能，垂直搜索功能，高亮显示搜索结果。值得注意的是，Solr还提供一款很棒的Web界面来管理索引的数据。


### [ElasticSearch](http://www.elasticsearch.org/)
ElasticSearch就是一款基于Lucene框架的分布式搜索引擎，并且也是一款为数不多的基于JSON进行索引的搜索引擎。ElasticSearch特别适合在云计算平台上使用。


### Solr Quick Start

Solr启动、关闭命令:

	E:\solr_dir\bin>solr start -e cloud -noprompt
	E:\solr_dir\bin>solr stop -all
	
	note:

windows post.jar Examples 命令

	java -Dc=gettingstarted -jar post.jar *.xml
	java -Ddata=args -Dc=gettingstarted -jar post.jar '<delete><id>42</id></delete>'
	java -Ddata=stdin -Dc=gettingstarted -jar post.jar < hd.xml
	java -Ddata=web -Dc=gettingstarted -jar post.jar http://example.com/
	java -Dtype=text/csv -Dc=gettingstarted -jar post.jar *.csv
	java -Dtype=application/json -Dc=gettingstarted -jar post.jar *.json
	java -Durl=http://localhost:8983/solr/techproducts/update/extract -Dparams=literal.id=pdf1 -jar post.jar solr-word.pdf
	java -Dauto -Dc=gettingstarted -jar post.jar *
	java -Dauto -Dc=gettingstarted -Drecursive -jar post.jar afolder
	java -Dauto -Dc=gettingstarted -Dfiletypes=ppt,html -jar post.jar afolder
	
	
	
Solr管理UI访问：

	http://localhost:8983/solr
	
	
### 
