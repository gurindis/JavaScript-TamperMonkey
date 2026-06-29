# JavaScript-TamperMonkey
**Summary:** TamperMonkey (TM) is a web browser extension publicly available on FireFox, Chrome, & MS Edge. It's used by Amazon employees to enhance certain websites. Amazon employees voluntarily code & develop TM scripts for process improvement.  

While working at Amazon, I recognized a business problem/bottleneck and independently learned/developed a TM script. I could not have been prouder of this accomplishment!

This tampermonkey script (600+ lines of code) runs on a website and adds multiple features to the website:  
1-Metrics display  
2-Sort button  
3-Sort dropdown list

**Business Problem**

Can you imagine you are a dispatcher monitoring on the road (OTR) performance of 30+ delivery drivers (or you are an Amazon Manager monitoring 250+ routes) but you don't know how the drivers/routes are performing? 

Specifically:

1-You don't know if they are going to finish delivering their route in the allocated time given to them- which is 10 hours 

2-You don't know the productivity metric of each driver- (DPPH- Delivery Per Paid Hour)

3-You don't know how much a driver is ahead/behind (Shift Completed % vs. Stops Completed %)

4-You don't know how much help to send a driver (OODT- Out of Drive Time Stops)

5- To get all of these metrics, you have to calculate them manually!!!

6- You can't sort your drivers in ascending/descending order based on the metrics above- DPPH, OODT, Stops Completed %.

**Financial Impact**- Amazon pays a fixed rate for 10 hours per standard parcel route to delivery companies- Delivery Service Providers(DSPs). Ff the drivers do not finish their route in 10 hours they go into overtime. Overtime pay comes out of a DSP's pocket, as Amazon only pays a fixed rate for 10 hours. Thus, it's critical to have access to the right data instantaneously to make the correct business decisions.

**Customer Impact** If your Amazon package was showing out for delivery, but you find out in the evening that it was not delivered, how would you feel?

**Internal Metrics Impacted** 
Several internal metrics are impacted by packages that are not delivered for the day.

**DSP Metrics Impacted** 
- Delivery Completion Rate- DCR %. Undelivered packages lower DCR.

**Details**  
1-The following metrics are displayed for each route once the website loads: Stops Completed %, Shift Completed %, DPPH, OODT Stops  
>Stops Completed % is Percent of route that is finished by the driver
>
>
>Shift completed % is calculated by subtracting 10 hour work day from (current time- clock in time to work)
>
> 
>DPPH is the delivery rate or how many stops/hr driver is delivering
>
>
>Out Of Drive Time(OODT) Stops is how many stops the driver is going to bring back to station (undelivered stops) based on time left in the 10hr shift. DPPH and >time left in shift is used to project/calculate this number  


2-Sort Button sorts all the routes in ascending or descending order based on what the user selects in the sort dropdown list

3-Sort dropdown list let user sort the routes based on Stops Completed, Shift Completed, DPPH, and OODT Stops  


**Problems Accounted For While Working on the Project:**  
1- Site navigation-  
>Metrics were being displayed on the route detail page after a user clicked on a route. Script should only run on the home page
>
>
>When a user returned to home page from route detail page, sort button, dropdown list, and metrics would not reappend
>
>
>When a user filters the routes based on other filters already present on the webpage, metrics would not reappend
>
>
>When a user used the search bar to search by driver name or route number, metrics would not reappend

2-Dynamic Metrics Update  
>Stops Completed %, Shift Completed %, DPPH, OODT Stops needs to be updated once the stops completed data on the website refreshes for each route

3-Remove the default Sort dropdown list that's already present on the website and replace it with my own list in 2 instances:  
>When the website initially loads
>
>
>when the user returns to the homepage

**Future Product Ideas:**  
1- Daily Report- Give stakeholders an ability to store/download all the data into excel format- Driver Name, Route ID, DPPH, DSP Name.
