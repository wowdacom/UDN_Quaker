<template>
  <div id="app">
    <indicator></indicator>
        <head-bar>
          <a href="index.html">副食品3大觀念</a>
          <a href="./complementary-food/index.html" target="_blanck">邁向營養均衡的關鍵</a>
        </head-bar>

        <cover name="添加副食品掌握3大關鍵" position="rightTop" :src="require('../static/CoverBg/bg01_m.jpg')" :src-web="require('../static/CoverBg/web/bg01.jpg')" use-arrow="yes" use-animate="yes" use-hint="yes">
          <h1 class="cover-title"><b>添加副食品掌握3大觀念<br>讓孩子身心成長更健康</b></h1>
        </cover>

        <content-container>
          <br><p>
          <Share href="https://udn.com/upf/newmedia/2017_data/ideal/index.html"></Share>
          <br><p>
          <p><b>「孩子3歲前要有自己專屬的副食品」</b>國內小兒科陳木榮醫師說。每位父母都知道「嬰幼兒的早期營養，3歲以前是關鍵」，除了當下的均衡之外，也是塑造孩子食物偏好和長大後飲食習慣的重要時期。</p><p>
          <br></p>
          <p>但是，究竟該如何為孩子添加副食品才能面面兼顧？聯合報集合國內小兒科醫師、臨床營養師與職能治療師的觀點，透過不同的切入方式，談添加副食品的原則。讓爸媽們能「更新」自己的觀念，讓孩子在這段時期吃得健康、快樂長大！</p>
          <p><br></p>
        </content-container>

        <div class="fixText">
          <anchor title="觀念1">
            <parallax-bg 
            :src="require('../static/CoverBg/b01_m.jpg')" :src-web="require('../static/CoverBg/web/b01.jpg')">
            </parallax-bg>
          </anchor>
        <h2><b>把握3歲前的關鍵期　讓孩子養成好的飲食習慣</b></h2>
        </div>

        <content-container>

          <p><br></p>
          <p>嬰兒期正是孩子成長最快速的階段，母乳或配方奶及副食品的添加成為主要的營養來源。根據衛福部今年公佈的《幼兒營養參考手冊》指出，<b>三歲前的營養攝取對於孩子日後的成長發展深具影響力</b>，除了先天遺傳的差異外，從哺餵方式到均衡的營養攝取，都是新手爸媽的重要課題。</p>
          <p><br></p>
          <p>近年國內父母多遵照世界衛生組織的建議，以純母乳哺育至6 個月後為目標，再開始添加副食品。然而，臺灣嬰兒於4 個月後鐵質缺乏狀況之比例明顯上升。為降低缺鐵性貧血的機率，臺灣兒科醫學會則建議嬰兒滿4-6個月後，可以開始給予副食品，補足母奶以外的營養。</p>
          <p><br></p>
          <Column-One description="<b>飲食中之鐵和鋅多為生物利用率較低的食物，造成鐵和鋅之吸收受到抑制，故鐵缺乏通常易伴隨鋅缺乏</b><br>資料來源：衛生福利部國民健康署《嬰兒期營養參考手冊》、 吳佩芯（2012）台灣嬰幼兒體位與營養狀況之探" :src="require('../static/SectionBg/chart001_m.png')" :src-web="require('../static/SectionBg/web/chart001.png')">
            <h4><b>0-6個月嬰兒主要營養素攝取不足百分比(%)</b></h4>
          </Column-One>
          <p><br></p>
          <Youtube :src="require('../static/video/doctor_talking.mp4')" showinfo="no" controls="yes" autoplay="no" muted="yes"></Youtube>
          <p><br></p>
          <p>小兒科陳木榮醫師（柚子醫師）指出，<b>「鐵質是身體裡面氧氣攜帶的重要物質，如果一個孩子鐵質缺乏的話，可能影響到他的學習，也可能影響智力發展。」</b>，因此建議父母親，嬰兒滿4-6個月開始搭配富含鐵的副食品，例如可以強化鐵的米精、麥精，幫助孩子的營養攝取。</p>
          <p><br></p>
          <Quote style="color: #d15c40" text="嬰幼兒飲食中食物的營養質量相對重要，例如，每100卡路里的食物，6至8個月大的純母乳餵養嬰兒的鐵質需求估計相當於一個成年男性的9倍。<span style='font-size: 0.5em'>[1]</span>"></Quote>
          <p><br></p>
          <h3>訓練孩子咀嚼的能力　首重「用湯匙餵食」</h3>
          <p><br></p>
          <p>陳木榮醫師曾在診間遇過有父母把添加副食品誤以為只要在泡奶時順便在奶瓶裡加一湯匙或兩湯匙的米精，就等於給孩子吃了副食品。他說：<b>「副食品的意義不是只有增加熱量而已，你加在奶粉裡面就是增加熱量，但是沒有訓練到小孩子咀嚼的能力。」</b></p>
          <p><br></p>
          <Quote style="color: #d15c40" text="小孩子在剛開始適應副食品的時候，一般先從米精、麥精，香蕉泥，地瓜泥、水果泥等餬狀泥狀的食物開始，一次一種少量、多樣化地利用湯匙慢慢餵食。"></Quote>

          <p><br></p>
          <p>不僅有助於孩子學習咀嚼的動作與體驗食物的層次，獲取更多營養，還能早期型塑良好飲食習慣，奠定後期對非傳染性疾病，例如肥胖、偏食的免疫能力。</p>
          <p><br></p>
          <p>醫師指出，孩子的第一顆牙齒，可能五、六個月就會慢慢地冒出來，爸媽製作副食品可漸漸地保留一點點小顆粒，可保持食物的能量和營養密度，較厚實的粗食能可以幫助孩子訓練咀嚼能力，讓孩子能順利過渡到能與大人一起共餐，接受各種質地的食物。</p>
          <p><br></p>

        </content-container>

        <div class="fixText">  
          <anchor title="觀念2">
            <parallax-bg :src="require('../static/CoverBg/b02_m.jpg')" :src-web="require('../static/CoverBg/web/b02.jpg')">
              
            </parallax-bg>
          </anchor>
          <h2><b>想要孩子長高長壯？先設定飲食常規</b></h2>
        </div>

        <content-container>

          <p><br></p>
          <p>孩子剛出生時，小兒科醫師都會告訴爸媽利用新生兒的體重計算每日奶量。隨著孩子進階到需要添加副食品的階段，爸爸媽媽一邊喜悅孩子的成長，一邊內心卻感到「無所適從」。</p>
          <p><br></p>
          <p>一方面是因為一旦開始副食品，就沒有明確的公式計算孩子究竟要吃到多少量。或者，多數的爸媽費心做了副食品，卻遇到「嬰兒不吃」的問題，確實讓人頭疼。</p>
          <p><br></p>
          <p>結果發現，這些孩子多數都會在餐與餐間吃零食，進而影響正餐的時候吃不到建議攝取量，導致發育緩慢。林郁茹營養師說，<b>「一到三歲的孩子，每餐至少要吃半碗到七分滿的飯，想長高長壯就是要吃到這麼多的量。」</b></p>
          <p><br></p>
          <p><br></p>
        </content-container>

        
        <AnimationMap />

        <content-container>

          <p><br></p>
          <p>若是遇到「三口組」的孩子（指只吃三口就不吃的孩子），營養師建議，爸媽先不用心慌，每個孩子身體吸收的狀況跟飲食的偏好都不太一樣，如果正餐時間孩子不想吃，爸媽不需強迫，但要堅定地讓孩子知道，如果他現在不吃，就沒有其他的東西吃。</p>
          <p><br></p>
          <Quote style="color: #d15c40" text="最怕的是父母親的補償心態，捨不得孩子餓肚子，進而多給了孩子一塊蛋糕或零食，反而建立錯誤的飲食常規，沒有讓孩子養成「在固定的時間點，吃該吃的量」。"></Quote>
          <p><br></p>
          <p>另外，若是因出門在外，用餐時間有所延遲，爸媽可以準備一些低熱量的蔬菜水果給孩子吃，幾顆小蕃茄或半根的小黃瓜，把握讓孩子好消化，卻也不會影響下一餐胃口的食物。</p>
          <p><br></p>

        </content-container>

        <div class="fixText">
          <anchor title="觀念3">
              <parallax-bg 
              :src="require('../static/CoverBg/b03_m.jpg')" :src-web="require('../static/CoverBg/web/b03.jpg')">
                
              </parallax-bg>
          </anchor>
          <h2><b>掌握餵食技巧 爸媽快樂、冷靜、不焦慮</b></h2>
        </div>

        <content-container>

          <p><br></p>
          <p>在孩子吃副食品的階段，其實他們的身心也正處於一個微妙的發展過程。孩子開始會專注於發展基本的運動技能且漸漸學習獨立。根據澳洲兒童營養研究中心報告，孩子通常在兩歲的時候開始有自己的主見跟想法，開始表達自己的意見，也會明確地拒絕爸媽準備的東西。</p>
          <p><br></p>
          <p>國外研究顯示，許多孩子只喜歡吃自己熟悉的食物，讓爸媽在提供新食物時，感到非常困難。這種「食物拒新」症狀常見於12到24個月大的孩子。同時，如果孩子的生長曲線在這時候趨於緩慢，也容易造成爸媽在餵食的過程中感到內心焦慮，造成雙方之間的不良循環。</p>
          <p><br></p>
          <Quote style="color: #d15c40" text="「其實孩子跟爸媽都是相映的」有二十年資歷的職能治療師許嘉琪說。"></Quote>
          <p><br></p>
          <p><b>「別把教養守則視為理所當然。畢竟沒有一個特定的方式能適用於所有的孩子」</b>。因此，當爸媽建立了常規的正餐和點心時間、提供多樣化的食物，幫助孩子養成良好飲食習慣的同時，也能透過三個實用的技巧，從<b>「給予選擇權、邀請式語言到遊戲式介紹」</b>，讓餵食副食品更簡單。</p>
          <p><br></p>
          <Column-One :src="require('../static/CoverBg/b04_m.jpg')" :src-web="require('../static/CoverBg/web/b04.jpg')"></Column-One>
          <p><br></p>
          <p>首先，爸媽必須給予孩子選擇權，讓孩子能自己選擇想吃哪些食物或哪些點心，透過這種方式讓他們在滿足食慾的過程中也能有決定權。接著，爸媽的態度必須保持靈活彈性，用邀請式的語言引導孩子，多多介紹不同顏色，不同形狀的食物給孩子認識。甚至，以遊戲的方式結合飲食，讓孩子選擇用手觸摸不同形體的食物，啟蒙孩子的感官與想像力。</p>
          <p><br></p>
          <p>其實，每個孩子一出生就用全身的感官在認識眼前的世界，想讓孩子感覺快樂、安全，且擁有健康的身體，爸媽首要回歸自身的安適感，保持快樂、冷靜、不焦慮的態度，才能建立一個充滿愛的環境，讓孩子的身心靈都能健康成長。</p>
          <p><br></p>
          <hr>
          <h5>[1]資料來源：Dewey KG, Brown KH: Update on technical issues concerning complementary feeding of young children in developing countries and implications for intervention programs. Food Nutr Bull 2003;24:5-28</h5>
          <p><br></p>
          <Share href="https://udn.com/upf/newmedia/2017_data/ideal/index.html"></Share>
          <p><br></p>
          <editor>
            <div>製作人：林筱穎</div>
            <div>視覺設計：蘇士堯</div>
            <div>攝影：賴佐誌</div>
            <div>影音：蘇士堯</div>
            <div>網頁製作：胡凈悟</div>
            <div>議題行銷：張乃文、陳欣媛、王敏</div>
            <div>監製：董谷音、潘如瑩、陳曼薇</div>
            <div>圖片來源：123RF</div>
            <div>2018.09.27</div>
          </editor>
          <p><br></p>
          <Relate title="延伸閱讀"
            href1="https://udn.com/upf/newmedia/2018_data/schoollunch/index.html" :img1="require('../static/RelatedBg/ex01.jpg')" text1="35元的營養午餐 你的孩子吃了什麼？" 
            href2="https://udn.com/upf/newmedia/2018_data/dream2/index.html" :img2="require('../static/RelatedBg/ex02.jpg')" text2="不再複製命運 數位改變偏鄉兒未來" 
            href3="https://udn.com/upf/newmedia/2018_data/British-Council/" :img3="require('../static/RelatedBg/ex03.jpg')" text3="自主享學的小學生英語課" 
            href4="https://udn.com/upf/newmedia/2018_data/British-Council_2/chapter1.html" :img4="require('../static/RelatedBg/ex04.jpg')" text4="慢慢走、快快到 用英語力深化競爭力" > 
          </Relate>
          <p><br></p>
          <fb-comment></fb-comment>
        </content-container>
        
  </div>
