# Interaction with VISION

One of the important aspects is the proper application data synchronization with external services. In case of Financial Assurance module For this purpose For this purposes were added fetching Purchase Orders from VISION. VISION is external database maintained by UNICEF and is being used by different services. When Purchase Order Number is prompted, while creating new Engagement, backend is trying to find it inside the database. If no such record exists, the VISION will be used additionally and in case of success entity will be synchronized into the database. 

![](../.gitbook/assets/image%20%283%29.png)



