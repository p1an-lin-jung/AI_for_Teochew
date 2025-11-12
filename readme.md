
# AI for Teochew

本项目搜集、整理现有的将AI语音技术（主要是语音合成和语音识别）应用到潮州方言的各类工作（论文、商业产品、个人开发、数据集）。

## 现有工作

### 论文

##### [LREC-COLING 2024] [Experiments on Speech Synthesis for Teochew, Can Taiwanese Help?](https://aclanthology.org/2024.lrec-main.598.pdf) 

很幽默的一篇论文，作者尝试进行潮汕话的语音合成，却懒得做数据集，于是采用了一种方法：从在线潮汕话词典中获取单个字或词的录音文件，与数据量较大的台湾闽南语数据集混合在一起，期望通过`句子级的闽南语数据` + `字词级的潮汕话数据`，让模型学习到`句子级的潮汕话语音合成能力`，例如变调能力。

最终，由于台湾闽南语和潮汕话实际差别过大，作者的设想并没成功实现。


### 商业产品

- 1、讯飞输入法-潮汕话识别（实际是翻译）
  
    科大讯飞的讯飞输入法在2022年加入了对潮汕方言的支持，但是其噱头大于使用，实际效果可以说是极差，只能识别很日常、常规的词汇，稍微复杂一点的词，甚至是本地地名（如牌坊街、澄海、潮阳）都识别不了，反倒是对很多闽南语词汇识别的挺准。并且自推出之后从未更新过，多半只是骗补贴的应付项目。

- 2、腾讯API
- 新版微信语音转文字功能，支持潮汕话输入、发送文字。但如若发送的是语音消息，再点击转文字，则不支持识别。
  ![image](./data/wechat_asr.jpg)

- get 笔记（小程序、app）
    ~~支持27种方言的识别，是目前对潮州话识别支持最好的产品，会识别为谐音字~~。
    get笔记母公司本身没太强的AI模型研发能力，其语音转写能力是由腾讯云提供的服务。
    ![image](./data/tencent_cloud.jpg)
  
