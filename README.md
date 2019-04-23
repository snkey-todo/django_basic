# django_rest_tutorial
django basic tutorial for other demos.

## 新建项目music app

[参考](https://github.com/twtrubiks/django-tutorial)


## 自定义错误页面

1. 修改配置文件
  
```
# 使用自带的错误
# DEBUG = True
# ALLOWED_HOSTS = []
# 使用自定义的错误
DEBUG = False
ALLOWED_HOSTS = ['*']
```

2. 新建错误页面page_404.html以及page_500.html。路径：musics/templates/page_404.html、musics/templates/page_500.html

page_404.html文件内容如下，可以自定义

```
error 404，aaaa
```

3. 新建错误view,error_views.py。路径：musics/templates/error_views.py。代码如下：

```python
from django.shortcuts import render

def view_404(request):
    return render(request, 'page_404.html', status=404)

def view_500(request):
    return render(request, 'page_500.html', status=500)
```

4. 在主urls.py中增加如下内容

```python
handler404 = "musics.templates.error_views.view_404"
handler500 = "musics.templates.error_views.view_500"
```

效果图如下：
![image](https://raw.githubusercontent.com/zhusheng/blog/master/django/03.png)


## 说明

1. admin superuser（zhusheng/zhusheng）

