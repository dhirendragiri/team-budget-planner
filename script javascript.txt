var empData=[];
function storeInSession() {
   localStorage.setItem("empInfo",JSON.stringify(empData));
   //sessionStorage.setItem("empInfo",JSON.stringify(empData));
}

function setSession() {
    var obj = JSON.parse(localStorage.getItem("empInfo"));
    //var obj = JSON.parse(sessionStorage.getItem("empInfo"));
    console.log(obj);
}

function onFormSubmit() {
    var formData = readData();
    insertNewRecords(formData);
   
    empData.push(formData);  
    console.log(empData)
}


function readData() {
    var formData={};
    formData.clientName=document.getElementById("clientName").value;
    formData.name = document.getElementById("name").value;
    formData.budget = document.getElementById("budget").value;

    return formData;
}


function insertNewRecords(formData) {

   
    var table = document.getElementById("employeeDetails");
    var tableBody = table.getElementsByTagName("tbody")[0];
    var newRow = tableBody.insertRow(tableBody.length);
    var cell1 = newRow.insertCell(0);
    cell1.innerHTML=formData.clientName;
    var cell2 =newRow.insertCell(1);
    cell2.innerHTML= formData.name;
    var cell3 = newRow.insertCell(2);

    cell3.innerHTML= formData.budget;
   



   
   
 
}

/*function setSession(){
    var formData = readData();
    insertNewRecords(formData);

    return console.log(formData)
}*/


function goback(){
    window.history.back();
}