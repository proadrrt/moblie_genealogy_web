<template>
    <div class="introduction">
        <!-- 头部固定导航 -->
        <header>
            <van-icon name="arrow-left" @click="go" />
            <h2>人物介绍</h2>
            <img src="@/assets/images/share.png" alt="">
        </header>
        <!-- 背景 -->
        <div class="bgc"></div>
        <!-- 人物 -->
        <div class="figure">
            <div class="Img"></div>
            <div>
                <h2>{{charityHelping.applyName}}</h2>
                <span>粉丝： {{charityHelping.status}}</span>
                <span>文章： 253</span>
            </div>
            <div class="gz">+关注</div>
        </div>
        <!-- 文章内容 -->
        <div class="article">
            <div class="articleConter">
                <h2>{{charityHelping.title}}</h2>
                <p>萨芬电风扇发的上到发大师傅答复撒萨芬等等撒放十大发多少发放多少发放速度发斯蒂芬发送到</p>
                <div class="picture"></div>
                <p>{{charityHelping.pictureAddress}}</p>                
            </div>
            <!-- 帮扶 -->
            <div class="audit">
                <div class="auditTop">
                    <div class="title">
                        <h3>申请帮扶基金</h3>
                        <h2>经办人： 周星</h2>
                    </div>
                    <div class="money">
                        <b>￥ {{charityHelping.applyMoney}}</b>
                        <div>
                            <van-icon name="passed" />
                            <span>审批通过</span>
                        </div>
                    </div>
                </div>
                 <h6>审批流程</h6>
                 <div v-for="item in flow" :key="item.id" class="audit-list" >
                     <div class="list-top">
                         <div class="state"></div>
                         <h4>申请人意见</h4>
                     </div>
                     <div class="statement">
                         <div class="Img"></div>
                         <div class="conter">
                             <div>{{item.applyName}} <span> [会长]</span></div>
                             <p>{{item.pictureAddress}}</p>
                         </div>
                     </div>
                 </div>
                 <!-- <div class="audit-list">
                     <div class="list-top">
                         <div class="state"></div>
                         <h4>申请人意见</h4>
                     </div>
                     <div class="statement">
                         <div class="Img"></div>
                         <div class="conter">
                             <div>张顺德 <span> [会长]</span></div>
                             <p>同意帮扶！同意帮扶！同意帮扶！同意帮扶！同意帮扶！</p>
                         </div>
                     </div>
                 </div>
                  <div class="audit-list">
                     <div class="list-top">
                         <div class="state"></div>
                         <h4>申请人意见</h4>
                     </div>
                     <div class="statement">
                         <div class="Img"></div>
                         <div class="conter">
                             <div>张顺德 <span> [会长]</span></div>
                             <p>同意帮扶！同意帮扶！同意帮扶！同意帮扶！同意帮扶！</p>
                         </div>
                     </div>
                 </div> -->
                  <div class="list-state audit-list">
                     <div class="list-top">
                         <h5>帮扶情况</h5>
                     </div>
                     <div class="statement">
                         <div class="Img"></div>
                         <div class="conter">
                             <div>张顺德 <span> [会长]</span></div>
                             <p>同意帮扶！同意帮扶！同意帮扶！同意帮扶！同意帮扶！</p>
                         </div>
                     </div>
                     <div class="state-Img">
                         <div></div>
                         <div></div>
                     </div>
                 </div>
            </div>

            <div class="still">
                <img src="@/assets/images/reward.png" alt="">
                <h2>相关推荐</h2>
            </div>
            <dir class="List">
                <h5>家谱内容要素主要包括什么，有什么标准</h5>
                <span>崇阳联谊会官网</span>
                <div class="listImg"></div>
            </dir>
            <dir class="List">
                <h5>家谱内容要素主要包括什么，有什么标准</h5>
                <span>崇阳联谊会官网</span>
                <div class="listImg"></div>
            </dir>
            <dir class="List">
                <h5>家谱内容要素主要包括什么，有什么标准</h5>
                <span>崇阳联谊会官网</span>
                <div class="listImg"></div>
            </dir>
                <!-- 评论 -->
            <div class="comment">
                <img class="zi" src="@/assets/images/reward.png" alt="">
                <h5>评论</h5>
                <ul class="commentList">
                    <li>
                        <div class="Img"></div>
                        <div class="listConter">
                            <h6>周星</h6>
                            <p>家谱是记载一个家族的世系繁衍及重要人物的事迹书</p>
                        </div>
                        <!-- 赞 -->
                        <div class="zan">
                            <img src="@/assets/images/praise.png" alt="">
                            <span>12</span>
                        </div>
                    </li>
                    <li>
                        <div class="Img"></div>
                        <div class="listConter">
                            <h6>周星</h6>
                            <p>家谱是记载一个家族的世系繁衍及重要人物的事迹书</p>
                        </div>
                        <!-- 赞 -->
                        <div class="zan">
                            <img src="@/assets/images/praise.png" alt="">
                            <span>12</span>
                        </div>
                    </li>
                    <li>
                        <div class="Img"></div>
                        <div class="listConter">
                            <h6>周星</h6>
                            <p>家谱是记载一个家族的世系繁衍及重要人物的事迹书</p>
                        </div>
                        <!-- 赞 -->
                        <div class="zan">
                            <img src="@/assets/images/praise.png" alt="">
                            <span>12</span>
                        </div>
                    </li>
                    <li>
                        <div class="Img"></div>
                        <div class="listConter">
                            <h6>周星</h6>
                            <p>家谱是记载一个家族的世系繁衍及重要人物的事迹书</p>
                        </div>
                        <!-- 赞 -->
                        <div class="zan">
                            <img src="@/assets/images/praise.png" alt="">
                            <span>12</span>
                        </div>
                    </li>
                </ul>
            </div>
        </div>

        <!-- 底部评论 -->
        <div class="observer">
            <input type="text" placeholder="我来说两句...">
            <img class="pen" src="@/assets/images/pen.png" alt="">
            <img class="shang" src="@/assets/images/shang.png" alt="">
            <img class="share" src="@/assets/images/share.png" alt="">
        </div>
    </div>