- 3、五方联手的“家己人”识别器

    ~~目前唯一一个可能可以期待的项目。暂未实际发布~~。
    五方机构分别是：
    -   深圳广电数字科技有限公司（牵头）
    -   汕头融媒集团（即汕头电视台，提供数据和标注）
    -   深圳市智想无界科技有限公司 (封装推广，大概率外包)
    -   北京中科模识科技有限公司（训练模型）
    -   北京语言大学信息科学学院柯登峰团队

    项目时间节点：
    -  2024.05.24 ， 发布第一则推文：[文博会亮点：五方联手潮汕方言语音识别项目 助力地方语言保护与产业发展](https://mp.weixin.qq.com/s/nUjGZrHRQ8ObFSJMNhOo-w)。
    -  2024.09.16 ， 汕头电视台标注团队摆烂，改由汕职院文旅学院 （大专院校）志愿者标注：[潮汕方言实践基地开班！](https://mp.weixin.qq.com/s/M_i__zDDsm8sCWvO1x4bsA)。 
    -  2024.11.24 ，趁世界潮商大会和国际潮团联谊年会在汕头举行，发布半成品炒热度：[潮汕话“语音识别器”来了](https://mp.weixin.qq.com/s/FTfiWC-8IVZQxvt7GhCCMA)。从新闻不甚清晰的特写画面来看，识别效果一般。
    -  2025.02.24 ， 招募金平、龙湖地区的志愿者录制更多数据，[“家己人”的语音识别系统进入优化阶段](https://mp.weixin.qq.com/s/yOwXN5f4fBqZ4osZcaIXeA)

    新闻截图：
        <div align="center">
            <img src="./data/rec_1.jpg" width="900" />
        </div>
        <div align="center">
            <img src="./data/rec_2.jpg" width="900" />
        </div>

    - 2025.09.28 ，宣称已有93.6%的识别准确率，但前提是输入语音内容较为书面，实际口语识别效果折半。 [新闻 | 柯登峰团队获广电AI大赛二等奖，祝贺北语信科](https://mp.weixin.qq.com/s/qYf1QyiDzkuKL-8kmj85hw)


### 非商业产品/作品

- 1、youtube 博主 [Efficient NLP] 用[whisper微调潮州话](https://www.youtube.com/watch?v=JH_78KmP4Zk)，并发布在[huggingface](https://huggingface.co/efficient-nlp/teochew-whisper-medium)。
    
    作者从youtube的潮汕小品视频中，借助字幕切割出35小时左右的数据，对whisper进行微调，效果较差。因为数据集都是自动处理的，非常粗糙，字幕也不能完全反映潮汕话的真实说话内容。

- 2、 微信小程序-潮汕话翻译器
    <div align="center">
        <img src="./data/cs_trs.jpg" width="250" />
    </div>

    <!-- ![image](./data/cs_trs.jpg =600x600) -->
    
    评分2.7。客观说，个人感觉效果比讯飞输入法和youtube博主微调的效果好

- 3、 北京语言大学 - 语音合成系统

[新闻｜科技赋能语言和文化——我校信息科学学院教师柯登峰及其研究团队发布创新研究成果](https://mp.weixin.qq.com/s/0WTkTXHCdZJCIcNfL2sdrA)

[数字人视频链接](https://mpvideo.qpic.cn/0bc3neabwaaaciadrosiy5tva2oddnuqagya.f10002.mp4?dis_k=0ff805d3b96a7b7dbe3846304d41e0f4&dis_t=1742575244&play_scene=10120&auth_info=TcDWvN4RVA92yuuzzjFuGjRFSWFkSjtvNkojNhl2Rw5rbkAeLF8rdQduFBJ3CWI5&auth_key=5f5fc3282cf8cf43598ef41bd27787d1&vid=wxv_3744484224561381377&format_id=10002&support_redirect=0&mmversion=false) 


## 本人的工作

### 数据集

- 首个开源的、野外的、正字标注的潮汕话数据集[teochew_wild](https://huggingface.co/datasets/panlr/teochew_wild)。 

    Teochew-Wild包括12500条音频片段，包含潮州市区、汕头市区、澄海、榕江音、潮安南部等多个区域的口音，声音来自20个发音标准的潮汕母语说话人，他们的身份主要是主持人、播音员、讲古艺人、自媒体博主，因此语料内容即覆盖书面用语，也包含了不少口头用语。Teochew-Wild同时提供正字和拼音标注，是首个公开可用、标注准确率高的潮州话数据集，主要面向语音识别和语音合成任务。
- 后续工作：800+小时的大规模潮汕话无监督数据集。


### 文本处理工具

- [pyPengIm](https://github.com/p1an-lin-jung/teochew-g2p): 首个开源的潮汕话文本处理工具，主要支持`汉字转拼音`、`口音转换`、`多音字消歧`、`普通话转潮汕话`、 `潮州拼音转音素`、`潮州拼音转国际音标`、`单字查询`等功能。是开发[teochew_wild](https://huggingface.co/datasets/panlr/teochew_wild)过程中的附属产品。

- [歹看正字法(PKO)](https://github.com/p1an-lin-jung/teochew-g2p/tree/master/doc/readme.md)：以现有的专家方案和谐音字为基础进行改进，得到的一个潮汕话正字方案，主要设计目的是，尽可能做到`减少多音字`、`解决有音无字问题`、`解决与普通话词义冲突`，最终为 **pyPengIm** 工具服务。


### 潮汕话正字识别-玩具项目
用 teochew_wild 微调 whisper，实现正字的识别（非翻译为普通话），[demo](https://huggingface.co/spaces/panlr/teochew_whisper)和[模型权重](https://huggingface.co/panlr/whisper-finetune-teochew)均上传在huggingface。 目前该微调模型在teochew_wild的验证集、测试集均取得10%左右的CER；不过目前teochew的数据时长不到19个小时，仍然有许多“潮汕土语”没有覆盖，所以实际应用效果也一般。~~当然huggingface space只提供免费GPU，所以推理速度特别慢，并且越来越慢，一开始20秒左右，后来100多秒~~
