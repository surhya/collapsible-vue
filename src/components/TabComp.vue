<template>
  <div class="hello">
    
    <div class="outer-card">

    <input type="radio" name="tabs" id="tab1" checked />
    <label for="tab1">Personal</label>
   
    <input type="radio" name="tabs" id="tab2" />
    <label for="tab2">Bank Details</label>
   
    <input type="radio" name="tabs" id="tab3" />
    <label for="tab3">Documents</label>
   


    <div class="tab content1">Tab1 Contents</div>
    
    <div class="tab content2">
        <div class="tab-title">
        <p>{{msg}}</p>
        </div>
        <div class="collapsible">
            <section class="accordion">
                <input type="checkbox" name="collapse" id="handle1" >
                <table style="width:100%">
                <tr>
                    <td>
                        <h3 class="handle">
                            <label for="handle1">Blue-Sea Marine Services</label>
                            <p>Bank of Singapore - xxxxxxxxxxxxxxxxxxx9224</p>
                            </h3>
                    </td>
                    <td>
                        <a id="angle-icon" class="ti-angle-down"></a>
                    </td>
                </tr> 
                </table>
                
                <div class="content">
                  <section class="table-section"> 
                    <p style=" font-weight: bold;">Account Type</p>
                    <p>Current</p>
                     <p style=" font-weight: bold;">Bank Name</p>
                      <p>SBM Bank (Marutius) LTD</p>
                  </section>
                  <section class="table-section"> 
                    <p style=" font-weight: bold;">Name as per Bank Account</p>
                    <p>LCV Trade Finance Fund</p>
                     <p style=" font-weight: bold;">Account Number</p>
                      <p>500105659541525</p>
                  </section>
                    
                </div>
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
      msg: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
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

.accordion > input[type="checkbox"] {
    position: absolute;
  
  }

  .accordion .content {
    overflow-y: hidden;
    height: 0;
    transition: height 0.3s ease;
    background-color: white;
    
  
  }

  .accordion > input[type="checkbox"]:checked ~ .content {
    height: auto;
    overflow: visible;
    
   
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

 .table-section{
   width: 135px;
   display: inline-block;
   
 }

 
</style>
