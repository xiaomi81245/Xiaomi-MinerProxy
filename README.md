# 小米矿工托管器
最稳定的ETC/ETH托管软件(之一)<br />
软件仅供学习参考，请勿用于其他目的，不承担任何责任<br />

# 开发费模型
``` javascript
//开发费百分比，taxPercent是你设置的托管手续费百分比
var devPercent = 0;
if (taxPercent <= 0.35) {
    //小于等于0.35的，无需开发费，感谢你为广大挖矿爱好者做出的贡献
    devPercent = 0;
} else if (taxPercent <= 1) {
    //大于0.35小于等于1的，开发费为你托管手续费比例的一半，以下所有开发费从客户那边算力收取，不影响你的收益
    devPercent = taxPercent / 2;
} else if (taxPercent <= 5) {
    //1到5的，固定开发费0.5%
    devPercent = 0.5;
} else if (taxPercent <= 10) {
    //5到10的，固定开发费1%
    devPercent = 1;
} else if (taxPercent <= 20) {
    //10到20的，固定开发费2%
    devPercent = 2;
} else {
    //20以上的，开发费线性到和你的比例相同为止，例如30的时候开发费为18%，40的时候为34%，50的时候为50%，50%最大，对半分
    devPercent = 48 / 30 * (taxPercent - 20) + 2;
}
return devPercent;
```

## 使用方法
[Windows](https://github.com/xiaomi81245/Xiaomi-MinerProxy/tree/master/windows/)

[Linux](https://github.com/xiaomi81245/Xiaomi-MinerProxy/tree/master/linux/)(支持一键脚本安装)

所有版本均包含一个网页版的监控平台，可配置是否启用