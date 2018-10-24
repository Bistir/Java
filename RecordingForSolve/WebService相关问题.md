WebService相关问题
=====

1.WebService想到哪写到哪的介绍
----

WebService的三大基础技术: xml+xsd, soap, wsdl;
WebService生成wsdl文件,需要根据类中的方法(需要实现的功能)来实现,先完成功能,再生成wsdl文件.

2.WebService流程
----

客户端——> 阅读WSDL文档 (根据文档生成SOAP请求) ——>发送到Web服务器——>交给WebService请求处理器 （ISAPI Extension）
——>处理SOAP请求——> 调用WebService——>生成SOAP应答 ——> Web服务器通过http的方式交给客户端