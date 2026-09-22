<script setup>
import { ref } from 'vue';
import customer from "./images/img-1.jpg";
import runner from "./images/img-2.jpg";
import merchant from "./images/img-3.jpg";
import pickup from "./images/img-4.jpg";
import delivery from "./images/img-5.jpg";
import commerce from "./images/img-6.jpg";
import rider from "./images/img-7.jpg";
import tracking from "./images/img-8.jpg";
const menuOpen = ref(false)
const logo = 'https://hebbkx1anhila5yf.public.blob.vercel-storage.com/errandmate%20logo-vJdc90wFL0P4W3bGmSjrcuWdmnw5Dd.png'
const images = {
  hero: 'https://hebbkx1anhila5yf.public.blob.vercel-storage.com/img-1-UVtfB4lxCIh0vQHfZityOjZup8xa1o.jpg',
  customer:customer,
  runner: runner,
  merchant: merchant,
  pickup: pickup,
  delivery: delivery,
  commerce : commerce,
  rider:rider,
  tracking : tracking
}
const navItems = ['How it works', 'Customers', 'Runners', 'Merchants']
const roles = [
  { title: 'Customers', heading: 'Get more done.', text: 'Groceries, pickups, and everyday tasks handled while you focus on what matters.', image: images.customer, icon: '⌂' },
  { title: 'Runners', heading: 'Make time work.', text: 'Choose flexible jobs and move with confidence through a trusted network.', image: images.runner, icon: '↗' },
  { title: 'Merchants', heading: 'Grow with us.', text: 'Reach more customers and fulfill local orders with a reliable last-mile partner.', image: images.merchant, icon: '▦' },
]
const steps = [
  { number: '01', title: 'Create Your Errand', text: 'Choose what you need — shopping, pickup, delivery, merchant order or a custom errand.', image: images.customer, icon: '＋' },
  { number: '02', title: 'Get Matched', text: 'ErrandMate connects your task with an available verified runner.', image: images.runner, icon: '⌁' },
  { number: '03', title: 'Track Everything', text: 'Follow your runner and receive updates as your errand moves from pickup to completion.', image: images.pickup, icon: '◎' },
  { number: '04', title: 'Done.', text: 'Your errand is completed. Review the experience and get back to your day.', image: images.delivery, icon: '✓' },
]
</script>

