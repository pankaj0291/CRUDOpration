# CRUDOpration
A basic CRUD operation requires data. It can be any database. For my CRUD application, I am using data in a JSON object.

1) I have data stored in a JSON object (in my application). I’ll extract the data and display it in a dynamically created HTML table.
2) Each row has few more dynamically created HTML elements like buttons, textboxes and Dropdown List, to perform functions like, update, delete, save, create new and cancel.
3) Button’s and textboxes will have events attached, dynamically.
4) Each row has a status, if status is Inactive then row is showing in red background.



I have a global function named crudApp(), which has other functions for the CRUD operations to work.

First, I have declared an Array of JSON objects with values in ContactList. This is my data, with which I’ll work.

this.ContactList = [];

I have another JSON object array named status. I’ll use the status object to populate the SELECT dropdown lists, which I’ll add in every row of the table.

The list (or data) is displayed in an HTML table. Since I have not included the table element in the design mode, I’ll create the table dynamically using JSON data. To do this I have declared a function named createTable().

this.createTable = function () { }

Create an HTML Table Dynamically


1)The for loop extracts the values from the array myBooks for the table header and stores it in another array called col[]. I have used this array in many functions in this application.

2)While creating the table, I am adding (or attaching) few elements dynamically to each row of the table.The first element is a label that shows a ✖ (lblCancel.innerHTML = '✖') sign. The function of this label is like a button, to Cancel. Clicking this element will cancel the update function. Therefore, it has onclick event attached to it, which calls a function named Cancel().

lblCancel.setAttribute('onclick', 'crudApp.Cancel(this)');

Similarly, I am creating and adding three buttons (input element of type button) with events and ids. Each has a function to 

save, update and delete.

3)	Finally, I am completing the table creation part by adding a row at the end of the table, which will have four blank textboxes and a SELECT dropdown list, followed a button (Create) at the last column. This is for creating new data for the list.

Functions for CRUD Operation

I have five different functions to perform different operations. These functions are

1)	this.Cancel () – This will cancel the update procedure. Every row of the table has an Update button. Clicking this button will show two more buttons, to cancel and to save. Clicking the cancel button will call the function this.cancel() that takes a parameter as the calling element.Using the object’s reference, you can get the active row, its elements and values.

2)	this.Update () – This functions is called when you click the Update button in any row. It only shows the input elements like textbox and a dropdown list with values. So now, you can edit the values in each cell of the selected row (except the first column).

In-addition, it will show the ✖ button (to cancel) and the Save button. See the image.

3)	this.Delete() – This function uses JavaScript splice() method to remove the data from JSON array.

this.ContactList.splice((activeRow - 1), 1);

4)	this.Save() - This function will update or save the rows data in the Array. It is associated with Update operations. The Save option is activated when the user click’s the Update button in any row.

5)	this.Create() – The last row has blank boxes and a button named Create at the last column. Clicking the Create button will call this function and it will add a new set of data in the exiting list inside the myBooks array.

6) applying proper validation on Email address and Phone no.
