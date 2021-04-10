<template>
  <div class="hello">
    
    <div class="outer-card">

    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Personal</label>
   
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">Bank Details</label>
   
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">Documents</label>
   


    <div class="tab content1">
      
    Tab1 Content

    </div>
    
    <div class="tab content2">
        <div class="tab-title">
        <p>{{msg}}</p>
        </div>

        <div class="collapsible">
            <section class="accordion" >
              <article class="message" :class="accordionClasses">
                <!-- <input type="checkbox" name="collapse" id="handle1" > -->
                
                <div class="accordion-header" @click="toggleAccordion">
                  <div>
                   <label for="handle1">Blue-Sea Marine Services</label>
                   <p>Bank of Singapore - xxxxxxxxxxxxxxxxxxx9224</p>
                   </div>
                    <div class="icon-header">
                      <p><a id="angle-icon" class="ti-angle-down"></a></p>
                   </div>
                </div>
              
                <div class="accordion-outer">
                  <div class="accordion-message">
                  <div class="table-section">
                      <p class="title-format" >Account Type</p>
                      <p>Current</p>
                      <p class="title-format" >Bank Name</p>
                      <p>SBM Bank (Marutius) LTD</p>
                  </div>
                  <div class="table-section">
                    <p class="title-format" >Name as per Bank Account</p>
                    <p>LCV Trade Finance Fund</p>
                    <p class="title-format">Account Number</p>
                    <p>500105659541525</p>
                  </div>
                  </div>
                     <p class="title-format" >To change your bank account details, contact <a href="">ir@siamvalidus.co.th </a> </p>
                  </div>
             
                 </article>
            </section>
        </div>

    </div>

    <div class="tab content3">Tab3 Contents</div>
 
</div>
   
    
  </div>
</template>

<script>
export default {
  name: 'TabComp',
  data () {
    return {
      msg: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
      isOpen: false
    }
  },
  
  methods: {
    toggleAccordion: function() {
      this.isOpen = !this.isOpen;
    }
  },
  computed: {
    accordionClasses: function() {
      return {
        'is-closed': !this.isOpen,
      
      };
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

p {
    color: #696969;
    font-size: 11px;
}

h3 {
    color: #4a4a4a;
}


.outer-card {
    padding: 5px;
   
}

.accordion-header{
  max-width: 250px;
  padding: 5px;
  cursor: pointer;
  display: flex;
 
}

.icon-header{
  padding: 10px;
}


.accordion-outer {
    padding: 0;
    max-width: 485px;
    overflow: hidden;
    transition: 0.3s ease all;
    background-color: white;
    position: relative;
}

  .accordion-message   {
    padding: 0;
    max-width: 485px;
    overflow: hidden;
    transition: 0.3s ease all;
    background-color: white;
    display: flex;
    position: relative;
  
  }

 .table-section{
  
  flex-basis: 50%;
     
 }

 .table-float {
   
   float: left;
 }

  .is-closed .accordion-message {
    max-height: 0;
  }
  .is-closed .accordion-outer{
    max-height: 0;
  }
  .accordion label {
    display: block;
  }

  input { display: none; }
  input + label { display: inline-block }

  input ~ .tab { display: none }
  #tab1:checked ~ .tab.content1,
  #tab2:checked ~ .tab.content2,
  #tab3:checked ~ .tab.content3 { display: block; }



  input + label {             /* box with rounded corner */
   
    background: white;
    padding: 4px ;
    border-radius: 4px 4px 0 0;
    position: relative;
    top: 1px;
  }
  input:checked + label {     /* white background for selected tab */
    background: white;
    color: #d90000;
   
    border-bottom: 4px solid #d90000;
  }

   input ~ .tab {         /*  grey line between tab and contents  */
    
    padding: 12px;
  }

  .collapsible {
    max-width: 500px;
    border: 2px solid #e0dcdc;
    border-radius: 5px;
    padding: 15px;
    padding-bottom: 0px;
    padding-top: 0px;
    background-color: #fafafa;
   
  }

 .tab-title {
    max-width: 500px;
    padding: 15px;
    padding-bottom: 0px;
    padding-top: 0px;
    left: 0;
    text-align: justify;

 }


 .title-format {
   font-weight: bold;
 }


 
</style>
