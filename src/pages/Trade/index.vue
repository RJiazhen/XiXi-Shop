<template>
  <div class="trade-container">
    <div class="title">
      <h1>填写并核对订单信息</h1>
    </div>
    <div class="content">
      <!-- 收件人信息 -->
      <div class="receive">
        <h5>收件人信息</h5>
        <div class="address clearFix">
          <span class="select-btn selected">张三</span>
          <p>
            <span class="s1">北京市昌平区宏福科技园综合楼6层</span>
            <span class="s2">15010658793</span>
            <span class="s3">默认地址</span>
          </p>
        </div>
        <div class="address clearFix">
          <span class=" select-btn selected">李四</span>
          <p>
            <span class="s1">北京市昌平区宏福科技园综合楼6层</span>
            <span class="s2">13590909098</span>
            <span class="s3">默认地址</span>
          </p>
        </div>
        <div class="address clearFix">
          <span class="select-btn selected">王五</span>
          <p>
            <span class="s1">北京市昌平区宏福科技园综合楼6层</span>
            <span class="s2">18012340987</span>
            <span class="s3">默认地址</span>
          </p>
        </div>
      </div>
      <div class="line"></div>

      <!-- 支付方式 -->
      <div class="pay">
        <h5>支付方式</h5>
        <div class="address clearFix">
          <span class="select-btn selected">在线支付</span>
          <span class="select-btn" style="margin-left:5px;">货到付款</span>
        </div>
      </div>

      <div class="line"></div>
      <!-- 送货清单 -->
      <div class="sku-list">
        <h5>送货清单</h5>
        <div class="way">
          <h5>配送方式</h5>
          <div class="info clearFix">
            <span class="s1">天天快递</span>
            <p>配送时间：预计8月10日（周三）09:00-15:00送达</p>
          </div>
        </div>
        <div class="detail">
          <h5>商品清单</h5>
          <ul class="list clearFix">
            <li>
              <img src="./images/goods.png" alt="">
            </li>
            <li>
              <p>
                Apple iPhone 6s (A1700) 64G 玫瑰金色 移动联通电信4G手机硅胶透明防摔软壳 本色系列</p>
              <h4>7天无理由退货</h4>
            </li>
            <li>
              <h3>￥5399.00</h3>
            </li>
            <li>X1</li>
            <li>有货</li>
          </ul>
          <ul class="list clearFix">
            <li>
              <img src="./images/goods.png" alt="">
            </li>
            <li>
              <p>
                Apple iPhone 6s (A1700) 64G 玫瑰金色 移动联通电信4G手机硅胶透明防摔软壳 本色系列</p>
              <h4>7天无理由退货</h4>
            </li>
            <li>
              <h3>￥5399.00</h3>
            </li>
            <li>X1</li>
            <li>有货</li>
          </ul>
        </div>
      </div>
      <div class="bbs">
        <h5>买家留言：</h5>
        <textarea placeholder="  建议留言前先与商家沟通确认" class="remarks-cont"></textarea>

      </div>
      <div class="line"></div>
      <div class="bill">
        <h5>发票信息：</h5>
        <div>普通发票（电子） 个人 明细</div>
        <h5>使用优惠/抵用</h5>
      </div>
    </div>
    <div class="money clearFix">
      <ul>
        <li>
          <b><i>1</i>件商品，总商品金额</b>
          <span>¥5399.00</span>
        </li>
        <li>
          <b>返现：</b>
          <span>0.00</span>
        </li>
        <li>
          <b>运费：</b>
          <span>0.00</span>
        </li>
      </ul>
    </div>
    <div class="trade">
      <div class="price">应付金额:　<span>¥5399.00</span></div>
      <div class="receiveInfo">
        寄送至:
        <span>北京市昌平区宏福科技园综合楼6层</span>
        收货人：<span>张三</span>
        <span>15010658793</span>
      </div>
    </div>
    <div class="sub clearFix">
      <a href="##" class="subBtn">提交订单</a>

    </div>
  </div>
</template>

<script setup lang="ts">

</script>