</template>

<script>
import Indicator from './components/Indicator'
import HeadBar from './components/HeadBar'
import Cover from './components/Cover'
import Content from './components/Content'
import Share from './components/Share'
import Anchor from './components/Anchor'
import ParallaxBg from './components/ParallaxBg'
import ColumnOne from './components/ColumnOne'
import Youtube from './components/Youtube'
import Quote from './components/Quote'
import AnimationMap from './components/new-feature/AnimationMap'
import Relate from './components/Relate'
import FBComment from './components/FBComment'
import Editor from './components/Editor'

export default {
  name: 'App',
  data () {
    return {
    }
  },
  components: {
    'indicator': Indicator,
    'head-bar': HeadBar,
    'cover': Cover,
    'content-container': Content,
    'Share': Share,
    'anchor': Anchor,
    'parallax-bg': ParallaxBg,
    'Column-One': ColumnOne,
    'Youtube': Youtube,
    'Quote': Quote,
    'AnimationMap': AnimationMap,
    'Relate': Relate,
    'fb-comment': FBComment,
    'editor': Editor
  },
}
</script>

<style lang="scss">
#app {
  background-color: #EEEEEE;
  hr { 
      display: block;
      margin-top: 0.5em;
      margin-bottom: 0.5em;
      margin-left: auto;
      margin-right: auto;
      border-style: inset;
      border-width: 1px;
  }
  .cover-title {
    margin: 0;
  }
  .map-title {
    background-color: inherit;
  }
  .fixText {
    color: #fff;
    width: 100%;
    position: relative;
    text-shadow: 0 0 6px #303030;
    h2 {
      position: absolute;
      left: 50%;
      top: 50%;
      z-index: 10;
      width: 75%;
      transform: translate(-50%, -50%);
      padding: 15px;
      margin: 0px;
      padding: 0px;
      @media (min-width: 768px) and (max-width: 1023px) {

      }
      @media screen and (min-width: 1024px) {
        text-align: center;
      }
    }
  }
}
</style>
