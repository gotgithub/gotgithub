什么是GitHub
================

GitHub，网址 https://github.com/ ，是一个开源软件项目的托管平台，因为只使用Git作为唯一的版本库格式进行版本库托管，故名GitHub。GitHub的注册用户已经接近百万，托管的版本库数量已超两百万，其中不乏知名的开源项目，如：Ruby on Rails [#]_ ，Hibernate [#]_ ，phpBB [#]_ ，jQuery [#]_ ，Prototype [#]_ ，Homebrew [#]_ 等。

GitHub于2008年4月10日正式发布 [#]_ ，相比于始于1999年的SourceForge [#]_ 和2005年的GoogleCode [#]_ ，GitHub后来者居上，从代码提交数量上看，GitHub已经超越其前辈 [#]_ ，如图1-1所示。

.. figure:: /images/explore-github/survival-of-the-forges.png
   :scale: 100

   图1-1：开源项目托管平台提交数量对照

对于一个开源项目，从开发角度讲大体上分为两类人群，一类称为核心开发团队，他们可以向保存源代码的版本库提交，即对源代码的修改具有最终的决定权。另外一类称为贡献者，他们不是核心团队的成员，虽然也能看到源代码，但是只可读不可写。

采用传统的集中式版本控制系统（如SVN）的开源项目，这两个群体的用户体验都不是太好。如图1-2所示，项目的贡献者（非核心成员）很不“高兴”，因为他们即便有修改代码的能力和渴望，也不能直接向版本库提交，要想成为提交者需要一个很长的建立信任的过程。对于项目的核心开发团队，体验也不是很好，因为凡是涉及到版本库的操作（检入、检出、查看日志等）都需要在联网的状态下运行，网络带宽对用户体验影响相当大。

.. figure:: /images/explore-github/svn-workflow.png
   :scale: 100

   图1-2：使用集中式版本控制系统

Git等分布式版本控制系统的出现，彻底颠覆了原有代码管理的管理模式和组织架构。使用Git，不再需要唯一的、集中式的版本库，而是每个开发者本地都拥有一份完整的版本库克隆。Git并不排斥集中式的使用模式，但更倾向于将集中式模式下的版本库称为共享版本库，核心开发团队的成员可以将自己本地版本库的提交推送到共享版本库上。

使用Git做版本控制，如图1-3所示，核心开发团队非常“高兴”，因为他们和共享版本库之间不必一直保持连接状态，诸如查看日志、提交、创建分支等几乎全部操作都（脱离网络）在本地的版本库中完成。项目贡献者（非核心成员）也不再那么沮丧，因为版本库人人皆可更改（当然是对本地版本库而言）。稍微让贡献者感到困难的就是如何将自己的改动被核心开发团队所了解并接纳。Git提供了多种途径，一个方法是先用 ``git-format-patch`` 命令将本地提交转换为补丁文件或补丁文件序列，再通过邮件发送给核心开发团队。另外一个办法就是搭建一个自己专有的共享版本库，让核心团队的开发者到自己共享的版本库来抓取（Pull）。自己动手搭建Git服务器建立共享版本库是一个难点，在我的
《Git权威指南》一书中花了七个章节来介绍，掌握起来有一定难度。

.. figure:: /images/explore-github/git-workflow.png
   :scale: 100

   图1-3：使用分布式版本控制系统

GitHub的出现极大地改善了开源项目的生态环境，无论项目的核心开发团队，还是普通的项目贡献者都工作得非常“愉快”。项目的创建者只需在GitHub上点击一下鼠标即可创建一个新版本库。普通的项目贡献者在GitHub上先找到自己希望参与的项目，然后只需点击一下鼠标即可在自己的托管空间下创建一个派生的版本库（即项目分支），就好像这个项目原本就是由自己创立的那样。如图1-4所示，当普通的项目贡献者完成开发，可以通过GitHub的Web界面向项目的核心开发团队发送一个拖拽请求（Pull Request），项目的核心团队收到 Pull Request 后审核代码，审核通过后可以直接点击Web界面上的合并按钮完成对贡献者代码的合并。

.. figure:: /images/explore-github/github-workflow.png
   :scale: 100

   图1-4：GitHub的协同模式

----

.. [#] https://github.com/rails/rails
.. [#] https://github.com/hibernate
.. [#] https://github.com/phpbb/phpbb3
.. [#] https://github.com/jquery/jquery
.. [#] https://github.com/sstephenson/prototype
.. [#] https://github.com/mxcl/homebrew
.. [#] https://github.com/blog/40-we-launched
.. [#] http://sourceforge.net/
.. [#] http://code.google.com/
.. [#] http://www.slideshare.net/sogrady/survival-of-the-forges
