<template>
  <div class="animated fadeIn">
    <b-row>
      <b-col sm="6" lg="3">
      <h2>My Skills Overview</h2>
      </b-col>
    </b-row>
    <b-row>
      <b-col sm="6" lg="3">
        <b-card no-body class="bg-primary">
          <b-card-body class="pb-0">
            <b-dropdown class="float-right" variant="transparent p-0" right>
              <template slot="button-content">
                <i class="icon-star"></i>
              </template>
              <b-dropdown-item>Sign Up</b-dropdown-item>
              <b-dropdown-item>Add to Wishlist</b-dropdown-item>
              <b-dropdown-item>Not Interested</b-dropdown-item>
            </b-dropdown>
            <h4 class="mb-0">Web Programming</h4>
            <p>You been recommend by <b>12 friends!</b></p>
          </b-card-body>
          <card-line1-chart-example class="chart-wrapper px-3" style="height:70px;" height="70"/>
        </b-card>
      </b-col>
      <b-col sm="6" lg="3">
        <b-card no-body class="bg-info">
          <b-card-body class="pb-0">
            <b-dropdown class="float-right" variant="transparent p-0" right no-caret>
              <template slot="button-content">
                <i class="icon-star"></i>
              </template>
              <b-dropdown-item>Sign Up</b-dropdown-item>
              <b-dropdown-item>Add to Wishlist</b-dropdown-item>
              <b-dropdown-item>Not Interested</b-dropdown-item>
            </b-dropdown>
            <h4 class="mb-0">Negotiation Technique</h4>
            <p>Newly recommended by <b>Aaron Tan</b>!</p>
          </b-card-body>
          <card-line2-chart-example class="chart-wrapper px-3" style="height:70px;" height="70"/>
        </b-card>
      </b-col>
      <b-col sm="6" lg="3">
        <b-card no-body class="bg-warning">
          <b-card-body class="pb-0">
            <b-dropdown class="float-right" variant="transparent p-0" right>
              <template slot="button-content">
                <i class="icon-star"></i>
              </template>
              <b-dropdown-item>Sign Up</b-dropdown-item>
              <b-dropdown-item>Add to Wishlist</b-dropdown-item>
              <b-dropdown-item>Not Interested</b-dropdown-item>
            </b-dropdown>
            <h4 class="mb-0">UI / UX</h4>
            <p>Most recommendation after completing <b>Mastering UI</b>!</p>
          </b-card-body>
          <card-line3-chart-example class="chart-wrapper" style="height:70px;" height="70"/>
        </b-card>
      </b-col>
      <b-col sm="6" lg="3">
        <b-card no-body class="bg-danger">
          <b-card-body class="pb-0">
            <b-dropdown class="float-right" variant="transparent p-0" right>
              <template slot="button-content">
                <i class="icon-star"></i>
              </template>
              <b-dropdown-item>Sign Up</b-dropdown-item>
              <b-dropdown-item>Add to Wishlist</b-dropdown-item>
              <b-dropdown-item>Not Interested</b-dropdown-item>
            </b-dropdown>
            <h4 class="mb-0">Social Media Engineering</h4>
            <p>Your skill is in hot demand right now!</p>
          </b-card-body>
          <card-bar-chart-example class="chart-wrapper px-3" style="height:70px;" height="70"/>
        </b-card>
      </b-col>
    </b-row>

    <b-row>
      <b-col sm="6" lg="3">
      <h2>Recommended Skills</h2>
      </b-col>
    </b-row>
    <b-row>
      <b-col sm="6" lg="3">
        <div class="social-box facebook">
          <div class="bg-danger">
            <h4 class="mb-0">Web Backend Programming</h4>
            <p>You have no related skill in this field! Aquring this skill can drasticly improve your overall competency!</p>
          </div>
          <ul>
            <li>
              <strong>23</strong>
              <span>Friends with this skill</span>
            </li>
            <li>
              <strong>59</strong>
              <span>Companies Seeking</span>
            </li>
          </ul>
        </div><!--/.social-box-->
      </b-col>
      <b-col sm="6" lg="3">
        <div class="social-box twitter">
          <div class="bg-info">
            <h4 class="mb-0">UI Art Creation</h4>
            <p>You are very highly reated in this field! Just a bit more and you are a leader in this field among your friends!</p>
          </div>
          <ul>
            <li>
              <strong>72</strong>
              <span>Friends with this skill</span>
            </li>
            <li>
              <strong>4th</strong>
              <span>best ranked in your circle</span>
            </li>
          </ul>
        </div><!--/.social-box-->
      </b-col>
      <b-col sm="6" lg="3">
        <div class="social-box linkedin">
          <div class="bg-primary">
            <h4 class="mb-0">Angular JS</h4>
              <p>Your competency with <b>React</b> is a hit! You might want to pick up this skill as well!</p>
          </div>
          <ul>
            <li>
              <strong>61</strong>
              <span>Friends with this skill</span>
            </li>
            <li>
              <strong>80%</strong>
              <span>Companies require this skill</span>
            </li>
          </ul>
        </div><!--/.social-box-->
      </b-col>
      <b-col sm="6" lg="3">
        <div class="social-box google-plus">
          <div class="bg-warning">
            <h4 class="mb-0">Baking Bread</h4>
            <p>Your recent activities happens to be around <b>baking</b>! Why not pick it up professionally?</p>
          </div>
          <ul>
            <li>
              <strong>23</strong>
              <span>Friends with this skill</span>
            </li>
            <li>
              <strong>16</strong>
              <span>Related activity this week</span>
            </li>
          </ul>
        </div><!--/.social-box-->
      </b-col>
    </b-row>


    <b-row>
      <b-col md="12">
        <b-card header="Your Friends">

          <b-table class="mb-0 table-outline" responsive="sm" hover :items="tableItems" :fields="tableFields" head-variant="light" align="left">
            <div slot="avatar" class="avatar" slot-scope="item">
              <img :src="item.value.url" class="img-avatar" alt="">
              <span class="avatar-status" v-bind:class="{ 'bg-success': item.value.status == 'success',  'bg-warning': item.value.status == 'warning', 'bg-danger': item.value.status == 'danger', 'bg-secondary': item.value.status == '' }"></span>
            </div>
            <div slot="user" slot-scope="item">
              <div>{{item.value.name}}</div>
              <div class="small text-muted">
                <span>
                  <template v-if="item.value.new">New</template>
                  <template v-else>Recurring</template>
                </span> | Registered: {{item.value.registered}}
              </div>
            </div>
            <div slot="country" slot-scope="item">
              <div>{{item.value.name}}</div>
            </div>
            <!-- <i slot="country" class="h4 mb-0" :class="flag(item.value.flag)" slot-scope="item" :title="item.value.flag" :id="item.value.flag"></i>
            <i class="flag-icon flag-icon-pw h1" title="pw" id="pw"></i> -->
            <div slot="usage" slot-scope="item">
              <div class="clearfix">
                <div class="float-left">
                  <strong>{{item.value.value}}%</strong>
                </div>
                <div class="float-right">
                  <small class="text-muted">{{item.value.period}}</small>
                </div>
              </div>
              <b-progress height={} class="progress-xs" v-model="item.value.value" :variant="variant(item.value.value)"></b-progress>
            </div>
            <!-- <i slot="payment" slot-scope="item" :class="item.value.icon" style="font-size:24px"></i> -->
            <div slot="activity" slot-scope="item">
              <div class="small text-muted">Last lesson</div>
              <strong>{{item.value}}</strong>
            </div>
          </b-table>
        </b-card>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import CardLine1ChartExample from './dashboard/CardLine1ChartExample'
