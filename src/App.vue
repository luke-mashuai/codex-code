<script setup>
import heroImage from "./assets/restaurant-hero.svg";
import fishImage from "./assets/dish-fish.svg";
import burrataImage from "./assets/dish-burrata.svg";
import soupImage from "./assets/dish-soup.svg";
import souffleImage from "./assets/dish-souffle.svg";
import steakImage from "./assets/dish-steak.svg";
import tomatoBeefImage from "./assets/dish-tomato-beef.svg";

const navItems = [
  { label: "菜单", href: "#menu" },
  { label: "风味", href: "#story" },
  { label: "到店", href: "#visit" },
];

const quickInfo = [
  { label: "人均", value: "¥168" },
  { label: "招牌", value: "炭烤桂鱼" },
  { label: "适合", value: "约会 · 小聚 · 家宴" },
];

const menuItems = [
  {
    name: "桂花酒炭烤桂鱼",
    price: "¥128",
    category: "江南炭火",
    image: fishImage,
    description: "薄盐腌制后慢烤，鱼皮带一点焦香，配桂花米酒汁和小葱油。",
    featured: true,
  },
  {
    name: "青梅番茄布拉塔",
    price: "¥56",
    category: "冷前菜",
    image: burrataImage,
    description: "冷泡青梅汁、熟番茄和奶香布拉塔，酸甜轻盈。",
  },
  {
    name: "砂锅菌菇鸡汤",
    price: "¥78",
    category: "暖汤",
    image: soupImage,
    description: "云南菌菇、走地鸡和老姜慢煨，入口清亮，收尾回甘。",
  },
  {
    name: "黑芝麻舒芙蕾",
    price: "¥42",
    category: "甜点",
    image: souffleImage,
    description: "现烤 18 分钟，外层轻盈，内里是温热黑芝麻流心。",
  },
  {
    name: "炭烤安格斯牛排",
    price: "¥168",
    category: "炭火主菜",
    image: steakImage,
    description: "厚切牛排炭火锁汁，配黑蒜黄油、烤小胡萝卜和海盐。",
  },
  {
    name: "西红柿牛腩",
    price: "¥88",
    category: "经典热菜",
    image: tomatoBeefImage,
    description: "牛腩慢炖到软糯，番茄汤底酸甜浓郁，配土豆和香草。",
  },
];

const stats = [
  { value: "26", label: "个当季菜品" },
  { value: "3", label: "间包厢" },
  { value: "80", label: "个餐位" },
];
</script>

<template>
  <header class="site-header">
    <a class="brand" href="#top" aria-label="拾味庭院首页">
      <span class="brand-mark">拾</span>
      <span>拾味庭院</span>
    </a>
    <nav class="main-nav" aria-label="主导航">
      <a v-for="item in navItems" :key="item.href" :href="item.href">
        {{ item.label }}
      </a>
    </nav>
    <a class="header-action" href="#reserve">订位</a>
  </header>

  <main id="top">
    <section class="hero" aria-label="拾味庭院餐厅首屏">
      <img
        class="hero-image"
        :src="heroImage"
        alt="餐厅木桌上的烤鱼、蔬菜、陶瓷餐盘与温暖灯光"
      />
      <div class="hero-shade"></div>
      <div class="hero-content">
        <p class="eyebrow">Seasonal Kitchen · Shanghai</p>
        <h1>拾味庭院</h1>
        <p class="hero-copy">
          把江南时令、炭火香气和手作甜点放进一顿松弛的晚餐里。今晚有热汤，也有刚出炉的面包。
        </p>
        <div id="reserve" class="hero-actions">
          <a class="primary-button" href="tel:+862155560888">电话订位</a>
          <a class="secondary-button" href="#menu">查看菜单</a>
        </div>
      </div>
      <aside class="reservation-panel" aria-label="今日营业信息">
        <span>今日</span>
        <strong>17:30 - 22:30</strong>
        <p>静安区梧桐路 118 号 · 晚市余位 6 桌</p>
      </aside>
    </section>

    <section class="quick-info" aria-label="餐厅特色">
      <div v-for="item in quickInfo" :key="item.label">
        <span>{{ item.label }}</span>
        <strong>{{ item.value }}</strong>
      </div>
    </section>

    <section id="menu" class="section menu-section">
      <div class="section-heading">
        <p class="eyebrow">Tonight's Table</p>
        <h2>晚市推荐</h2>
      </div>
      <div class="menu-grid">
        <article
          v-for="item in menuItems"
          :key="item.name"
          class="menu-card"
          :class="{ featured: item.featured }"
        >
          <div class="menu-photo">
            <img :src="item.image" :alt="item.name" />
          </div>
          <div class="menu-card-body">
            <div class="menu-meta">
              <span class="category">{{ item.category }}</span>
              <span class="price">{{ item.price }}</span>
            </div>
            <h3>{{ item.name }}</h3>
            <p>{{ item.description }}</p>
          </div>
        </article>
      </div>
    </section>

    <section id="story" class="section story-section">
      <div class="story-copy">
        <p class="eyebrow">From Market To Fire</p>
        <h2>让食材先说话</h2>
        <p>
          我们每天从附近菜场和稳定小农处挑选蔬果、鱼鲜与香草。厨房保留中式火候，也借一点开放式餐厨的轻松节奏：看得见的炭火、闻得到的高汤、每桌都刚好热闹。
        </p>
      </div>
      <div class="story-stats" aria-label="餐厅数据">
        <div v-for="item in stats" :key="item.label">
          <strong>{{ item.value }}</strong>
          <span>{{ item.label }}</span>
        </div>
      </div>
    </section>

    <section id="visit" class="section visit-section">
      <div>
        <p class="eyebrow">Visit Us</p>
        <h2>今晚来坐坐</h2>
      </div>
      <div class="visit-details">
        <p><strong>地址</strong> 上海市静安区梧桐路 118 号</p>
        <p><strong>营业</strong> 周二至周日 11:30 - 14:00 / 17:30 - 22:30</p>
        <p><strong>电话</strong> <a href="tel:+862155560888">021-5556-0888</a></p>
      </div>
    </section>
  </main>
</template>
