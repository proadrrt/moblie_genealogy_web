<template>
  <div class="count">
    <div class="cpf">
      <h2>公益基金</h2>
      <span>总金额</span>
      <img src="@/assets/images/solid.png" alt>

      <div class="cpfBottom">
        <span class="bottomRight">￥{{fund.remain}}</span>
        <span class="sss">捐助</span>
      </div>
    </div>
    <!-- <div class="flgure">
      <div class="flgureText">
        <h5>刚刚捐款完亲</h5>
        <div class="textLeft">
          <router-link to="/personnel" tag="span">共158人</router-link>
          <van-icon name="arrow"/>
          <van-icon name="arrow"/>
        </div>
      </div>
      <ul class="flgureUl">
        <li v-for="item in celebrity" :key="item.id">
          <div class="div1 portrait" :style="api.imgBG(item.allUserLogin.picSrc)"></div>
          <h5>{{item.allUserLogin.nickName}}</h5>
          <span>捐助 {{item.allUserLogin.role}}元</span>
          <div class="bunText">
            <span>+关注</span>
            <img src="@/assets/images/praise.png" alt>
            <span>{{item.allUserLogin.status}}</span>
          </div>
        </li>
      </ul>
    </div> -->
    <div class="deal">
      <h3>交易明细</h3>
      <div class="money" v-for="item in flow" :key="item.id">
        <div class="running">
          <div class="runningleft">
            <h6>10.01</h6>
            <span>
              <a href="#"></a>
              {{item.useFor}}
            </span>
          </div>
          <span class="ring">+{{item.amount}}</span>
        </div>
        <span class="time">2018</span>
      </div>
    </div>
    <!-- <div class="titleBox">
      <div class="title">
        <span>支出明细</span>
        <h5>{{flow.length ? flow[1].newsTitle : ''}}</h5>
      </div>
      <p>{{flow.length ? flow[1].newsText : ''}}</p>
      <div class="titleBtm">
        <span>{{flow.length ? flow[1].status : ''}}条评论</span>
        <span>{{flow.length ? flow[1].visitNum : ''}}浏览</span>
        <span>刚刚</span>
      </div>
    </div>-->
    <!-- <div class="list" v-for="item in this.$store.state.wasteBook.records" :key="item.id">
      <div class="title">
        <span>支出明细</span>
        <h5>{{item.newsTitle}}</h5>
      </div>
      <div class="titleBtm">
        <span>{{item.status}}条评论</span>
        <span>{{item.visitNum}}浏览</span>
        <span>刚刚</span>
      </div>
    </div>-->
  </div>
</template>

<script>
export default {
  props: {},
  data() {
    return {
      celebrity: [], // 捐款名人
      flow: [], // 交易明细
      fund: [] // 总金额
    };
  },
  computed: {},
  created() {
    this.$store.dispatch("account");
    this.count();
  },
  mounted() {},
  watch: {},
  methods: {
    count() {
      let stairAsk = this.$store.state.apiList;
      this.api
        .get(
          this.api.county.base +
            stairAsk.index_architecture_pay_in_person_1.apiUrl
        )
        .then(res => {
          if (res.code == 200) {
            this.celebrity = res.data.records;
          }
          return this.api.get(
            this.api.county.base + stairAsk.index_fund_1.apiUrl
          );
        })
        .then(res => {
          if (res.code == 200) {
            // 公益基金
            this.fund = res.data;
            return this.api.get(
            this.api.county.base + stairAsk.index_charity_pay_out.apiUrl
          );
          }
        })
        .then(res => {
          if(res.code == 200){
            this.flow = res.data.records
          }
           return this.api.get(
            this.api.county.base + stairAsk.index_architecture_pay_in.apiUrl
          )
        })
        .then(res => {
          if(res.code == 200){
            console.log(res)
          }
        })

      // 捐款名人
      //   this.celebrity = this.$store.state.celebrity;
      // console.log(this.$store.state.wasteBook)
    }
  },
  components: {}
};
</script>

