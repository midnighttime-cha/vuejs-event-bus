# event-bus

## Create Component: Body.vue
```javascript
<template>
  <div>
    <strong>
      <font size="8px">Body: {{text}}</font>
    </strong>
    <br />
    <button @click="onEvent()">Click Here..</button>
  </div>
</template>

<script>
export default {
  data: () => ({
    textBody: "?"
  }),

  methods: {
    onEvent() {
      this.textBody = "Hello Bangkok";
      this.$EventBus.$emit("hello-bangkok", this.textBody);
    }
  }
};
</script>
```

## Create Component: Header.vue
```javascript
<template>
  <div>
    <strong>
      <font size="8px">Header: {{textHeader}}</font>
    </strong>
  </div>
</template>

<script>
export default {
  data: () => ({
    textHeader: "?"
  }),

  mounted() {
    this.$EventBus.$on("hello-bangkok", param1 => {
      console.log("Receive event.", param1);
      this.textHeader = param1;
    });
  }
};
</script>
```

## Create Component: Footer.vue
```javascript
<template>
  <div>
    <strong>
      <font size="8px">Footer: {{textFooter}}</font>
    </strong>
  </div>
</template>

<script>
export default {
  data: () => ({
    textFooter: "?"
  }),
  mounted() {
    this.$EventBus.$on("hello-bangkok", param1 => {
      console.log("Receive event.", param1);
      this.textFooter = param1;
    });
  }
};
</script>
```

## Run: yarn serve
<img alt="Vue logo" src="https://lh3.googleusercontent.com/HLi4JdrtkYVucq2h5fMLmZP9YVSf_rkZjfoUQBnPtqUZiqOKLJM-KSqWM2rh6akXFCkVa6xweayw_tKMEcgEijl9J5p2pWYXF6GKZV-52dp8L5RqxXdNbl2_J3Geqft4R4rudRQ8iPvXBlknRc8TSq0zsZxdSjaGmWqEQ8zj7IDWVMeMtgJgS9tTSZtwTZuE0ZqptrQxeyq15njYvFsD-YwpxUaMD0V7wRbgIBugU5Hf-8n1JKh8C6sG6CRVn8IzLOUGY-zljC76BhVpsQDYBxodFaVy8Bbjl75HvmK4e1gjYQn-dTerdvy46u-dnIUHhfP_dQOP2QN3VtP7d-QimAuyiGsGUrX0FbHMsfdaphpAAGPw4W_Lb1s9GqoBJJAURp6zNdlNreLDD1dXxz0SP9NyR4KBYGoAZ8WVJSSx0353hXFX8dscIKd6S6cY11zignuQzUw1TB7vMmS6OWPgnsE3pGBylDmurgO5lmjGOaoFWepnCYxQw4kZ5SIyqq8MajBemNtnRsfOrSMrWBPAvm7vvKHNbV148ttnLiOEDg7TOizOVFng3m6x7mqTyvWgALu0uKP98vLnL5NLeUcLnBomrQfzqswK7IK6Y4uVGWpyRUsp006crz1xzNjcUo1u30SZtPqT-OO8U33O2SS22vryXuoyuATVo56336to2shXPXBcWAbR7oSkAyd6=w380-h269-no?authuser=0" />

## Click Button in Body.vue
<img alt="Vue logo" src="https://lh3.googleusercontent.com/JCgvttUNd_KjuWNqjla0u1zlJiQpoXk-MFxV0PmtpUzOG2vD8zrQwrj19OL7aL5qT-T9QcmThBn60FUyaSYNBgsmthDVU960nYKtj35QEC_iHCiStPIHnK2RG1OF9iSK0crbkonYDz9TGv_k2NcTN8384cEyDQx5JHsMvQoAvSllfKrfsCqJm--UnrMV_MOgqG9eEVGJ95zsNoqesFHOXuhb0dHFJ1ZI8lpzPFf85g9x8q--iT1OO8jfZiRApYccwLDNl7c32nAZLU86uDePH-uwAjDFF36bOPsRpAbZWI7DQlhC5Vnywf8SB0moG7RJA9Nb2Pmby3t1oPPylnisyXlRwOO1fto_EKwKWK_EaBnx03DfFI4etuNEDuP8sr_Ef1hWjqNZdp-MmhjHqM6pGkEfIINDjHu4EC_8WutQF16DPArW-R7u3xGekabwvMu2ipYw_7-cnB6EGT4inzPZCMDBaMCzv-rfrU1MNlFtK5HXHUEOXASgowl1UqKJcF4azMwg_DahXZESRH0SXtUG-dXB9cc2qNw2s1Ubgkchna6qu7quvli8mG_1TQbTAAy8n0QfCgLT7VjRJtfxs5DCZ6JXtDt9netTL6ox5Eijx6OI9QJRswEQxNr5aI8LAbse9y3NKWR4BpJHBNpPbjlFpeqxQd3lESlq7_BP33OO6g2wOnzZgXIIRxH1HOVy=w748-h250-no?authuser=0" />