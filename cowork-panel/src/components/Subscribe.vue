<template>
<div class="subscribe">
  <div v-if="this.isUser" class="columns is-mobile is-centered">
    <div class="column is-narrow">
        <a href="./#/order" class="button is-warning is-large is-outlined">{{ this.button.order }}</a>
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <img src="/static/img/PANO_20171111_100131.jpg" alt="progressbar cowork bratislava">
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <div class="card">
        <header class="card-header">
          <p class="card-header-title">
           🏢 Coworking 👩‍🚀 Space Offers
          </p>
        </header>
        <div class="card-content">
          <div class="content">
            <ul>
              <li>
                <a href="https://www.google.com/maps/place/Progressbar+hackerspace/@48.1442259,17.1055539,17z/data=!4m8!1m2!3m1!2sProgressbar+hackerspace!3m4!1s0x0:0x72ac0b6fccaf66fd!8m2!3d48.1442778!4d17.1065933" title="Michalska 3, Bratislava">Place for your work in downtown</a>
              </li>
              <li>
                <a href="https://beta.speedtest.net/result/6614494632">High-speed Internet ~ 250/20</a><a href="http://www.speedtest.net/my-result/a/3374894584">📱</a>
              </li>
              <li>
                <a href="https://scontent-vie1-1.xx.fbcdn.net/v/t31.0-8/21765459_1941520825863850_876389467015918658_o.jpg?oh=7de68da52211a7304d10a3298d7e02fc&oe=5A538F7E">Lot of Electric Sockets ⚡️🔌</a>
              </li>
              <li>
                <a href="https://www.google.com/maps/place/Progressbar+hackerspace/@48.1442769,17.1065927,3a,75y,68.38h,60.45t/data=!3m8!1e1!3m6!1sAF1QipOS15iBvtp1oSLXg6nuorM282YC64pjorvA2LVk!2e10!3e11!6shttps:%2F%2Flh5.googleusercontent.com%2Fp%2FAF1QipOS15iBvtp1oSLXg6nuorM282YC64pjorvA2LVk%3Dw203-h100-k-no-pi-0-ya6.500005-ro-0-fo100!7i8000!8i4000!4m5!3m4!1s0x476c8946152ff129:0x72ac0b6fccaf66fd!8m2!3d48.1442784!4d17.1065933" title="1080p HDMI/DVI mostly">External Monitors - shared 🖥</a>
              </li>
              <li>
                <a href="http://www.ikea.com/sk/sk/catalog/products/S29084966/" title="IKEA SKARSTA">Standing desks</a>
              </li>
              <li>
                Room for calls 🗣📞
              </li>
              <li>
                Coding women have 50% off 👩🏽‍💻
              </li>
              <li>
                Bitcoin & Litecoin accepted
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
    <div class="column is-narrow">
      <div class="card">
        <header class="card-header">
          <p class="card-header-title">
            🍳 Kitchen & Drink 🥤 bar
          </p>
        </header>
        <div class="card-content">
          <div class="content">
            <ul>
              <li>
                ☕️ Specialty Coffee
              </li>
              <li>
                🍵 Tea
              </li>
              <li>
                <a href="https://www.facebook.com/progressbar/photos/a.946997141982895.1073741833.140864112596206/1933082956707637/?type=3" title="drinks in fridge">🍹 Softdrinks ❄️ </a>
                <ul>
                  <li>
                    Club-Mate
                  </li>
                  <li>
                    Flora-power
                  </li>
                  <li>
                    Fritz-kola
                  </li>
                  <li>
                    Mana Roots
                  </li>
                  <li>
                    Thomas Henry Mate-Mate
                  </li>
                </ul>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <iframe src="https://www.google.com/maps/embed?pb=!1m0!4v1510323201819!6m8!1m7!1sCAoSLEFGMVFpcE50MW83am50YXRrdnRwTG1kczV4N0s0TUhHX05DTE1TZmpTbnlS!2m2!1d48.1442841!2d17.1065927!3f92.18082033085125!4f-19.784725182968003!5f0.4000000000000002" width="360" height="300" frameborder="0" style="border:0" allowfullscreen></iframe>
    </div>
    <div class="column is-narrow">
      <iframe src="https://www.google.com/maps/embed?pb=!1m0!4v1510323406618!6m8!1m7!1sCAoSLEFGMVFpcE9TMTVpQnZ0cDFvU0xYZzZudW9yTTI4MllDNjRwam9ydkEyTFZr!2m2!1d48.1442769!2d17.1065927!3f56.55411849549628!4f-28.5293173380876!5f0.4000000000000002" width="360" height="300" frameborder="0" style="border:0" allowfullscreen></iframe>
    </div>
  </div>
  <div v-if="!this.isUser" class="columns is-centered">
    <div class="column is-narrow">
      <div class="control has-icons-left">
        <input v-model="subEmail" class="input is-medium is-white" type="email" placeholder="Enter your email">
        <span class="icon is-medium is-left">
          <i class="fa fa-envelope"></i>
        </span>
      </div>
    </div>
    <div class="column is-narrow">
      <a v-if="this.config.coworkSubscribe" @click="subscribeMe(subEmail)" class="button is-warning is-medium is-outlined">{{ this.button.subscribe }}</a>
      <a v-if="!this.config.coworkSubscribe" @click="subscribeMe(subEmail)" class="button is-warning is-medium is-outlined" disabled>{{ this.button.subscribe }}</a>
      <a v-if="this.config.coworkLogin" @click="sendLoginLink(subEmail)" class="button is-primary is-medium is-outlined">{{ this.button.login }}</a>
      <a v-if="!this.config.coworkLogin" @click="sendLoginLink(subEmail)" class="button is-primary is-medium is-outlined" disabled>{{ this.button.login }}</a>
      <a class="button is-info is-medium is-outlined" href="https://m.me/progressbar">Contact us via ⚡️Messenger</a>
    </div>
  </div>
  <div class="columns is-centered">
    <Offer></Offer>
  </div>
  <div class="columns is-centered">
    <div class="column is-4">
      <article class="message is-dark">
        <div class="message-header">
          <p>Our story</p>
        </div>
        <div class="message-body">
          <div class="content">
            <ul>
              <li>
                We started as <a href="https://progressbar.sk">first Slovak hackerspace</a> back in June 2010, this is our 3rd place as we went through expansion and <a href="https://progressbar.sk/calendar">held more and biggers meetups</a>.
              </li>
              <li>
                In September 2017 we considered to keep up our 💸 cashflow & our existence and started thinking about daily utilization. We came up with idea to open <strong>coworking</strong> in our hackerspace Progressbar in Bratislava.
              </li>
              <li>
                Now we are looking to move in new space to double our meetup space and increase coworking size.
              </li>
              <li>
                If you think we are doing great thing
                <ul>
                  <li>
                    <a href="https://donate.progressbar.sk">you can support us at donate.progressbar.sk</a>
                  </li>
                  <li>
                     signup for our <a href="https://cowork.progressbar.sk">coworking in Bratislava</a>
                  </li>
                  <li>
                    <router-link to="/sponsors"><a href="/#/sponsors">be our proud sponsor</a></router-link>
                  </li>
                </ul>
              </li>
              <li>
                👋🏼 You are welcome 🤗
              </li>
            </ul>
          </div>
        </div>
      </article>
    </div>
    <div class="column is-3">
      <article class="message is-dark">
        <div class="message-header">
          <p>Our coworkers are ~</p>
        </div>
        <div class="message-body">
          <div class="content">
            <ul>
              <li>
                Blockchain startups
              </li>
              <li>
                Decentralization technology specialists
              </li>
              <li>
                Cryptocurrency techies & fanatics
              </li>
              <li>
                Backend & Frontend developers
              </li>
              <li>
                Machine learning developers
              </li>
              <li>
                Hardware tinkers
              </li>
              <li>
                Opensource developers
              </li>
              <li>
                Cyberpunks & Cypherpunks
              </li>
            </ul>
          </div>
        </div>
      </article>
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <img src="/static/img/P71108-200741.jpg" alt="progressbar cowork bratislava blockchain meetup">
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <img src="/static/img/P71108-222854.jpg" alt="progressbar tech cowork bratislava bitcoin accepted">
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <a class="button is-outlined is-white" href="https://progressbar.sk/calendar">Upcoming meetups</a>
    </div>
    <div class="column is-narrow">
      <router-link to="/coworking-progressbar-bratislava-photos"><a class="button is-outlined is-white">Coworking Bratislava Meetup Photos</a></router-link>
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <a class="button is-outlined is-link" href="https://www.facebook.com/progressbar">Progressbar at Facebook</a>
    </div>
    <div class="column is-narrow">
      <a class="button is-outlined is-info" href="https://t.me/coworkprogressbar">Cowork Progressbar at Telegram</a>
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <a class="button is-outlined is-white" href="https://donate.progressbar.sk">💰 Donate Progressbar</a>
    </div>
    <div class="column is-narrow">
      <router-link to="/call-for-the-sponsors"><a class="button is-outlined is-white">Call for the Sponsors</a></router-link>
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <a class="button is-outlined is-white" href="https://www.google.com/maps/place/Progressbar+hackerspace/@48.1442841,17.1065927,3a,75y,183.19h,75.08t/data=!3m8!1e1!3m6!1sAF1QipNt1o7jntatkvtpLmds5x7K4MHG_NCLMSfjSnyR!2e10!3e11!6shttps:%2F%2Flh5.googleusercontent.com%2Fp%2FAF1QipNt1o7jntatkvtpLmds5x7K4MHG_NCLMSfjSnyR%3Dw203-h100-k-no-pi0-ya261.5-ro-0-fo100!7i8000!8i4000!4m5!3m4!1s0x476c8946152ff129:0x72ac0b6fccaf66fd!8m2!3d48.1442784!4d17.1065933" >Workspace Deck (360)</a>
    </div>
    <div class="column is-narrow">
      <a class="button is-outlined is-white" href="https://www.google.com/maps/place/Progressbar+hackerspace/@48.1442769,17.1065927,3a,75y,68.38h,60.45t/data=!3m8!1e1!3m6!1sAF1QipOS15iBvtp1oSLXg6nuorM282YC64pjorvA2LVk!2e10!3e11!6shttps:%2F%2Flh5.googleusercontent.com%2Fp%2FAF1QipOS15iBvtp1oSLXg6nuorM282YC64pjorvA2LVk%3Dw203-h100-k-no-pi-0-ya6.500005-ro-0-fo100!7i8000!8i4000!4m5!3m4!1s0x476c8946152ff129:0x72ac0b6fccaf66fd!8m2!3d48.1442784!4d17.1065933">Workspace Cowork (360)</a>
    </div>
    <div class="column is-narrow">
      <router-link to="/coworking-bratislava"><a class="button is-outlined is-white">Coworking Bratislava</a></router-link>
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <h1 id="blackh1">Tech Cowork Progressbar in Bratislava</h1>
    </div>
  </div>
  <div class="columns is-centered">
    <div class="column is-narrow">
      <h2 id="blackh2">Tech Cowork Progressbar in Bratislava where we accept Bitcoin and Litecoin for coworking. Daypass starts from {{ this.config.orderPrices.day }}€ </h2>
    </div>
  </div>
  <cookie-law transitionName="fade"
   position="bottom"
   theme="dark-lime"
   buttonText="I understand"></cookie-law>