<style scoped lang="less">
.count {
  padding-top: 4.2rem;
  margin-bottom: 1.2rem;
  font-size: 0.24rem;
  overflow: hidden;
  overflow-y: auto;
  overflow-x: hidden;
  .cpf {
    width: 7.1rem;
    height: 2.5rem;
    border-radius: 0.2rem;
    background-size: cover;
    background-image: url(../../assets/images/cpf.png);
    background-repeat: no-repeat;
    background-position: center;
    position: relative;
    padding: 0.4rem 0.7rem 0;
    box-sizing: border-box;
    color: #fff;
    text-align: left;
    margin-left: 0.2rem;
    h2 {
      font-size: 0.32rem;
      margin: 0;
    }
    span {
      font-size: 0.22rem;
    }
    img {
      width: 0.9rem;
      height: 0.9rem;
      position: absolute;
      right: 0.72rem;
      top: 0.52rem;
    }
    .cpfBottom {
      margin-top: 0.2rem;
      .bottomRight {
        font-size: 0.45rem;
      }
      .sss {
        position: absolute;
        right: 0.96rem;
        bottom: 0.52rem;
      }
    }
  }
  .flgure {
    height: 3.8rem;
    width: 100%;
    padding: 0 0.2rem;
    box-sizing: border-box;
    margin-top: 0.55rem;
    .flgureText {
      display: flex;
      position: relative;
      h5 {
        font-size: 0.32rem;
        margin: 0;
      }
      .textLeft {
        position: absolute;
        right: 0;
        top: 0.03rem;
        span {
          color: #ccc;
          margin-right: 0.2rem;
          letter-spacing: 1px;
        }
        /deep/.van-icon {
          color: #767676;
          margin-left: -0.22rem;
        }
      }
    }
    .flgureUl {
      margin-top: 0.4rem;
      display: flex;
      li {
        width: 33.33%;
        height: 3.1rem;
        margin-right: 0.1rem;
        text-align: center;
        padding-top: 0.25rem;
        color: #767676;
        box-sizing: border-box;
        box-shadow: 0px 0px 1px rgba(0, 0, 0, 0.4);
        .portrait {
          width: 1rem;
          height: 1rem;
          border-radius: 50%;
          vertical-align: top;
          background: no-repeat center / cover;
          margin-left: 0.6rem;
        }
        h5 {
          margin: 0.2rem 0 0.3rem 0;
          font-size: 0.26rem;
          color: #333333;
        }
        .bunText {
          margin-top: 0.05rem;
          img {
            width: 0.31rem;
            height: 0.31rem;
            margin: 0.1rem 0.01rem -0.03rem 0.3rem;
          }
        }
      }
      li:nth-child(3) {
        margin-right: 0;
      }
    }
  }
  .deal {
    // padding: 0 0.2rem;
    margin-top: 0.5rem;
    h3 {
      font-size: 0.34rem;
      padding-left: 0.2rem;
      margin: 0.4rem 0 0.45rem 0;
    }
    .money {
      width: 100%;
      height: 0.85rem;
      padding: 0 0.2rem 0 0.2rem;
      box-sizing: border-box;
      margin-bottom: 0.29rem;
      border-bottom: 0.01rem solid #ccc;
      .running {
        display: flex;
        font-weight: 600;
        justify-content: space-between;

        span:nth-child(2) {
          justify-content: flex-start;
        }
        .runningleft {
          width: 3.5rem;
          display: flex;
          justify-content: space-between;
          h6 {
            margin: 0;
            font-size: 0.24rem;
          }
          span {
            font-size: 0.26rem;
            a {
              display: inline-block;
              width: 0.1rem;
              height: 0.1rem;
              background: #d2211b;
              border-radius: 50%;
              position: relative;
              top: -0.05rem;
            }
          }
        }
        .ring {
          color: #d2211b;
          font-size: 0.22rem;
        }
      }
      .time {
        color: #767676;
        font-size: 0.16rem;
      }
    }
  }
  .titleBox {
    padding: 0 0.2rem 0.26rem;
    margin-bottom: 0.27rem;
    border-bottom: 0.01rem solid #dedddd;
    box-sizing: border-box;
    p {
      color: #767676;
      font-size: 0.24rem;
    }
    .titleBtm {
      color: #767676;
      font-size: 0.2rem;
    }
  }
  .list {
    height: 1.1rem;
    padding: 0 0.2rem;
    box-sizing: border-box;
    margin-bottom: 0.27rem;
    border-bottom: 0.01rem solid #dedddd;
  }
  //  抽离title部位样式
  .title {
    display: flex;
    span {
      display: inline-block;
      width: 1.2rem;
      height: 0.42rem;
      color: white;
      text-align: center;
      line-height: 0.42rem;
      font-size: 0.23rem;
      border-radius: 0.05rem;
      margin-right: 0.15rem;
      background-color: #d2211b;
    }
    h5 {
      margin: 0;
      display: inline;
      font-size: 0.3rem;
      color: #333333;
    }
  }
  .titleBtm {
    color: #767676;
    font-size: 0.2rem;
    margin-top: 0.23rem;
  }
}
</style>
