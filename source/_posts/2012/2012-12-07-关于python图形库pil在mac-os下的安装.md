---
date: 2012-12-07
layout: post
title: 关于python图形库pil在mac os下的安装
categories:
- program
tags: []
published: true
comments: true
---
<p>首先在mac os的环境下根据官方给出的release版本
<a href="http://effbot.org/downloads/Imaging-1.1.7.tar.gz" title="Python Imaging Library 1.1.7 Source Kit ">Python Imaging Library 1.1.7 Source Kit</a> <br />
如果在debian下可以非常简便的就<br />
sudo apt-get install libjpeg62-dev<br />
sudo apt-get install zlib1g-dev<br />
sudo apt-get install libfreetype6-dev<br />
sudo apt-get install liblcms1-dev<br />
然后就 python setup.py install 轻松又愉快<br />
可是mac的说明我有点蒙</p>

<p>--------------------------------------------------------------------<br />
Additional notes for Mac OS X<br />
--------------------------------------------------------------------</p>

<p>On Mac OS X you will usually install additional software such as<br />
libjpeg or freetype with the "fink" tool, and then it ends up in<br />
"/sw".  If you have installed the libraries elsewhere, you may have<br />
to tweak the "setup.py" file before building.</p>

<p>反正我一开始也就理所当然的当成usually install additional software的一份子了、当然结果肯定是残忍的<br />
pil是可以用但是任何的解析基本都会报类似<br />
raise IOError decoder s not available decoder_name IOError decoder jpeg not available的错</p>

<p>google了无数各种做ln连来连去的……<br />
注意一点就是 3一下的版本都在 /System/Library/Frameworks/Python.framework/Versions/下<br />
3以上的版本都在 /Library/Frameworks/Python.framework/Versions<br />
然后site-package<br />
分别在<br />
/Library/Python/2.7/site-packages<br />
/Library/Python/2.3/site-packages<br />
/usr/local/git/lib/python2.7/site-packages<br />
/Library/Python/2.5/site-packages<br />
/Library/Python/2.6/site-packages<br />
/Library/Frameworks/Python.framework/Versions/3.2/lib/python3.2/site-packages<br />
/usr/local/lib/python3.2/site-packages<br />
混乱了吧……记得你装的是哪儿个版本、然后在configure之前要都设置对路径……私认为这绝对是太残忍了……<br />
-----------------------------------分割线--------------------------------------<br />
下面是经过实践出的最简单的方法、就用python自带的easy_install里的pip这样默认都帮你configure完了也不用你纠结了<br />
就这么几句就搞定了<br />
sudo easy_install pip<br />
sudo brew install jpeg<br />
sudo brew install libjpeg<br />
sudo pip uninstall pil<br />
sudo pip install pil</p>

<p>搞定记得顺序、先要装依赖</p>

<p>附上PIL的文档:<br />
http://www.pythonware.com/library/pil/handbook/index.htm</p>
