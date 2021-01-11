# AliPay-F2F-For-WHMCS
基于Alipay即时支付，手机支付，当面付的基于WHMCS的支付网关模块
支持WHMCS 5.x/6.x/7.x
针对 WHMCS 8.x 进行了部分修改，但**请注意 `config_gen.php` 是需要您手动修改配置的！**
因为 WHMCS8.x（我测试的是8.1）引入了数据库内容加密，直接读取数据库的内容读出来的是一串乱码（应该是仅和站点有关，与保存时间无关，怀疑是为了最小化数据泄露可能带来的影响所以引入了加密），您需要手动查询您的数据库记录中`tblpaymentgateways`表的 gateway = alipay_full 且 setting = apitype 项，手动配置`config_gen.php`文件中第27、40、49行的判断条件。
link_gen.php则因为调用时会传入参数，所以直接引入参数即可，无需再读取数据库。