import CardLine2ChartExample from './dashboard/CardLine2ChartExample'
import CardLine3ChartExample from './dashboard/CardLine3ChartExample'
import CardBarChartExample from './dashboard/CardBarChartExample'
import MainChartExample from './dashboard/MainChartExample'
import SocialBoxChartExample from './dashboard/SocialBoxChartExample'
import CalloutChartExample from './dashboard/CalloutChartExample'
import { Callout } from '../components/'

export default {
  name: 'dashboard',
  components: {
    Callout,
    CardLine1ChartExample,
    CardLine2ChartExample,
    CardLine3ChartExample,
    CardBarChartExample,
    MainChartExample,
    SocialBoxChartExample,
    CalloutChartExample
  },
  data: function () {
    return {
      selected: 'Month',
      tableItems: [
        {
          avatar: { url: 'static/img/avatars/1.jpg', status: 'success' },
          user: { name: 'Charissa Tang', new: true, registered: 'Jan 1, 2018' },
          country: { name: 'Back End Web Development', flag: 'us' },
          usage: { value: 50, period: 'May 11, 2018 - Jul 10, 2018' },
          payment: { name: 'Mastercard', icon: 'fa fa-cc-mastercard' },
          activity: '13 May 2018'
        },
        {
          avatar: { url: 'static/img/avatars/2.jpg', status: 'danger' },
          user: { name: 'Rebecca Lee', new: false, registered: 'Feb 10, 2017' },
          country: { name: 'Search Engine Optimisation', flag: 'br' },
          usage: { value: 22, period: 'Apr 11, 2018 - Sept 10, 2018' },
          payment: { name: 'Visa', icon: 'fa fa-cc-visa' },
          activity: '10 May 2018'
        },
        {
          avatar: { url: 'static/img/avatars/3.jpg', status: 'warning' },
          user: { name: 'Jonathan Lim', new: true, registered: 'Mar 20, 2018' },
          country: { name: 'Beginner Pop Piano Lessons', flag: 'in' },
          usage: { value: 74, period: 'Apr 6, 2018 - Sept 10, 2018' },
          payment: { name: 'Stripe', icon: 'fa fa-cc-stripe' },
          activity: '9 April 2018'
        },
        {
          avatar: { url: 'static/img/avatars/4.jpg', status: '' },
          user: { name: 'Melissa Chew', new: true, registered: 'Dec 13, 2016' },
          country: { name: 'Programming Fundamentals', flag: 'fr' },
          usage: { value: 98, period: 'Feb 1, 2018 - Jun 10, 2018' },
          payment: { name: 'PayPal', icon: 'fa fa-paypal' },
          activity: '20 Feb 2018'
        },
        {
          avatar: { url: 'static/img/avatars/5.jpg', status: 'success' },
          user: { name: 'Alicia Tan', new: true, registered: 'May 1, 2018' },
          country: { name: 'Basic Pet Groomer', flag: 'es' },
          usage: { value: 22, period: 'May 6, 2018 - Aug 10, 2018' },
          payment: { name: 'Google Wallet', icon: 'fa fa-google-wallet' },
          activity: '8 May 2018'
        },
        {
          avatar: { url: 'static/img/avatars/6.jpg', status: 'danger' },
          user: { name: 'David Lee', new: true, registered: 'Nov 1, 2017' },
          country: { name: 'Data Analytics using R', flag: 'pl' },
          usage: { value: 43, period: 'Feb 2, 2018 - Jul 10, 2018' },
          payment: { name: 'Amex', icon: 'fa fa-cc-amex' },
          activity: '20 March 2018'
        }
      ],
      tableFields: {
        avatar: {
          label: '<i class="icon-people"></i>'
        },
        user: {
          label: 'Friend'
        },
        country: {
          label: 'Current Course'
        },
        usage: {
          label: 'Completion'
        },
        activity: {
          label: 'Last Lesson'
        }
      }
    }
  },
  methods: {
    variant (value) {
      let $variant
      if (value <= 25) {
        $variant = 'info'
      } else if (value > 25 && value <= 50) {
        $variant = 'success'
      } else if (value > 50 && value <= 75) {
        $variant = 'warning'
      } else if (value > 75 && value <= 100) {
        $variant = 'danger'
      }
      return $variant
    },
    flag (value) {
      return 'flag-icon flag-icon-' + value
    }
  }
}
</script>
