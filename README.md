# Docker_ElasticSearch_SearchEngine_TravelSite
Docker基于ElasticSearch全文搜索引擎的旅游景点搜索网设计

开发环境： Idea + Mysql + ubuntu + Docker + RabbitMQ + ElasticSearch + kibana

  本项目主要是学习利用全文检索引擎框架ElasticSearch实现一个中文旅游网站搜索设计，通过建立一个hotel的索引库关联对应的mysql表数据，实现高效率的查询，解决了传统关系型数据因为数据量大导致的查询瓶颈问题。查询业务是crud中最复杂的业务，涉及到多种条件的组合，查询结果的分页和排序，搜索引擎查询结果的解析；根据查询条件的设置对结果某些信息字段进行聚合分析方便用户的筛选；还有就是试下用户输入查询拼音关键字也可以下拉自动补全功能，这就需要引入拼音分词器以及它和ik分词器的各种组合形成自定义的复合分词器。
  
  项目实现的功能页面不多，主要包括前台用户查询酒店结果和后台管理员对酒店信息添加和维护。其中管理员对酒店维护的时候，因为修改了mysql数据库里面酒店的信息，这样就需要把酒店的最新信息同步到全文搜索引擎中，这里采用了RabbitMQ作为消息中间件实现了它们之间的解耦合。
