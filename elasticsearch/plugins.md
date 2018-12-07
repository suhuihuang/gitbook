# Elasticsearch 插件

1. Head 插件

   > Elasticsearch-Head-Chrome扩展程序

   https://chrome.google.com/webstore/detail/elasticsearch-head/ffmkiejjmecolpfloofpjologoblkegm

   *需要翻墙才能访问。*

2. ik 插件

   > https://github.com/medcl/elasticsearch-analysis-ik/releases?after=v1.10.6

   安装：

   ```
   /usr/share/elasticsearch/bin/elasticsearch-plugin install https://github.com/medcl/elasticsearch-analysis-ik/releases/download/v5.6.1/elasticsearch-analysis-ik-5.6.1.zip
   ```

   参数说明：

   __ik_max_word__: 会将文本做最细粒度的拆分，比如会将“中华人民共和国国歌”拆分为“中华人民共和国,中华人民,中华,华人,人民共和国,人民,人,民,共和国,共和,和,国国,国歌”，会穷尽各种可能的组合；

   __ik_smart__: 会做最粗粒度的拆分，比如会将“中华人民共和国国歌”拆分为“中华人民共和国,国歌”。

3. 