</template>

<script>
export default {
    props: {

    },
    data() {
        return {
            charityHelping: [],
            flow:[] // 申请流程
        };
    },
    computed: {

    },
    created() {

    },
    mounted() {
        this.banfu()
    },
    watch: {

    },
    methods: {
        go() {
            this.$router.go(-1)
        },
        banfu() {
            this.api.get(this.api.county.base + 'genogram/fanSysCharitableDeclare/getFamilyStructureDetails?id=3')
            .then( res => {
                this.charityHelping = res.data
                // console.log(res)
                return this.api.get(this.api.county.base + '/genogram/fanSysCharitableDeclare/getSysCharitableDeclare?pageNo=1&pageSize=6')
            })
            .then( res => {
                this.flow = res.data.records
                console.log(res)
            })
        }

    },
    components: {

    },
};
</script>

<style scoped lang="less">
.introduction {
    font-size: 0.32rem;
    overflow: hidden;
    overflow-y: auto;
    overflow-x: hidden;
    position: relative;
    padding: 1.5rem 0rem 1rem 0;
        // 头部固定
        header {
            font-size: 0.32rem;
            padding: 0.25rem 0.2rem;
            display: flex;
            width: 100%;
            box-sizing: border-box;
            justify-content: space-between;
            align-items: center;
            z-index: 999;
            position: fixed;
            top: 0;
            left: 0;
            color: #fff;
                h2 {
                    margin: 0;
                }
                img {
                    width: 0.46rem;
                    height: 0.45rem;
                }
                /deep/ .van-icon  {
                    font-size: 0.32rem;
                    color: #000000;
                }
        }
        // 底部固定
        .observer {
            position: fixed;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 1rem;
            z-index: 999;
            padding: 0.13rem 0.2rem;
            background-color: #fff;
            border-top: 0.01rem solid #D0CFCF;
            box-sizing: border-box;
                input {
                    outline:none;
                    color: #666666;
                    width: 5.78rem;
                    height: 0.7rem;
                    border-radius: 0.3rem;
                    border: 0.01rem solid #D0CFCF;
                    font-size: 0.26rem;
                    padding-left: 0.8rem;
                    box-sizing: border-box;
                }
                .pen {
                    widows: 0.43rem;
                    height: 0.37rem;
                    position: absolute;
                    left: 0.38rem;
                    top: 0.3rem;
                }
                .shang {
                    width: 0.51rem;
                    height: 0.51rem;
                    position: absolute;
                    right: 0.85rem;
                    top: 0.25rem;
                }
                .share {
                    width: 0.46rem;
                    height: 0.45rem;
                    position: absolute;
                    right: 0.2rem;
                    top: 0.25rem;
                }
        }
        // 红色背景
        .bgc {
            position: fixed;
            top: 0;
            width: 100%;
            height: 2.5rem;
            background-color: #D2211B;
            z-index: 2;
        }
        /deep/.van-icon-arrow-left::before {
            color: #fff;
        }
        .figure {
            height: 1.95rem;
            width: 7.1rem;
            background-color: #fff;
            border-radius: 0.1rem;
            position: fixed;
            top: 1.5rem;
            margin-left: 0.2rem;
            box-shadow: 0 0 0.25rem #ccc;
            display: flex;
            z-index: 3;
                .Img {
                    margin: 0.45rem 0 0 0.32rem;
                    width: 1rem;
                    height: 1rem;
                    background-color: pink;
                    border-radius: 50%;
                }
                :nth-child(2) {
                    margin: 0.6rem 0 0 0.17rem;
                        h2 {
                            font-size: 0.28rem;
                            margin:  0;
                        }
                        span {
                            font-size: 0.22rem;
                            color: #999999;
                            margin: 0 0.35rem 0 0;
                        }
                }
                .gz {
                    width: 1.7rem;
                    height: 0.55rem;
                    border-radius: 0.3rem;
                    font-size: 0.24rem;
                    color: #D2211B;;
                    border: 0.01rem solid #D2211B;
                    text-align: center;
                    line-height: 0.55rem;
                    position: absolute;
                    right: 0.3rem;
                    top: 0.5rem;
                }
        }
        // 文章内容
        .article {
            padding-top: 2.3rem;
            overflow: hidden;
            overflow-y: auto;
            overflow-x: hidden;
                .articleConter {
                    padding:  0 0.2rem;
                        h2 {
                            font-size: 0.32rem;
                        }
                        p {
                            text-indent: 0.5rem;
                            font-size: 0.26rem;
                            color: #333333;
                        }
                        .picture {
                            height: 4rem;
                            width: 7.1rem;
                            background-color: pink;
                        }
                }
                .still {
                    height: 3.5rem;
                    width: 100%;
                    padding: 0 0.2rem;
                    position: relative;
                        img {
                            width: 0.88rem;
                            height: 0.88rem;
                            position: absolute;
                            left: 50%;
                            top: 50%;
                            transform: translate(-50%,-50%);
                        }
                        h2 {
                            position: absolute;
                            bottom: 0rem;
                            font-size: 0.32rem;
                        }
                }
                .List {
                    padding:  0.2rem 0.2rem;
                    border-top: 0.01rem solid #DBD8D8;
                    position: relative;
                        h5 {
                            font-size: 0.32rem;
                            margin: 0  1.8rem 0.25rem 0;
                        }
                        .listImg {
                            width: 1.45rem;
                            height: 1.45rem;
                            background-color: pink;
                            position: absolute;
                            right: 0.2rem;
                            top: 0.2rem;
                        }
                        span {
                            font-size: 0.22rem;
                            color: #999999;
                        }
                }
                 // 评论内容
                .comment {
                    width: 100%;
                    position: relative;
                        .zi {
                            width: 0.88rem;
                            height: 0.88rem;
                            position: absolute;
                            left: 50%;
                            top: -1.3rem;
                            transform: translateX(-50%);
                        }
                        h5 {
                            margin-top: 2.4rem;
                            margin-left: 0.2rem;
                            margin: 2.4rem 0 0.3rem 0.2rem;
                            font-size: 0.32rem;
                        }
                        .commentList {
                                li {
                                    height: 2rem;
                                    width: 100%;
                                    padding-left:  0.2rem;
                                    border-top: 0.01rem solid #DBD8D8;
                                    display: flex;
                                    position: relative;
                                        .Img {
                                            width: 1rem;
                                            height: 1rem;
                                            background: pink;
                                            border-radius: 50%;
                                            margin: 0.25rem  0.2rem 0 0;
                                        }
                                        .listConter {
                                            padding-right: 0.4rem;
                                                h6 {
                                                    margin-bottom: 0.3rem;
                                                    color: #0033FF;
                                                    font-size: 0.22rem;
                                                }
                                                p {
                                                    font-size: 0.28rem;
                                                    color: #333333;
                                                }
                                        }
                                        .zan {
                                            position: absolute;
                                            top: 0.42rem;
                                            right: 0.4rem;
                                            color: #B0B0B0;
                                            font-size: 0.16rem;
                                                img {
                                                    width: 0.31rem;
                                                    height: 0.3rem;
                                                    display: inline-block;
                                                }
                                        }   
                                }
                        }
                }
        }
        // 审核
        .audit {
                .auditTop {
                    width: 7.1rem;
                    height: 1.8rem;
                    margin-left: 0.2rem;
                    border-radius: 0.2rem;
                    box-shadow: 0 0 0.25rem #ccc;
                        .title {
                            display: flex;
                            padding: 0 0.57rem 0 0.65rem;
                            justify-content: space-between;
                            h3 {
                                font-size: 0.22rem;
                            }
                            h2 {
                                font-size: 0.28rem;
                            }
                        }
                        .money {
                            margin:  0 0.57rem 0 0.65rem;
                            display: flex;
                            justify-content: space-between;
                            color: #D92F29;
                                b {
                                    font-size: 0.36rem;
                                }
                                span {
                                    font-size: 0.28rem
                                }
                                /deep/.van-icon {
                                    top: 0.06rem;
                                    left: -0.05rem
                                }

                        }
                      
                }
                h6 {
                    margin: 0.32rem 0 0.38rem 0.2rem;
                    font-size: 0.32rem
                }
                .audit-list {
                    height: 2.5rem;
                    width: 100%;
                    padding:  0 0.2rem;
                    border-bottom: 0.01rem solid #CBCBCB;
                    margin-bottom: 0.26rem;
                        .list-top {
                            position: relative;
                                .state {
                                    width: 0.1rem;
                                    height: 0.1rem;
                                    background: #D2211B;
                                    position: absolute;
                                    top: 0.13rem;
                                    left: 0.2rem;
                                    border-radius: 50%;
                                }
                                h4 {
                                    margin: 0 0 0 0.45rem;
                                    font-size: 0.26rem;
                                }
                        }
                        .statement {
                            display: flex;
                            margin-top: 0.32rem;
                                .Img {
                                    width: 1rem;
                                    height: 1rem;
                                    background-color: pink;
                                    border-radius: 50%;
                                    margin-right: 0.1rem;
                                }
                                .conter {
                                    font-size: 0.26rem;
                                        div {
                                            font-size: 0.23rem;
                                        }
                                        span {
                                            color: #0033FF;
                                        }
                                }
                        }
                }
                .list-state {
                    height: 4.5rem;
                    position: relative;
                    h4 {
                        margin-right: 0 !important;
                    }
                    .state-Img {
                        position: absolute;
                        bottom: 0.35rem;
                        right: 0.6rem;
                        display: flex;
                        div {
                            width: 2.9rem;
                            height: 1.65rem;
                            background: pink;
                            margin-left: 0.15rem;
                        }
                    }
                }
        }   
}
</style>