<style scoped lang="scss">
.trade-container {
  display: flex;
  flex-direction: column;
  align-items: center;

  .title {
    width: 1000px;
    margin: 0 auto;
    font-size: 14px;
    line-height: 21px;
    text-align: left;
  }

  .content {
    width: 1000px;
    margin: 10px auto 0;
    border: 1px solid rgb(221, 221, 221);
    padding: 10px 25px;
    box-sizing: border-box;
    text-align: left;

    // 各部分标题
    .receive,
    .pay,
    .list,
    .sku-list {
      width: 900px;

      h5 {
        line-height: 36px;
        margin-top: 5px;
      }
    }

    // 收件人信息
    .address {
      padding-left: 20px;
      margin-bottom: 15px;

      .select-btn {
        float: left;
        width: 100px;
        height: 30px;
        line-height: 30px;
        text-align: center;
        border: 1px solid #ddd;
        position: relative;
      }

      .select-btn::after {
        content: "";
        display: none;
        width: 13px;
        height: 13px;
        position: absolute;
        right: 0;
        bottom: 0;
        background: url(../images/choosed.png) no-repeat;
      }

      .select-btn.selected {
        border-color: #e1251b;
      }

      .select-btn.selected::after {
        display: block;
      }

      p {
        width: 610px;
        float: left;
        line-height: 30px;
        margin-left: 10px;
        padding-left: 5px;
        cursor: pointer;

        .s1 {
          float: left;

        }

        .s2 {
          float: left;
          margin: 0 5px;
        }

        .s3 {
          float: left;
          width: 56px;
          height: 24px;
          line-height: 24px;
          margin-left: 10px;
          background-color: #878787;
          color: #fff;
          margin-top: 3px;
          text-align: center;
        }
      }

      p:hover {
        background-color: #ddd;
      }
    }

    // 分割线
    .line {
      height: 1px;
      background-color: #ddd;
    }

    // 送货清单
    .sku-list {

      // 配送方式
      .way {
        height: 110px;
        padding-left: 15px;

        h5 {
          margin-top: 0;
        }

        .info {
          margin-top: 10px;

          .s1 {
            float: left;
            border: 1px solid #ddd;
            width: 120px;
            height: 30px;
            line-height: 30px;
            text-align: center;
            margin-right: 10px;
          }

          p {
            line-height: 30px;
          }
        }
      }

      // 商品清单
      .detail {
        background: #feedef;
        padding:0 15px;
        margin: 2px auto 0;

        h5 {
          line-height: 50px;
        }

        .list {
          display: flex;
          justify-content: space-between;

          li {
            line-height: 30px;

            p {

              margin-bottom: 20px;
            }

            h4 {
              color: #c81623;
              font-weight: 400;
            }

            h3 {

              color: #e12228;
            }
          }
        }
      }
    }

    // 买家留言
    .bbs {
      margin-bottom: 15px;

      h5 {
        line-height: 50px;
      }

      textarea {
        width: 100%;
        border-color: #e4e2e2;
        line-height: 1.8;
        outline: none;
        resize: none;
      }
    }

    .bill {
      h5 {
        line-height: 50px;
      }

      div {
        padding-left: 15px;
      }
    }
  }

  .money {
    width: 1000px;
    margin: 20px auto;

    ul {
      width: 220px;
      float: right;

      li {
        line-height: 30px;
        display: flex;
        justify-content: space-between;

        i {
          color: red;
        }
      }
    }
  }

  .trade {
    box-sizing: border-box;
    width: 1000px;
    padding: 10px;
    margin: 10px auto;
    text-align: right;
    background-color: #f4f4f4;
    border: 1px solid #ddd;

    div {
      line-height: 30px;
    }

    .price span {
      color: #e12228;
      font-weight: 700;
      font-size: 14px;
    }

    .receiveInfo {
      color: #999;
    }
  }

  .sub {
    width: 1000px;
    margin: 0 auto 10px;

    .subBtn {
      float: right;
      width: 164px;
      height: 56px;
      font: 700 18px "微软雅黑";
      line-height: 56px;
      text-align: center;
      color: #fff;
      background-color: #e1251b;
    }
  }
}
</style>