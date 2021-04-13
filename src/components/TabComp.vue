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

    <!-- Tab BankDetails Content: Begins -->
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
                      <p>{{acctype}}</p>
                      <p class="title-format" >Bank Name</p>
                      <p>{{bname}}</p>
                  </div>
                  <div class="table-section">
                    <p class="title-format" >Name as per Bank Account</p>
                    <p>{{accname}}</p>
                    <p class="title-format">Account Number</p>
                    <p>{{accnumber}}</p>
                  </div>
                  </div>
                     <p class="title-format" >To change your bank account details, contact <a href="">ir@siamvalidus.co.th </a> </p>
                  </div>

                 </article>
            </section>
        </div>

    </div>
    <!-- Tab BankDetails Content: Ends -->

    <!-- Tab Documents Content: Begins -->
    <div class="tab content3">
      <table>
        <caption>Uploaded Documents</caption>
          <thead>
          <tr>
            <th scope="col">Name</th>
            <th scope="col">Type</th>
            <th scope="col">Upload Date</th>
            <th scope="col"></th>
           

          </tr>
        </thead>
        <tbody>
          <tr>
            <td data-label="Name">{{uname}}</td>
            <td data-label="Type">{{utype}}</td>
            <td data-label="Upload Date">{{udate}}</td>
             
              <td class="dropdown">
                <p><a id="" class="ti-more-alt"></a></p>
               <div class="dropdown-content">
                  <a href="#">View</a>
                  <a href="#">Download</a>
                  <a href="#">Print</a>
                </div>
              </td>
               
          </tr>
          
          <tr>
             <td data-label="Name">{{uname}}</td>
            <td data-label="Type">{{utype}}</td>
            <td data-label="Upload Date">{{udate}}</td>
              <td class="dropdown">
                <p><a id="" class="ti-more-alt"></a></p>
               <div class="dropdown-content">
                  <a href="#">View</a>
                  <a href="#">Download</a>
                  <a href="#">Print</a>
                </div>
              </td>
          </tr>
          <tr>
             <td data-label="Name">{{uname}}</td>
            <td data-label="Type">{{utype}}</td>
            <td data-label="Upload Date">{{udate}}</td>
            <td class="dropdown">
                <p><a id="" class="ti-more-alt"></a></p>
               <div class="dropdown-content">
                  <a href="#">View</a>
                  <a href="#">Download</a>
                  <a href="#">Print</a>
                </div>
              </td>
          </tr>
          <!-- <tr>
            <td scope="row" data-label=""></td>
            <td data-label=""></td>
            <td data-label=""></td>
            
          </tr> -->
        </tbody>
      </table>
     
    </div>
    <!-- Tab Documents Content: Ends -->

</div>


  </div>
</template>

<script>


export default {
  props: ['acctype', 'accnumber','bname','accname','uname','utype','udate'],
  name: 'TabComp',
  data () {
    return {
      msg: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
      isOpen: false
    }
  },
  components: {

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

 /* Documents CSS */
 table {
  border: 1px solid #ccc;
  border-radius: 5px;
  /* border-collapse: collapse; */
  margin: 0;
  padding: 0;
  width: 50%;
  table-layout: fixed;
}

table caption {
  font-size: 15px;
  padding: 10px;
  text-align: left;

}

table tr {
  background-color: white;
  border: 1px solid #ddd;
  padding: 10px;
}

table th,
table td {
  padding: 10px;
  text-align: left;
  border-bottom: 1px solid #ddd;
  
}

table th {
  font-size: 15px;

  text-transform: uppercase;
}

.action-bt{ 
  
 cursor: pointer;
 
  
}

.dropdown {
  position: relative;
  display: inline-block;
 
}

.dropdown-content {
  
  display: none;
  position: absolute;
  background-color: white;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {background-color: #ddd;}

.dropdown:hover .dropdown-content {display: block;}

.dropdown:hover .dropbtn {background-color: #3e8e41;}



@media screen and (max-width: 600px) {
  table {
    border: 0;
    width: 100%
  }

  table caption {
    font-size: 15px;
  }

  table thead {
    border: none;
    /* clip: rect(0 0 0 0); */
    height: 1px;
    margin: -1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
    width: 1px;
  }

  table tr {
    border-bottom: 1px solid #ddd;
    display: block;
    /* margin-bottom: .625em; */
  }

  table td {
    border-bottom: 1px solid #ddd;
    display: block;
    font-size: 13px;
    text-align: right;
  }

  table td::before {
    
    content: attr(data-label);
    float: left;
    font-weight: bold;
    text-transform: uppercase;
  }

  table td:last-child {
    border-bottom: 0;
  }

.action-bt{ 
   padding: 0;
   
 
}

}



</style>
