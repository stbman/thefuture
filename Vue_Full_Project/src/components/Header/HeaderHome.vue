<template>
  <header class="app-header navbar">
    <button class="navbar-toggler mobile-sidebar-toggler d-lg-none" type="button" @click="mobileSidebarToggle">
      <span class="navbar-toggler-icon"></span>
    </button>
    <b-link class="navbar-brand" to="#"></b-link>
    <button class="navbar-toggler sidebar-toggler d-md-down-none" type="button" @click="sidebarToggle">
      <span class="navbar-toggler-icon"></span>
    </button>
    <b-navbar-nav class="ml-auto">
      <b-nav-item>

    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal" @click="connectLinkedln">
      Connect with Linkedln
    </button>

    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">Connect With Linkedln</h5>
            <!-- <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button> -->
          </div>
          <div class="modal-body">
            <input type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="basic-addon1">
            <input type="password" class="form-control" placeholder="Password" aria-label="Username" aria-describedby="basic-addon1">
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal" @click="closeModal">Close</button>
            <button type="button" class="btn btn-primary" @click="connecting">Connect</button>
          </div>
        </div>
      </div>
    </div>

      </b-nav-item>

    </b-navbar-nav>

  </header>
</template>
<script>
import HeaderDropdown from './HeaderDropdown.vue'
import router from '../../router'

export default {
  name: 'HeaderHome',
  components: {
    HeaderDropdown
  },
  methods: {
    sidebarToggle (e) {
      e.preventDefault()
      document.body.classList.toggle('sidebar-hidden')
    },
    sidebarMinimize (e) {
      e.preventDefault()
      document.body.classList.toggle('sidebar-minimized')
    },
    mobileSidebarToggle (e) {
      e.preventDefault()
      document.body.classList.toggle('sidebar-mobile-show')
    },
    asideToggle (e) {
      e.preventDefault()
      document.body.classList.toggle('aside-menu-hidden')
    },
    connectLinkedln (e) {
      e.preventDefault()
      console.log('Connect to Linkedln')
      $('#exampleModal').addClass('show')
      $("#exampleModal").css({ 'display': 'block' })
    },
    closeModal (e) {
      e.preventDefault()
      console.log('Connect to Linkedln')
      $('#exampleModal').removeClass('show')
      $("#exampleModal").css({ 'display': 'none' })
    },
    connecting (e) {
      e.preventDefault()
      console.log('Connecting')
      $('#exampleModal').removeClass('show')
      $('#exampleModal').css({ 'display': 'none' })

      router.push('/dashboard')
    }
  }
}
</script>
