<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p class="intro">
      2015年6月畢業於世新大學資管系，畢業後在宏華食品有限公司任職-行銷與銷售為主的工作，工作內容包括：設計DM，銷售商品，開拓網路市場。
      堅強獨立 個性開朗
      勇於接受挑戰有著強大的‘獅子山下精神’。不斷地「自主學習」。
      去年疫情期間，更往前端設計邁進自我研習。對於html/css rwd切版甚是熟練<br />
      2021.4更報名資策會UIUX課程充實自我。課程包括 html/css jq js ps ai ui/ux
      php..etc <br />
      2021.9從資策會畢業後更自學Vue.js
      對於新事物學習快速、適應力強，勇於接受新挑戰，不拒絕任何學習的機會，期望往後能在前端設計上任職。
    </p>
    <div class="wrap">
      <div class="box l_box">
        <h5>短期目標</h5>
        <p>精通各式繪圖與設計工具 ，並熟練網頁切版能力。</p>
      </div>
      <div class="box c_box">
        <h5>中期目標</h5>
        <p>
          能夠依照各種不同需求規劃良好的使用者體驗，並熟悉前端三大框架，除了切版更能與後端進行資料串接．
        </p>
      </div>
      <div class="box r_box">
        <h5>長期目標</h5>
        <p>成為專業的網頁 UI/UX 設計 與獨當一面的前端工程師。</p>
      </div>
    </div>
    <p>
      GitHub
      <a href="https://github.com/le1219" target="_blank" rel="github"
        >https://github.com/le1219</a
      >
    </p>
    <!-- 工作經歷 -->
    <div class="part2 mH">
      <h3>Work Experience</h3>
      <ul>
        <li @click="work = 'first'">2020/03 - 2020/12</li>
        <li @click="work = 'second'">2020/12 - 2015/07</li>
        <li @click="work = 'third'">2012/04 - 2014/12</li>
      </ul>
      <div v-if="work == 'first'">
        <h5>MOMOKING EDUCATION Administration</h5>
        <p>
          工作內容：整合公司教務資料達到教學與行政的彙整，製作教材吸引學生注意提高學習能力。
          處理家長對於上課教材的疑問，讓老師安心教學，製作發文素材，剪輯學生上課短片和家長回報學習進度
        </p>
      </div>
      <div v-if="work == 'second'">
        <h5>太和傳統餅 行銷與銷售組長</h5>
        <p>
          工作內容：開拓網路市場讓客人可以在網路上購買，讓世界各地的客人都可以購買到商品
          月營業額高峰達到百萬銷售，對產品銷售作出分析，掌握顧客所喜愛的產品，並對顧客所回饋提出改進
          公司價格牌全面升級，重新設計達到電子化並加入韓，日，英三種語言負責Facebook內容編輯、產品圖拍攝，增加與粉絲互動，提高點擊率
          製作店面文宣與廣告DM
        </p>
      </div>
      <div v-if="work == 'third'">
        <h5>雅田牙醫 牙醫助理</h5>
        <p>工作內容：協助醫師看診與檢驗，器材消毒</p>
      </div>
    </div>
    <!-- 軟體 -->
    <div class="part_3 mH">
      <h3>Skill</h3>
      <div class="flex">
        <div class="skill" v-for="(skill, index) in skills" :key="index">
          <img :src="skill.image" class="skiiImg" />
          <p class="skillName">{{ skill.name }}</p>
        </div>
      </div>
    </div>
    <!-- 小遊戲 -->
    <!-- <button @click="go">Click</button> -->
    <!-- part4 作品-->
    <div class="part4 mH">
      <h3>Portfolio</h3>
      <div class="frame">
        <img :src="bigImgSrc" alt="" class="bigImg" v-scroll="rightA" />
        <div class="square" v-scroll="leftA">
          <img
            :src="foImg.img"
            alt=""
            @click="changeBigImg(foImg.img)"
            class="smallImg"
            v-for="(foImg, index) in prot"
            :key="index"
          />
        </div>
      </div>
    </div>
    <!-- part5 學歷 -->
    <div class="part5 mH" v-scroll="handleScroll">
      <h3>學歷 Education</h3>
      <div class="out_box1">
        <div class="school_exp">
          <h5 class="sch_name">資策會 2021 - 2021</h5>
          <p class="subject">互動式網站UI/UX設計師就業養成班</p>
        </div>
        <div class="school_exp">
          <h5 class="sch_name">世新大學 2011 - 2015</h5>
          <p class="subject">資訊管理資訊科技組</p>
        </div>
        <div class="school_exp">
          <h5 class="sch_name">國立師範大學僑生先修部 2010 - 2011</h5>
          <p class="subject">一類組</p>
        </div>
        <div class="school_exp">
          <h5 class="sch_name">仁濟醫院王華湘中學 2004 - 2010</h5>
          <p class="subject">F.1 - F.6</p>
        </div>
      </div>
    </div>
    <div class="up" @click="up">UP</div>
    <footer>
      <p>Copyright © 2021 Elaine Lai. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      // 預設第一個
      work: "first",
      // 技能
      skills: [
        //  require("../assets/img/logo.png") 使用require引入本機圖片
        {
          name: "html",
          image:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/6/61/HTML5_logo_and_wordmark.svg/200px-HTML5_logo_and_wordmark.svg.png",
        },
        {
          name: "css",
          image:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/d/d5/CSS3_logo_and_wordmark.svg/220px-CSS3_logo_and_wordmark.svg.png",
        },
        {
          name: "jQuery",
          image: "http://www.marcus-povey.co.uk/wp-content/jquery_logo.jpg",
        },
        {
          name: "bootstrap",
          image:
            "https://uploads-ssl.webflow.com/60d29cc33f302e8be91cf0e2/60e8280e777fa914f2591701_5e5cba69e2e9425b17ab2fd6_Blog%2520post%2520feature%2520img%2520(10).jpeg",
        },
        {
          name: "JavaScript",
          image: "https://www.lidihuo.com/uploads/html/javascript_logo.png",
        },
        {
          name: "Adobe illustrator",
          image:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/f/fb/Adobe_Illustrator_CC_icon.svg/1200px-Adobe_Illustrator_CC_icon.svg.png",
        },
        {
          name: "Adobe Photoshop",
          image:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/a/af/Adobe_Photoshop_CC_icon.svg/220px-Adobe_Photoshop_CC_icon.svg.png",
        },
        {
          name: "Adobe XD",
          image:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/c/c2/Adobe_XD_CC_icon.svg/200px-Adobe_XD_CC_icon.svg.png",
        },
      ],
      // 技能結束
      bigImgSrc: require("../assets/img/1.jpg"),
      prot: [
        { img: require("../assets/img/1.jpg") },
        { img: require("../assets/img/2.png") },
        { img: require("../assets/img/3.png") },
        { img: require("../assets/img/4.png") },
        { img: require("../assets/img/5.png") },
        { img: require("../assets/img/6.png") },
        { img: require("../assets/img/7.png") },
        { img: require("../assets/img/achievement_img1.jpeg") },
      ],
    };
  },
  methods: {
    changeBigImg(now_img) {
      this.bigImgSrc = now_img;
    },
    handleScroll: function (evt, el) {
      console.log(window.scrollY);
      if (window.scrollY > 1582) {
        el.setAttribute(
          "style",
          "opacity: 1; transform: translate3d(0, -20px, 0)"
        );
      } else {
        el.setAttribute(
          "style",
          "opacity: 0; transform: translate3d(0, 20px, 0)"
        );
      }
    },
    up() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
    leftA(evt, el) {
      console.log(window.scrollY);
      if (window.scrollY > 1475) {
        el.setAttribute("style", "opacity:1;transform:translateX(-20px)");
      } else {
        el.setAttribute("style", "opacity:0;transform:translateX(20px)");
      }
    },
    rightA(evt, el) {
      console.log(window.scrollY);
      if (window.scrollY > 1475) {
        el.setAttribute("style", "opacity:1;transform:translateX(20px)");
      } else {
        el.setAttribute("style", "opacity:0;transform:translateX(0px)");
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  width: 700px;
  margin: 0px auto;
}

h3 {
  text-decoration: underline;
}
.mH {
  margin-top: 100px;
}
/* 目標 */
a {
  color: #42b983;
}

p {
  line-height: 1.8rem;
  letter-spacing: 0.2rem;
  text-align: left;
}
.wrap {
  display: flex;
  justify-content: center;
  margin-top: 30px;
  margin-bottom: 50px;
}
.box {
  width: 200px;
  height: 100px;
  background-color: rgb(255, 213, 213);
  padding: 2%;
  margin-right: 10px;
  border-radius: 0% 30%;
  box-shadow: 5px 5px 2px rgba(128, 128, 128, 0.171);
  text-align: center;
  transition: 2s;
}
/* hoverbox */
.box:hover {
  transform: translateY(-10px);
}
.box h5 {
  margin: 0;
}
.box p {
  font-size: 12px;
  line-height: 1rem;
  color: rgb(252, 63, 63);
  margin-top: 10px;
}
/* part2 work */
ul {
  list-style-type: none;
  padding: 0;
  display: inline-block;
}
li {
  display: inline-block;
  margin: 0 20px;
  cursor: pointer;
  font-weight: bolder;
}
li:hover {
  text-decoration: underline;
}
/* part3 */
.flex {
  display: flex;
  flex-wrap: wrap;
}
.skill {
  margin: 30px;
  text-align: center;
  width: 100px;
}
.skillName {
  text-align: center;
}
.skiiImg {
  width: 100px;
  height: 100px;
  overflow: hidden;
  transition: 1s;
}
.skiiImg:hover {
  transform: scale(1.2);
}
/* part4 */
.frame {
  display: flex;
  justify-content: center;
  margin-top: 30px;
}
.square {
  width: 300px;
  opacity: 0;
  transition: 2s;
  margin-left: 50px;
}
.smallImg {
  width: 40px;
  height: 60px;
  margin: 10px;
  cursor: pointer;
  transform-origin: center center;
  transition: 1.5s cubic-bezier(0.21, 0.82, 0.82, 1);
}
.smallImg:hover {
  transform: scale(1.1) rotate(360deg);
}
.bigImg {
  width: auto;
  height: 300px;
  opacity: 0;
  transition: 2s;
}
/* part5 css*/
.part5 {
  opacity: 0;
  transition: 2s;
}
.sch_name,
.subject,
h5 {
  text-align: left;
  font-size: 16px;
  margin: 5px;
}
.up {
  width: 50px;
  height: 30px;
  border-radius: 0 30%;
  background-color: rgb(255, 213, 213);
  position: relative;
  right: 0;
  transition: 2s;
  line-height: 2.2rem;
  cursor: pointer;
}
/* footer */
footer p {
  text-align: center;
}
/* rwd */
@media screen and (max-width: 700px) {
  .hello {
    width: 500px;
  }
  .box {
    height: 150px;
  }
}
@media screen and (max-width: 500px) {
  .hello {
    width: 300px;
  }
  .wrap {
    display: flex;
    flex-wrap: wrap;
  }
  .box {
    width: 110px;
    border-radius: 10px;
    margin-top: 15px;
  }
  .skill {
    margin: 10px;
  }
  .frame {
    flex-wrap: wrap;
  }
}
</style>