</div>
</template>

<script>
import axios from 'axios'
import CookieLaw from 'vue-cookie-law'
import Offer from './Offer.vue'

export default {
  name: 'subscribe',
  data() {
    return {
      seats: {
        subscribers: 0,
        capacity: 0
      },
      credited: 0,
      orderSum: {},
      newSubscriber: {
        email: ''
      },
      button: {
        subscribe: 'Register for cowork',
        verify: '__',
        login: 'Send login link',
        order: 'Go to Dashboard'
      },
      daysBooked: 0,
      subEmail: '',
      isUser: false,
      config: {
        baseWebUrl: 'https://cowork.progressbar.sk/',
        orderPrices: {
          day: 5,
          month: 100,
          fix: 180,
          locker: 10,
          nonstop: 20
        },
        openHours: {
          monthPass: {
            start: 6,
            end: 18
          },
          dayPass: {
            start: 9,
            end: 18
          }
        },
        coworkLogin: false,
        coworkSubscribe: false
      }
    }
  },
  components: {
    Offer,
    CookieLaw
  },
  created() {
    this.alreadyUser()
    this.getConfig()
  },
  methods: {
    alreadyUser() {
      if (this.$ls.get('user')) {
        this.isUser = true
      }
    },
    getConfig() {
      axios({
        method: 'get',
        url: this.$api.base + this.$api.pubConfig
      })
        .then(response => {
          // console.log(response)
          this.config = response.data
          this.seats.capacity = response.data.seatCapacity
        })
        .catch(e => {
          console.log(e)
        })
    },
    getSubscribers() {
      axios({
        method: 'get',
        url: this.$api.base + this.$api.subscribers
      })
        .then(response => {
          // console.log(response)
          this.seats = response.data.seats
          this.orderSum = response.data.orderSum
          this.daysBooked = response.data.daysBooked
          this.config = response.data.config
        })
        .catch(e => {
          console.log(e)
        })
    },
    subscribeMe(email) {
      axios({
        method: 'get',
        url: this.$api.base + this.$api.newSubscriber,
        params: {
          email
        }
      })
        .then(response => {
          // console.log(response)
          this.button.subscribe = response.data.code
        })
        .catch(e => {
          console.log(e)
        })
    },
    sendLoginLink(email) {
      axios({
        method: 'get',
        url: this.$api.base + this.$api.login,
        params: {
          email
        }
      })
        .then(response => {
          // console.log(response)
          this.button.subscribe = response.data.code
        })
        .catch(e => {
          console.log(e)
        })
    }
  }
}
</script>
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
/*input {
  background-color: #000
}*/
h1#blackh1 {
  color: black;
}
h2#blackh2 {
  color: black;
}
</style>
