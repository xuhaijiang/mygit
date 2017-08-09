## Twig PHP模板语言 [参考外文](http://twig.sensiolabs.org/doc/templates.html)##

Twig [官网](http://twig.sensiolabs.org) 是一个灵活，快速，安全的PHP模板语言。它将模板编译成经过优化的原始PHP代码。Twig拥有一个Sandbox模型来检测不可信的模板代码。Twig由一个灵活的词法分析器和语法分析器组成，可以让开发人员定义自己的标签，过滤器并创建自己的DSL

### 简介 ###

twig 的模板就是普通的文本文件，也不需要特别的扩展名，.html .htm .twig 都可以。模板内的 变量和表达式会在运行的时候被解析替换，标签（tags）会来控制模板的逻辑
下面是个最小型的模板，用来说明一些基础的东西

### 示例模板 [官方文档](http://twig.sensiolabs.org/documentation)###

模版1
   
    <!DOCTYPE html> 
    <html> 
    <head> 
        <title>My Webpage</title> 
    </head> 
    <body> 
        <ul id="navigation"> 
        {% for item in navigation %} 
            <li><a href="{{ item.href }}">{{ item.caption }}</a></li> 
        {% endfor %} 
        </ul> 
 
        <h1>My Webpage</h1> 
        {{ a_variable }} 
    </body> 
    </html>

模版2

    <!DOCTYPE html>
    <html>
    <head>
        <title>My Webpage</title>
    </head>
    <body>
        <ul id="navigation">
        {% for item in navigation %}
            <li><a href="{{ item.href }}">{{ item.caption }}</a></li>
        {% endfor %}
        </ul>

        <h1>My Webpage</h1>
        {{ a_variable }}
    </body>
    </html>

上面模版中包含两种符号**{% ... %}** 和 **{{ ... }}** 

- **{% ... %}：**用来控制的比如for循环
- **{{ ... }}：**用来输出变量和表达式的

### ide 支持 ###

- Twig Plugin 2.0.0 Eclipse plugindy

无需猜测您的 [语法](http://markdownpad.com) 是否正确；每当您敲击键盘，实时预览功能都会立刻准确呈现出文档的显示效果。

### 语法 ###

#### 注释 ####
    {# ... #}

#### 变量 ####

- 普通变量
    - `{{ hello }}`
- 对象变量,使用 **.** 
    - `{{ foo.bar }}`
- 数组变量,使用下标 **[]** 
    - `{{ foo['bar'] }}`
- 变量赋值
    - `{% set foo = 'foo' %}`
    - `{% set foo = [1,2] %}`
    - `{% set foo = {'foo':'bar'}%}`

#### 全局变量 ####

- **\_self :** macro标签
- **\_context :** 当前环境
- **\_charset :** 字符编码

#### 过滤器 ####

- `{{ name|striptags|title}}`
    - **striptags:**去除html标签
    - **title:**每个单词的首字母大写
-  代码块中使用
    -  `{% filter upper %} This text becomes uppercase {% endfilter %}`

#### 函数 ####
   
内置函数示例

    {% for i in range(0, 3) %}
    {{ i }},
    {% endfor %}

#### 截入模版 ####

    {% include 'sidebar.html' %}  

#### 模版继承 ####
先定义一个基本骨骼页base.html 他包含许多block块，这些都可以被子模板覆盖

base.html
    
    <!DOCTYPE html> 
    <html> 
    <head> 
        {% block head %} 
            <link rel="stylesheet" href="style.css" /> 
            <title>{% block title %}{% endblock %} - My Webpage</title> 
        {% endblock %} 
    </head> 
    <body> 
        <div id="content">{% block content %}{% endblock %}</div> 
        <div id="footer"> 
            {% block footer %} 
                © Copyright 2011 by <a href="http://domain.invalid/">you</a>. 
            {% endblock %} 
        </div> 
    </body> 
    </html>

我们定义了4个block块，分别是 block head, block title, block content, block footer

*注意*

1. block是可以嵌套的。
2. block可以设置默认值（中间包围的内容），如果子模板里没有覆盖，那就直接显示默认值。比如block footer ，大部分页面你不需要修改（省力），但你需要到时候仍可以方便到修改（灵活）下面我看下子模板应该怎么定义。

sub.html

    {% extends "base.html" %}
    {% block title %}
	   Index
    {% endblock %}
    {% block head %}
        {{ parent() }}
        <style type="text/css">
            .important { color: #336699; }
        </style> 
    {% endblock %}
    {% block content %}
        <h1>Index</h1>
        <p class="important">
            Welcome on my awesome homepage.
        </p>
    {% endblock %}
    
*注意 {% extends "base.html" %} 必须是第一个标签。其中 block footer就没有定义，所以显示父模板中设置的默认值
如果你需要增加一个block的内容，而不是全覆盖，你可以使用 parent函数*

#### macros宏 ####

宏有点类似于函数，常用于输出一些html标签。
这里有个简单示例，定义了一个输出input标签的宏

    {% macro input(name, value, type, size) %} 
        <input type="{{ type|default('text') }}" name="{{ name }}" value="{{ value|e }}" size="{{ size|default(20) }}" /> 
    {% endmacro %}
宏导入使用

    {% import "forms.html" as forms %} 
    <p>{{ forms.input('username') }}</p>

部分宏导入使用，语法 **{% from 'macroDir' import tagName as alias%}**

    {% from 'forms.html' import input as input_field, textarea %}
    <dl> 
        <dt>Username</dt> 
        <dd>{{ input_field('username') }}</dd> 
        <dt>Password</dt> 
        <dd>{{ input_field('password', type='password') }}</dd> 
    </dl> 
    <p>{{ textarea('comment') }}</p>

 
   