<template>
  <div class="site-shell">
    <header class="nav-wrap"><nav class="nav container"><a class="brand" href="#top"><img :src="logo" alt="ErrandMate Services" /></a><div class="nav-links"><a v-for="item in navItems" :key="item" :href="'#' + item.toLowerCase()">{{ item }}</a></div><div class="nav-actions"><a class="portal" href="#merchants">Merchant portal <span>↗</span></a><a class="button button-dark" href="#download">Get the app <span>↗</span></a></div><button class="menu-button" aria-label="Toggle navigation" @click="menuOpen = !menuOpen">{{ menuOpen ? '×' : '☰' }}</button></nav><div v-if="menuOpen" class="mobile-menu"><a v-for="item in navItems" :key="item" :href="'#' + item.toLowerCase()" @click="menuOpen = false">{{ item }}</a><a href="#download" class="button button-dark">Get the app ↗</a></div></header>

    <main id="top">
      <section class="hero container"><div class="hero-copy"><p class="eyebrow"><span class="dot"></span> One ecosystem. Every errand.</p><h1>Your errands.<br /><em>Handled.</em></h1><p class="hero-text">ErrandMate connects time-pressed customers with verified runners for shopping, pickup, delivery, and everything in between.</p><div class="hero-actions"><a class="button button-lime" href="#download">Get the ErrandMate app <span>↗</span></a><a class="text-link" href="#runners">Become a runner <span>↗</span></a></div><div class="trust-row"><span>✓ Verified runners</span><span>✓ Real-time tracking</span><span>✓ Secure payments</span></div></div><div class="hero-visual"><div class="hero-image-wrap"><img :src="images.hero" alt="ErrandMate runner carrying a grocery delivery" /><div class="image-label"><span class="pulse"></span> Runner en route <strong>●</strong></div></div><div class="float-card customer-float"><span class="mini-icon lime">⌂</span><div><small>Customer</small><b>Errand posted</b></div><span class="check">✓</span></div><div class="float-card merchant-float"><span class="mini-icon lime">▦</span><div><small>Merchant partner</small><b>Order ready</b></div><span class="check">✓</span></div></div></section>

      <section class="marquee"><div class="marquee-track"><span>PEOPLE</span><i>✦</i><span>RUNNERS</span><i>✦</i><span>BUSINESSES</span><i>✦</i><span>PEOPLE</span><i>✦</i><span>RUNNERS</span><i>✦</i><span>BUSINESSES</span></div></section>
 
      <section  id="customers" class="section ecosystem container"><div class="section-heading"><p class="eyebrow">The big idea</p><h2>One platform.<br /><em>Three powerful</em> experiences.</h2><p>ErrandMate brings the people who need things done, the people who get them done, and the businesses they love into one simple ecosystem.</p></div><div class="role-grid"><article v-for="role in roles" :key="role.title" class="role-card"><div class="role-image"><img :src="role.image" :alt="role.title + ' ErrandMate experience'" /><span class="role-icon">{{ role.icon }}</span></div><div class="role-content"><p class="card-kicker">{{ role.title }}</p><h3>{{ role.heading }}</h3><p>{{ role.text }}</p><a class="text-link" href="#download">{{ role.title === 'Customers' ? 'Get the app' : role.title === 'Runners' ? 'Become a runner' : 'Join as a merchant' }} <span>↗</span></a></div></article></div></section>

      <section id="how it works" class="section how-section"><div class="container"><div class="section-heading centered"><p class="eyebrow">How it works</p><h2>Getting things done<br /><em>should be this simple.</em></h2><p>From a simple request to a completed handoff, every step is designed to keep you moving.</p></div><div class="journey-grid"><article v-for="(step, index) in steps" :key="step.number" class="journey-card"><div class="journey-media"><img :src="step.image" :alt="step.title" /><span class="journey-number">{{ step.number }}</span><span class="journey-icon">{{ step.icon }}</span></div><div class="journey-content"><h3>{{ step.title }}</h3><p>{{ step.text }}</p></div><span v-if="index < steps.length - 1" class="journey-connector">→</span></article></div></div></section>

      <section id="technology" class="section technology-section"><div class="container"><div class="section-heading technology-heading"><p class="eyebrow">The ErrandMate platform</p><h2>Technology That<br /><em>Keeps Everything Moving.</em></h2><p>From the moment an errand is created to the moment it is completed, ErrandMate connects customers, runners and merchants through one intelligent platform.</p></div><div class="bento-grid"><article class="tech-card tracking-card"><div class="tech-copy"><span class="tech-label">01 / Visibility</span><h3>Real-Time Tracking</h3><p>Know what is happening at every handoff, without the guesswork.</p></div><div class="tracking-ui"><div class="route-line"></div><span class="route-dot customer-dot">C</span><span class="route-dot runner-dot">R</span><span class="route-dot destination-dot">D</span><div class="track-status"><span class="pulse"></span><div><b>Runner is on the way</b><small>Arriving at destination</small></div><strong>92%</strong></div></div></article><article class="tech-card matching-card"><span class="tech-label">02 / Intelligence</span><h3>Smart Matching</h3><div class="match-ui"><span>Customer request</span><b>⌁</b><span>Available runner</span><strong>Matched ✓</strong></div></article><article class="tech-card network-card"><span class="tech-label">03 / Connection</span><h3>Merchant Network</h3><div class="network-ui"><span>Customer</span><i>→</i><span>Merchant</span><i>→</i><span>Runner</span><i>→</i><span>Home</span></div></article><article class="tech-card payment-card"><span class="tech-icon">▣</span><span class="tech-label">04 / Trust</span><h3>Secure Payments</h3><div class="wallet-ui"><span>ErrandMate wallet</span><b>$ ••••</b><small>Payment secured</small></div></article><article class="tech-card updates-card"><span class="tech-icon">◎</span><span class="tech-label">05 / Clarity</span><h3>Live Updates</h3><div class="status-row"><span>Placed</span><span>Accepted</span><span>Pickup</span><span class="active">On the way</span><span>Done</span></div></article><article class="tech-card verified-card"><span class="tech-icon">✓</span><span class="tech-label">06 / Safety</span><h3>Verified Runners</h3><div class="runner-profile"><span class="avatar">R</span><div><b>Runner profile</b><small>Runner ID • Verified</small></div><strong>✓</strong></div></article></div></div></section>

      <section class="section split-section container"><div class="split-image"><img :src="images.tracking" alt="Runner delivering a grocery box to a customer's door" /><div class="photo-note"><span>⌁</span><div><b>On the move</b><small>Every step, visible.</small></div></div></div><div class="split-copy"><p class="eyebrow">For customers</p><h2>Your time is valuable.<br /><em>Let us handle the rest.</em></h2><p>From groceries and pickups to custom tasks, ErrandMate makes getting things done feel effortless.</p><ul><li>Shopping & grocery runs</li><li>Pickup & drop-off</li><li>Merchant orders</li><li>Custom errands</li><li>Order history & ratings</li><li>Real-time runner tracking</li></ul><a class="button button-dark" href="#download">Download the customer app <span>↗</span></a></div></section>

      <section id="runners" class="section runner-section"><div class="container runner-grid"><div class="runner-copy"><p class="eyebrow">For runners</p><h2>Earn by<br /><em>getting things done.</em></h2><p>Join a trusted network, choose jobs that fit your day, and get the tools you need to move with confidence.</p><div class="feature-pills"><span>Find nearby jobs</span><span>Flexible availability</span><span>Track earnings</span><span>Runner support</span></div><a class="button button-lime" href="#download">Become a runner <span>↗</span></a></div><div class="runner-card"><img :src="images.rider" alt="ErrandMate runner delivering an order" /><div class="earnings-card"><span class="mini-icon lime">↗</span><small>Your next job</small><strong>Ready when you are</strong><span class="status">● Available nearby</span></div></div></div></section>

      <section id="merchants" class="section merchant-section container"><div class="merchant-top"><div><p class="eyebrow">For merchants</p><h2>Turn every order<br /><em>into an opportunity.</em></h2></div><p>Put your business in front of customers and let verified runners help you fulfill orders, reliably and locally.</p></div><div class="merchant-flow"><div class="flow-list"><div><span>01</span><b>Customer places order</b></div><div><span>02</span><b>Merchant receives it</b></div><div><span>03</span><b>Runner picks it up</b></div><div><span>04</span><b>Customer receives it</b></div><a class="button button-dark" href="#download">Become a merchant <span>↗</span></a></div><div class="merchant-photo"><img :src="images.commerce" alt="ErrandMate merchant handing an order to a customer" /><div class="photo-caption">Built for local commerce <span>↗</span></div></div></div></section>

      <section id="download" class="final-cta"><div class="final-inner container"><div><p class="eyebrow">Ready when you are</p><h2>Whatever needs doing,<br /><em>ErrandMate can help.</em></h2><p>Get your errands handled, earn by completing them, or grow your business with the ErrandMate network.</p></div><div class="cta-actions"><a class="cta-card" href="#download"><span>For customers</span><b>Download the app</b><i>↗</i></a><a class="cta-card" href="#runners"><span>For runners</span><b>Become a runner</b><i>↗</i></a><a class="cta-card" href="#merchants"><span>For merchants</span><b>Join ErrandMate</b><i>↗</i></a></div></div></section>
    </main>

    <footer class="footer"><div class="container footer-grid"><div class="footer-brand"><a class="brand" href="#top"><img :src="logo" alt="ErrandMate Services" /></a><p>Your errands.<br />Handled.</p></div><div><b>Platform</b><a href="#customers">For customers</a><a href="#runners">For runners</a><a href="#merchants">For merchants</a><a href="#how it works">How it works</a></div><div><b>Company</b><a href="#top">About</a><a href="#top">Contact</a><a href="#top">Careers</a></div><div><b>Legal</b><a href="#top">Privacy policy</a><a href="#top">Terms of service</a><a href="#top">Cookie policy</a></div></div><div class="container footer-bottom"><span>© 2026 ErrandMate. All rights reserved.</span><span>Made for getting things done.</span></div></footer>
  </div>
</template>
