## RESTful API  
Elasticsearch 提供了功能全面而强大的 RESTful API 与集群进行交互。这些 API 可用来实现以下功能：  
- 查看集群、节点、索引的健康状态，统计值。
- 管理集群、节点、索引数据、元数据，调整集群配置。
- 对索引数据进行 CRUD （Create、Read、Update、Delete）以及各种形式的查询，如全文检索、过滤、聚合、排序等。

详情请参见 Elasticsearch 官方的 [API 文档](https://www.elastic.co/guide/en/elasticsearch/reference/5.6/index.html)。

## 客户端
- 可通过任意支持发送 HTTP/REST 调用的客户端，调用 REST API 访问集群。例如 curl 工具、Kibana Dev Tool。  
- Elasticsearch 提供了各种开发语言的客户端，例如 Java、Python 等，以满足不同开发者的需要。详情请参见 [Elasticsearch Client](https://www.elastic.co/guide/en/elasticsearch/client/index.html)。 
- Elasticsearch 从5.6.0版本开始，发布了官方的 Java High Level REST Client，可用于执行 search、index、delete、update and bulk 操作，同 TransportClient 使用的核心 Java classes 一致，并且是为了替代 TransportClient。详情请参见 [Java High Level REST Client 说明](https://www.elastic.co/guide/en/elasticsearch/client/index.html)。

>版本兼容性上，建议客户端版本同服务端版本保持一致，详情请参见 [兼容性说明](https://www.elastic.co/guide/en/elasticsearch/client/java-rest/6.0/java-rest-high-compatibility.html)，腾讯云 ES 目前提供了多个可选的 Elasticsearch 版本，请注意选择客户端版本。 

## 访问鉴权
选择高级特性（原官方 X-Pack 插件）是白金版时，Elasticsearch 集群将开启用户认证功能，您在通过各种客户端或 API 访问客户集群时，需要输入用户名密码，开源版和基础版则不需要。

在访问集群时，请注意所选择的的 Elasticsearch 高级特性版本，具体使用方式可参考 [客户端访问集群](https://intl.cloud.tencent.com/document/product/845/19538)、[通过 Kibana 访问集群](https://intl.cloud.tencent.com/document/product/845/19541)。 

**关于网络问题的特别说明：**
- 为安全起见，腾讯云 ES 集群构建在私有网络 VPC 内，对集群数据的访问也都限定在同一 VPC 网络内。  
- 用户在购买集群时，所选择的地域和可用区内，必须已经配置过 [VPC](https://intl.cloud.tencent.com/document/product/215/) 和子网。  
- 通常需要在同一 VPC 下由 [CVM](https://intl.cloud.tencent.com/document/product/213) 作为客户端来访问 ES 集群，发起数据的存储和查询请求。  
- 对于腾讯云老用户，如需在已有数据和服务的基础上搭建 ES 集群，在创建 ES 集群时需选择和已有业务相同的 VPC。
