---
title: DeepSeek 学习手册
date: 2025-02-11 10:37:28
tags:
---

## API 搭建知识库
如果本地数据不涉密,还想获得最佳使用效果,那肯定得选满1血的DeepSeekR1模型。
我们来看看怎么利用API用上满血的R1模型(671B)。

1、先下载一个叫Cherry Studio的软件。
地址: https://cherry-ai.com/download

![image](http://maikoushuo.oss-cn-beijing.aliyuncs.com/DeepSeek-image.png)

2、登录/注册「硅基流动」,新用户会赠送2000万Token额度。
地址: https://cloud.siliconflow.cn/i/S97XY4rE
![image](http://maikoushuo.oss-cn-beijing.aliyuncs.com/DeepSeek-image-1.png)

3、来到API密钥生成界面,创建或者复制已有的密钥。
![image](http://maikoushuo.oss-cn-beijing.aliyuncs.com/DeepSeek-image-2.png)

4、来到CherryStudio,配置 API Key。
![image](http://maikoushuo.oss-cn-beijing.aliyuncs.com/DeepSeek-image-3.png)

5、在「硅基流动」模型广场首页,排在前两位的就是「硅基流动」和「华为云」合作发布的DeepSeek R1/V3模型。
如果需要推理能力,记得打开并复制R1模型的名称。
在「Cherry Studio」模型服务的硅基流动下方,添加相应模型。
![image](http://maikoushuo.oss-cn-beijing.aliyuncs.com/DeepSeek-image-4.png)

6、现在对话模型有了R1,还缺少一个嵌入模型。

嵌入模型的主要作用是将本地文件的内容转换成有意义的数字,存储到向量数据库中。
在用户提问时,利用RAG技术在数据库中搜索到相似答案最终回复用户。
我们再配置一个向量模型:BAAI/bge-m3,如果希望搜索的精准度更高,可以选择Pro/BAAI/bge-m3。
![image](http://maikoushuo.oss-cn-beijing.aliyuncs.com/DeepSeek-image-5.png)

7、在「Cherry Studio」创建知识库,选择刚才配置的嵌入模型,这样就会自动利用对应的模型来向量化数据。
![image](http://maikoushuo.oss-cn-beijing.aliyuncs.com/DeepSeek-image-6.png)

8、上传本地文件进行向量化。
如果本地PDF文件是扫描件、手写件,或者带有复杂的表格和数学公式,解析效果会很差,甚至无法解析。
这样才可以正常回复知识库的内容:

如果追求执行比,推荐使用Doc2x:https://doc2x.noedgeai.ccom?inviteCode=4A6KOD
如果希望更加稳定,那么可以考虑Textin:https://www.textin.com/market/detail/pdf_to_markdown
当我们上传文件后,箭头指向的图标如图所示,则代表向量量化成功。
![image](http://maikoushuo.oss-cn-beijing.aliyuncs.com/DeepSeek-image-7.png)


9、测试使用,这一步添加助手,并选择刚配置的满血R1模型。
![image](http://maikoushuo.oss-cn-beijing.aliyuncs.com/DeepSeek-image-8.png)