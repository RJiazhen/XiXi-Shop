<template>
  <li class="">
    <div class="list-wrap">
      <div class="p-img">
        <router-link :to="`/detail/${goodId}`" target="_blank"><img v-lazy="imgSrc" /></router-link>
      </div>
      <div class="price">
        <strong>
          <em>¥&nbsp;</em>
          <i>{{ price }}.00</i>
        </strong>
      </div>
      <div class="attr">
        <router-link :to="`/detail/${goodId}`" target="_blank" :title="title">{{ title }}</router-link>
      </div>
      <div class="commit">
        <i class="command">已有<span>2000</span>人评价</i>
      </div>
      <div class="operate">
        <a class="sui-btn btn-bordered btn-danger" @click="addToCart">加入购物车</a>
        <a href="javascript:void(0);" class="sui-btn btn-bordered">收藏</a>
      </div>
    </div>
  </li>
</template>

<script setup lang="ts">
import { useRouter } from "vue-router"
import { useDetail } from "@/stores/detail"
const router = useRouter()
const detail = useDetail()

const props = defineProps<{
  imgSrc: string,
  title: string,
  price: number,
  goodId: number
}>()

// 点击「加入购物车」按钮
const addToCart = async () => {
  try {
    // 获取商品信息
    await detail.getGoodsInfo(props.goodId)
    // 发出添加进购物车的请求
    await detail.addOrUpdateShopCart(props.goodId.toString(), 1)
    // 将加入购物车的商品信息存储在session中
    sessionStorage.setItem("SKUINFO", JSON.stringify(detail.skuInfo))
    router.push({ name: 'addcartsuccess', query: { skuNum: 1 } })
  } catch (error) {
    console.log(error);
    alert(error.message)
  }
}


</script>

<style scoped lang="scss">
li {
  height: 100%;
  width: 20%;
  margin-top: 10px;
  line-height: 28px;

  .list-wrap {
    .p-img {
      padding-left: 15px;
      width: 215px;
      height: 255px;

      a {
        color: #666;

        img {
          max-width: 100%;
          height: auto;
          vertical-align: middle;
        }
      }
    }

    .price {
      padding-left: 15px;
      font-size: 18px;
      color: #c81623;

      strong {
        font-weight: 700;

        i {
          margin-left: -5px;
        }
      }
    }

    .attr {
      padding-left: 15px;
      width: 85%;
      overflow: hidden;
      margin-bottom: 8px;
      min-height: 38px;
      cursor: pointer;
      line-height: 1.8;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 2;

      a {
        color: #333;
        text-decoration: none;
      }
    }

    .commit {
      padding-left: 15px;
      height: 22px;
      font-size: 13px;
      color: #a7a7a7;

      span {
        font-weight: 700;
        color: #646fb0;
      }
    }

    .operate {
      padding: 12px 15px;

      .sui-btn {
        display: inline-block;
        padding: 2px 14px;
        box-sizing: border-box;
        margin-bottom: 0;
        font-size: 12px;
        line-height: 18px;
        text-align: center;
        vertical-align: middle;
        cursor: pointer;
        border-radius: 0;
        background-color: transparent;
        margin-right: 15px;
      }

      .btn-bordered {
        min-width: 85px;
        background-color: transparent;
        border: 1px solid #8c8c8c;
        color: #8c8c8c;

        &:hover {
          border: 1px solid #666;
          color: #fff !important;
          background-color: #666;
          text-decoration: none;
        }
      }

      .btn-danger {
        border: 1px solid #e1251b;
        color: #e1251b;

        &:hover {
          border: 1px solid #e1251b;
          background-color: #e1251b;
          color: white !important;
          text-decoration: none;
        }
      }
    }
  }
}
</style>
