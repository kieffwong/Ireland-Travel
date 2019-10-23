
<template>
  <div class="form-group">
    <label for="name">Your Name </label>

    <input
      id="name" 
      v-model="userData.name" 
      type="text" 
      class="form-control"
    >

    <label for="email">Your Email Address</label>
    <input 
      id="email"
      v-model="userData.email"
      type="text"
      class="form-control"
    >
	
    <label for="budget">Your Budget per Day </label>
    <input
      id="budget"
      v-model.number="userData.budget"
      min="100"
      max="10000"
      type="number"
      class="form-control"
    >
    <label for="message">Travel Plans</label>
    <textarea
      id="message"
      v-model="message"
      rows="5"
      class="form-control"
    />
    <label for="pickup">
      <input
        v-for="item in checkboxOptions"
        id="pickup"
        :key="item"
        type="checkbox"
        value="pickup"
      > Pick-up Service</label>
    <br>
    <label for="gadgets">
      <input
        v-for="item in checkboxOptions"
        id="gadgets"
        :key="item"
        type="checkbox"
        value="gadgets"
      > Go pro, Electric Scooters, Drone</label>
    <br>
    <label for="filmmaking">
      <input
        v-for="item in checkboxOptions"
        id="filmmaking"
        :key="item"
        type="checkbox"
        value="filmmaking"
      > Create Your Travel Video</label>
    <br>
    <label for="museum">
      <input
        v-for="item in checkboxOptions"
        id="museum"
        :key="item"
        type="checkbox"
        value="museum"
      > Museum / Church </label>
    <br>
    <label for="scnery">
      <input
        v-for="item in checkboxOptions"
        id="scnery"
        :key="item"
        type="checkbox"
        value="scnery"
      > Natural Scenery </label>
    <br>
    <label for="adventures">
      <input
        v-for="item in checkboxOptions"
        id="adventures"
        :key="item"
        type="checkbox"
        value="adventures"
      > Adventures, e.g. Hiking, Sports activities </label>
    <button
      class="btn btn-primary"
      @click.prevent="submitted"
    >
      Send Enquiry
    </button>
    <br>
    <div
      v-if="isSubmitted"
      class="card"
    >
      <div class="card-body">
        <h4 class="card-title">
          Form Data
        </h4>
        <p>Name: <b>{{ userData.name }}</b></p>
 
        <p>Mail: <b>{{ userData.email }}</b></p>
        
        <p>Budget: <b>{{ userData.budget }}</b></p>
        <p style="white-space: pre">
          Travel Plan: <b>{{ message }}</b>
        </p>
        <p>Interest Areas:</p>
        <ul>
          <li
            v-for="item in checkboxOptions"
            :key="item"
          >
            <b>{{ item }}</b>
          </li>
        </ul>
      </div>
    </div>  
  </div>
</template>


<script>
    export default {
        data() {
            return {
                userData: {
                    email: '',
					Name: '',
					budget: '',
				},
				message: 'Describe your travel plans..',
				checkboxOptions: [item],
				isSubmitted: false
            }
		},
		methods: {
            submitted() {
                this.isSubmitted = true;
            }
	}
	}
	
</script>

<style>

</style>