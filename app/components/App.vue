<template>
    <Page>
        <ActionBar title="Welcome to NativeScript-Vue!"/>
        <StackLayout class="content-wrapper">
            <Label class="header" :text="msg" col="0" row="0"/>
            <Label class="estimated-wait" :text="estimatedWait" />
            <TextField class="input" autocorrect="false" hint="Name" text="" returnKeyType="done"/>
            <TextField class="input" autocorrect="false" hint="# of Customers" text="" returnKeyType="send"/> 
            <Label class="current-date" :text="timeNow" col="0" row="0"/>
        </StackLayout>
    </Page>
</template>

<style scoped>
.content-wrapper {
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 50px;
}
.header {
    text-transform: capitalize;
    margin-bottom: 20px;
    font-size: 30px;
    font-weight: bold;
}

TextField {
  border-width: 1;
  border-color: black;
  text-align: center;
  height: 80px;
  margin: 15px 0;
}

ActionBar {
  background-color: #53ba82;
  color: #ffffff;
}

.message {
  vertical-align: center;
  text-align: center;
  font-size: 20;
  color: #333333;
}
</style>

<script>
function getCurrentDateString() {
  let dateObject = new Date();
  let months = [
    "January",
    "Feburary",
    "March",
    "April",
    "May",
    "June",
    "July",
    "August",
    "September",
    "October",
    "November",
    "December"
  ];
  let currentMonth = months[dateObject.getMonth()];
  let currentDate = dateObject.getDate();

  return `${currentMonth} ${currentDate}`;
}

function getEstimatedWaitTime() {
    // get total people waiting from API
    // estimated it based on time (breakfast/lunch/dinner)
    return 16;
}

export default {
  data() {
    return {
      msg: "Please sign in",
      timeNow: getCurrentDateString(),
      estimatedWait: 'Estimated wait time: ' + getEstimatedWaitTime() + 'min',
    };
  }
};
</script>
