<template>
  <div class="all">
    <b-container class="form-container" fluid id="container">

      <b-row class ="top" id="top">
        <b-col>
          <br />
          <h3 id="title">Step 1</h3>
          <h1 id="step">Welcome!</h1>
        </b-col>
      </b-row>


      <b-row class ="mid" id="row">
        <b-col>
          <span class="completed" id="dot1">
          <svg class="icon" xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"><path d="M0 0h24v24H0V0z" fill="none"/><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 17h-2v-2h2v2zm2.07-7.75l-.9.92C13.45 12.9 13 13.5 13 15h-2v-.5c0-1.1.45-2.1 1.17-2.83l1.24-1.26c.37-.36.59-.86.59-1.41 0-1.1-.9-2-2-2s-2 .9-2 2H8c0-2.21 1.79-4 4-4s4 1.79 4 4c0 .88-.36 1.68-.93 2.25z"/></svg>
          </span>
        </b-col>

        <b-col>
          <span class="dot" id="dot2">
          <svg class="icon" xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"><path d="M0 0h24v24H0V0z" fill="none"/><path d="M21 3h-6.18C14.4 1.84 13.3 1 12 1s-2.4.84-2.82 2H3v18h18V3zm-9 0c.55 0 1 .45 1 1s-.45 1-1 1-1-.45-1-1 .45-1 1-1zm2 14H7v-2h7v2zm3-4H7v-2h10v2zm0-4H7V7h10v2z"/></svg>          </span>
        </b-col>

        <b-col>
          <span class="dot" id="dot3">
          <svg class="icon" xmlns="http://www.w3.org/2000/svg" enable-background="new 0 0 24 24" height="24" viewBox="0 0 24 24" width="24"><g><rect fill="none" height="24" width="24"/></g><g><g><g><path d="M23,8c0,1.1-0.9,2-2,2c-0.18,0-0.35-0.02-0.51-0.07l-3.56,3.55C16.98,13.64,17,13.82,17,14c0,1.1-0.9,2-2,2s-2-0.9-2-2 c0-0.18,0.02-0.36,0.07-0.52l-2.55-2.55C10.36,10.98,10.18,11,10,11s-0.36-0.02-0.52-0.07l-4.55,4.56C4.98,15.65,5,15.82,5,16 c0,1.1-0.9,2-2,2s-2-0.9-2-2s0.9-2,2-2c0.18,0,0.35,0.02,0.51,0.07l4.56-4.55C8.02,9.36,8,9.18,8,9c0-1.1,0.9-2,2-2s2,0.9,2,2 c0,0.18-0.02,0.36-0.07,0.52l2.55,2.55C14.64,12.02,14.82,12,15,12s0.36,0.02,0.52,0.07l3.55-3.56C19.02,8.35,19,8.18,19,8 c0-1.1,0.9-2,2-2S23,6.9,23,8z"/></g></g></g></svg>          </span>
        </b-col>

        <b-col>
          <span class="dot" id="dot4">
          <svg class="icon" xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"><path d="M6.99 11L3 15l3.99 4v-3H14v-2H6.99v-3zM21 9l-3.99-4v3H10v2h7.01v3L21 9z"/><path d="M0 0h24v24H0z" fill="none"/></svg>          </span>
        </b-col>

        <b-col>
          <span class="dot" id="dot5">
          <svg class="icon" xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 0 24 24" width="24"><path d="M0 0h24v24H0V0z" fill="none"/><path d="M9 16.2L4.8 12l-1.4 1.4L9 19 21 7l-1.4-1.4L9 16.2z"/></svg>
          </span>
        </b-col>

      </b-row>
      <b-container class="bottom">
        <b-row>
          <div class="form-area" id="p1" v-if="counter === 0">
          Welcome to B-On-Time!<br /><br />
          This app will help you to better manage the hours of your employees. <br />
          This setup wizard is for me to better know your company!<br />
          Press next to begin our journey!
          </div>

          <div align="center" class="form-area" id="p2" v-if="counter === 1">
            <b-form-input
              id="input-1"
              v-model="form.pass"
              type="password"
              placeholder="Enter password"
              :state="(pActive) ? password_name_state : null"
              v-on:click="activatePassword"
            />
            <br />
            <b-form-input
              id="input-1"
              v-model="form.Repass"
              type="password"
              required
              placeholder="Re-enter password"
              :state="(vpActive) ? verifyPass_name_state : null"
              v-on:click="activateVerifyPassword"
            />
            <br />
            <b>Note*</b> this will serve as your master password <br /> so choose wisely.
          </div>

          <div align="center" class="form-area" id="p3" v-if="counter === 2">
          <b-form-input
            id="input-1"
            v-model="form.fqdn"
            type="text"
            required
            placeholder="Enter the FQDN"
            :state="(fqdnActive) ? fdqn_name_state : null"
            v-on:click="activatefdqn"
            />
            <br />
          <b-form-input
            id="input-1"
            v-model="form.ipAddy"
            type="text"
            required
            placeholder="Enter the IP Adress"
            :state="(ipActive) ? ip_name_state : null"
            v-on:click="activateip"
            />
            <br />
          <b-form-input
            id="input-1"
            v-model="form.port"
            type="number"
            required
            placeholder="Enter the port #"
            :state="(portActive) ? port_name_state : null"
            v-on:click="activatePort"
            />
          </div>

           <div align="center" class="form-area" id="p4" v-if="counter === 3">
          <b-form-input
            id="input-1"
            v-model="form.databaseName"
            type="text"
            required
            placeholder="Enter the name of your Database"
            :state="(databaseActive) ? database_name_state : null"
            v-on:click="activateDataBase"
            />
            <br />
            <b-form-input
            id="input-1"
            v-model="form.postSQLUser"
            type="text"
            required
            placeholder="Enter your user name"
            :state="(userActive) ? user_name_state : null"
            v-on:click="activateUser"
            />
            <br />
            <b-form-input
            id="input-1"
            v-model="form.postSQLPass"
            type="password"
            required
            placeholder="Enter your password"
            :state="(sqlPassActive) ? sqlPass_name_state : null"
            v-on:click="activatesqlPass"
            />
          </div>
          
           <div align="center" class="form-area" id="p5" v-if="counter === 4">
            <br />
          Done! Your account has been created, <br />
          please sign in with the user name you received and your password.
          <br />
          <br />

          We can't wait to start working with you! :)
          </div>

        </b-row>
        <b-row>
          <b-col>
            <md-button class="md-primary next-button" v-on:click="goForward" id="button">Next</md-button>
            <md-button class="md-primary back-button" v-on:click="goBack" id="button">Back</md-button>
          </b-col>
        </b-row>
      </b-container>
    </b-container>

  </div>
