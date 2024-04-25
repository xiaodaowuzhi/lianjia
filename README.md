# 链家二手房成交数据

鉴于链家倾向于不展示成交价格，但是成交数据那里其实是有自定义价格查询的，所以写了一个脚本爬取上海二手房成交价格数据

主要是要抓取链家的cookie，Firefox F12 network自行抓取
cookie='select_city=310000; lianjia_ssid=xxxxx'

headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.0.0 Safari/537.36 Edg/123.0.0.0',
    'Cookie': cookie.encode("utf-8").decode("latin1")
}

还有一个潜在的问题就是通过这样的筛选，可能存在成交的套数超过3000套，这个时候页面只有3000套的数据，可以自行添加筛选条件
<https://sh.lianjia.com/chengjiao/pudong/bp100ep101>是浦东新区[100，101)的成交价格链接
