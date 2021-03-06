---
title: GitHub Pull Request初体验 | 给Hexo博客留言页面添加评论系统
date: 2015-12-30 20:58:54
categories:
- Tech
tags:
- GitHub
- Chinese
---

今天第一次在GitHub上完成了Pull Request，颇有纪念意义。代码只有区区两行，却是我第一次在GitHub技术社区“改进”了别人的代码库，大言不惭地讲，这微小的正作用将随着时间、用户的增长而传递下去。

*对技术细节无感的读者可酌情阅读下一段落，后面听我讲故事*
昨晚的我正在配置这个博客，观察到[参照博客](https://www.haomwei.com/)有一个留言板，我创建并添加guestbook page作为留言页面后，始终显示不出评论系统。留言板不能留言，那还叫什么留言板呢。阅读了原作者博客上的一些资料后，发现原作者通过在guestbook page的*markdown*文件中直接添加disqus或多说评论系统的*html/javascript*代码后实现的。可我却屡试不成，看其他用户的留言也有相同痛点。再做了一番研究后，发现往往是因为这类主题默认post（文章）显示，而page（页面）不显示评论系统，而这个留言板是按照page来处理的，通过hack相关代码可以搞定。可惜能找到的例子都是用*swig*, *ejs*写的，而我用的主题使用*jade*写的，不知*jade*为何物的我便看得一头雾水.
终于在午夜过后找对了需要改的位置和看懂了大致的手法，只需要在负责生成page的文件加上评论系统的代码，并由每个页面的`page.comments`变量控制即可，这样就能实现about页面不能评论而guestbook页面可以评论。代码如下：
```
  if page.comments
    include _partial/comments
```
此时我意识到，我可以把它放进本来的代码库中，作为我的第一个code change。说干就干，这件事好像就叫Pull Request。初听这个词，我还很confuse的，因为明明我在push代码，怎么能叫pull呢，大概是request owner to pull的意思吧。没走过流程也不怕，应该和我们在公司做CL，submit code一个意思，走完之后果然如此。作为专业的程序员，顺便也update了英文的文档。折腾到凌晨两点之后，还真是有点小激动呢。一觉睡到了上午十点，满心期待打开电脑，发现owner已经merge了我的这个pull request，今天下班后发现owner将中文文档也update了.
至此小功告成。详情见：[我的第一个GitHub Pull Request](https://github.com/tufu9441/maupassant-hexo/pull/32)


*现在开始放松读故事*
这一天其实迟到了五年。
2010年，冬天，大三，第一次听说GitHub这东西，在台大资工系系馆的一场讲座里。作为交换生的我听着和编程生涯有关的经验分享，只听主讲反复提到JitHat（听不清），还说JitHat上如此这般有用。于是我举手问，“您说的JitHat是什么？”于是得听大名，“GitHub"。前排一位女教授还开口说道，“每一个程序员和计算机系的学生都应该知道GitHub。” 于是全场哄笑。讲座结束后的我悄悄打开这个网站，注册了账号，可是仍然看的云里雾里，并且不知道上面提到的repo，pull request，git和github的关系，还有这些搞来搞去是图的什么。
2011年上，大三的我下载了别人分享的Git使用手册的电子书，潦草翻翻作罢。
2011年下，进入微软实习的我需要和Mentor在同一个代码库写代码，出身承德市理科状元的年轻导师问我，你用过svn、git之类的版本控制系统吗。我说，听说过，没用过。
2013年，第一次使用svn，还是和研究生实验室师兄一起做project。
2013年，时隔三年，我才第一次在GitHub创建repo，存放自己参加编程比赛、刷面试题库的代码。
2013年，和几个好友的课程project进驻了GitHub。
2013年，帮一个长得像汤唯的女生做project，姑娘在那一周成功被我convert成GitHub的用户，后来，跟了青年才俊的师兄。
2014年，研究生毕业project放进了GitHub。
2015年6月，用GitHub创建了博客，却迟迟没有真正动笔。
2015年的尾巴，博客重启，第一个阅读并fork别人的代码，Pull Request成就达成。

我很羡慕我所见过的美国学生（含本科留学生）的一点是，他们有着浓厚的技术社区的文化和传统。而国内，或者说我所成长的环境，在这方面却有一段距离值得追赶。
通过技术类社区比如GitHub，Quora，Stackoverflow等，可以分享干货、切磋技艺、结交朋友，大家写博客、做项目、一起写博客、一起做项目，江山如画，一时多少豪杰。

*后记*
记者在加州山景城的Castro Street和Villa Street的路口，采访了一名刚刚完成了第一个pull request的程序员，你现在在想什么。
他会拿起话筒说，“感谢郭嘉，如果明年能够给TensorFlow之类的名库贡献一些solid的代码和feature，听起来还蛮牛的，不错哦。”

[点击这里阅读英文版](2015/12/30/my-first-pull-request-en/)