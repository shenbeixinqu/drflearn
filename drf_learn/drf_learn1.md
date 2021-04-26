### 创建项目

```shell
django-admin startproject apiproject
cd  apiproject
# 创建app
python manage.py startapp blog
将新建的blogapp和rest_framework添加到INSTALLED_APPS,编辑apiproject/settings.py文件
```

![](G:\drf_learn\drf_learn\drf_image\0001.png)

### ugettext和ugettext_lazy对比

```shell
django封装了很多api,如翻译的ugettext和ugettext_lazy,都在django.utils.translations,
我们只需要 
from django.utils.translations import ugettext as _
fron django.utils.translation import ugettext_lazy as _
ugettext：预加载的时候调度的翻译方法
ugettext_lazy：请求执行的时候调度的翻译方法
--- 推荐方法在一下模块中使用
	ugettext:
	   models.py
        apps.py
        forms.py
        settings.py
        等其他不需要请求执行, 而是在启动执行的模块中
     ugettext_lazy
        views.py
        函数封装的.py文件
        等其他需要请求一次就需要执行一次的模块中
```

