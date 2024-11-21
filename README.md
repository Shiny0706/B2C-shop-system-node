# 福克商城单店版
近日工作上的事情比较繁忙，没有及时开发

##更新计划
1.使用MySQL 5.7的 JSON特性
2.优化满减功能
3.加入团购功能

##历史由来：
福克客城起源于一家在线运营的电商B2B2C平台，后因商务原因，该平台停止运营，开发人员将商城大量修改优化，造就了福克B2C单店商城。原福克商城使用Java开发，在实际的运营中，由于初创公司业务变更比较频繁，我们渐渐的从Java转到了Node.JS，起到了很好的效果，对于业务变更响应更加及时，稳定性也足以经受日UV 50万，日成交订单7万单的考验。所以福克商城使用Node.JS做为开发语言。

##技术选型：
服务端语言Node.JS，数据库MySQL

Node.JS对于电商项目中的团购，秒杀等促销活动所带来的大流量，高并发有足够优秀的表现，具体可参考天猫在双11中Node.JS的表现，同时节省了服务器费用。我们有理由相信Node.JS是可以用来做电商项目的服务端语言的。

MySQL是具备强事务，强一致性能力的关系型数据库。我们没有选用MongoDB做为我们的电商数据库，主要考虑是MongoDB的强一致性能力并不足以达到电商项目的要求，如电商中的异常订单（退货，换货），秒杀活动，都需要对库存做到及时的管理，同时还要处理用户的数据，这时一致性的要求，就足以让我们放弃MongoDB


##代码结构及部署要求：
项目代码分为两端：业务端及后台管理系统。分别是项目根目录下的front和server目录，需要独立部署。简单来说，要完整的使用福克商城，必须最少有两个web服务。这是保障业务稳定的需要，如果需要，使用者可以将两端代码合一，但不推荐

项目使用Node.JS+MySQL开发，对服务器的硬件要求并不高，我们在运营中，主要使用Linux服务器，但经过测试，项目在Windows下也可以稳定工作。
bbxvip_b2c.sql文件为数据库sql脚本
先安装MySQL,并配置帐号密码，修改项目中的dbconfig.js文件，项目中包含dbconfig.js和dbconfig_dev.js分别为开发和生产环境的数据库配置文件，在项目启动后，请使用生产环境配置
在pm2中，加入
>--env production

##主要功能：
1.商城系统品信息展示，用户在线支付下单，促销活动，物流查询
2.用户：用户个人信息展示、编辑，收货地址，订单，售后管理。
3.超级管理员：用户管理，订单及售后管理，商城页面管理，商品管理（支持多SKU）。
4.其它功能：系统日志，定时任务。


##开发计划（RoadMap）：
1.物流快递查询：可以查询订单的快递详细信息及收货状态
2.促销活动：满减功能，满赠功能，秒杀功能，一元购功能
3.二级分销：二级分销功能，可结算，可管理分销商
4.售后功能：用户可对异常订单（退货，换货）进行处理，上传照片及描述，可以申请退换货，并在后台处理完成后，自动退款或退货
5.结算功能：以月或周为指定周期，统计商城销售成本及利润
6.优惠券（积分券）功能：可以设定商品的积分规则，在用户下单后返还积分，同时积分可以抵扣部分购物现金
7.多端：开发PC端及安卓,IOS端（目前只支持移动网页端）

##联系方式
QQ:6365151
G-MAIL:SuperDev9676@gmail.com