</template>

<script>
export default {
  name: 'hello',

  data: function() {
  return {
    show: 1,
    pActive: false,
    vpActive: false,
    fqdnActive : false,
    ipActive: false,
    portActive: false,
    databaseActive: false,
    userActive: false,
    sqlPassActive: false,
    counter: 0,

    form: {
      pass: '',
      Repass: '',
      fqdn: '',
      ipAddy: '',
      port: '',
      databaseName: '',
      postSQLUser: '',
      postSQLPass: ''
    }
  };
},
  computed: {
    password_name_state() {
      return this.form.pass.length >= 8 ? true : false
    },
    verifyPass_name_state() {
      var pass = this.form.pass
      var verifyPass = this.form.Repass
      return ((pass == verifyPass) && (verifyPass.length >= 8))
    },
    fdqn_name_state() {
      return this.form.fqdn.length >= 1 ? true : false
    },
    ip_name_state() {
      return this.form.ipAddy.length >= 1 ? true : false
    },
    port_name_state() {
      return this.form.port.length >= 1 ? true : false
    },
    database_name_state() {
      return this.form.databaseName.length >= 1 ? true : false
    },
    user_name_state() {
      return this.form.postSQLUser.length >= 1 ? true : false
    },
    sqlPass_name_state() {
      return this.form.postSQLPass.length >= 1 ? true : false
    }
  },
  methods: {
    goForward: function () {
      if (this.counter == 0)
      {
        document.getElementById("dot2").className = "completed"
        document.getElementById("title").innerHTML = "Step " + (this.counter + 1);
        document.getElementById("step").innerHTML = "Set a V.I.P password";
        this.counter++;
      }

      else if (this.counter == 1)
      {
        if (!((this.form.pass == this.form.Repass) && (this.form.Repass.length >= 8))) {return;}
        document.getElementById("dot3").className = "completed"
        document.getElementById("title").innerHTML = "Step " + (this.counter + 1);
        document.getElementById("step").innerHTML = "Domain info now";
        this.counter++;
      }

      else if (this.counter == 2)
      {
        if (!((this.form.ipAddy.length >= 1) && (this.form.fqdn.length >= 1) && (this.form.port.length >= 1))) {return;}
        document.getElementById("dot4").className = "completed"
        document.getElementById("title").innerHTML = "Step " + (this.counter + 1);
        document.getElementById("step").innerHTML = "Database info please";
        this.counter++;
      }

      else if (this.counter == 3)
      {
        if (!((this.form.databaseName.length >= 1) && (this.form.postSQLUser.length >= 1) && (this.form.postSQLPass.length >= 1))) {return;}
        document.getElementById("dot5").className = "completed"
        document.getElementById("row").style.background = "linear-gradient(#7750CA 50%, #66AD83 50%)";
        document.getElementById("title").innerHTML = ""
        document.getElementById("step").innerHTML = "Thanks!";
        this.counter++;
        alert(JSON.stringify(this.form))
      }
    },
    goBack: function () {
      if (this.counter == 0) return;
      this.counter--;
      if (this.counter == 0)
      {
        document.getElementById("dot2").className = "dot"
        document.getElementById("title").innerHTML = "Step " + (this.counter + 1);
        document.getElementById("step").innerHTML = "Set a V.I.P password";
      }

      else if (this.counter == 1)
      {
        document.getElementById("dot3").className = "dot"
        document.getElementById("title").innerHTML = "Step " + (this.counter + 1);
        document.getElementById("step").innerHTML = "Domain info now";
      }

      else if (this.counter == 2)
      {
        document.getElementById("dot4").className = "dot"
        document.getElementById("title").innerHTML = "Step " + (this.counter + 1);
        document.getElementById("step").innerHTML = "Database info please";
      }

      else if (this.counter == 3)
      {
        document.getElementById("dot5").className = "dot"
        document.getElementById("row").style.background = "linear-gradient(#7750CA 50%, #66AD83 50%)";
        document.getElementById("title").innerHTML = ""
        document.getElementById("step").innerHTML = "Thanks!";
      }
    },
    activatePassword() { this.pActive = true },
    activateVerifyPassword() {this.vpActive = true},
    activatefdqn() {this.fqdnActive = true},
    activateip() {this.ipActive = true},
    activatePort() {this.portActive = true},
    activateDataBase() {this.databaseActive = true},
    activateUser() {this.userActive = true},
    activatesqlPass() {this.sqlPassActive = true}
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.all
{
  position: relative;
}


.form-container {
  border: 1px solid black;
  position: relative;
  width: 556px;
  height: 742px;
  top: 50px;
  background: #FFFFFF;
  box-shadow: 5px 10px;
}

.icon
{
  margin-top: 0.8mm;
}

.top
{
  position: absolute;
  width: 554px;
  height: 150px;
  color: white;
  background: #7750CA;
}

.next-button
{
  position: absolute;
  right: 0;
  /* background: blue; */
  margin-top: 20%;
  /* margin-left: 150%; */
}

.back-button
{
  position: absolute;
  left: 0;
  /* background: blue; */
  margin-top: 20%;
  /* margin-left: 150%; */
}

.mid
{
  position: absolute;
  width: 554px;
  height: 30px;
  top: 140px;
  background: linear-gradient(#7750CA 50%, #fff 50%)
}

.completed {
  height: 30px;
  width: 30px;
  background-color: #fff;
  border-radius: 50%;
  display: inline-block;
  background: #66AD83;
}

.bottom
{
  position: absolute;
  width: 525px;
  height: 500px;
  top: 170px;
  margin-right: 10cm;
  /* padding: 200px; */
  /* background: black; */
}

.dot {
  
  height: 30px;
  width: 30px;
  background-color: #fff;
  border-radius: 50%;
  display: inline-block;
}

p {
  margin-top: 10%;
  /* margin-left: 8%; */
  padding: 100px;
  text-align: center;
  /* background:blue; */
}

.form-area  {
  font-size: 16pt;
  text-align: justify;
  line-height: 25pt;
  width: 525px;
  height: 350px;
  margin-top: 12%;
  margin-left: 5%;
  margin-right: 5%;
}

</style>