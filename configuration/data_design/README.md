## Data Design

**Example:**

_To start, you should ask yourself three questions:_

1.   _What are the kinds of information I want to store?_
2.   _What is the depth of information I want to store?_
3.   _How do the different kinds of information relate to each other?_

1.   _In a research project thats maps personal relations by means of institutional affiliation and epistolary communication, you can identify four kinds of information:_
    *   _Person_
    *   _Institute_
    *   _Letter_
    *   _City_
2.   _Here, you can use varying depths to store the information you need:_
    *   _Person_
        *   _First Name_
        *   _Last Name_
        *   _Date of Birth_
        *   _Place of Birth_
        *   _Date of Death_
        *   _Place of Death_
        *   _Places of Residence_
    *   _Institute_
        *   _Name_
        *   _Founded_
        *   _Location_
        *   _Members_
    *   _Letter_
        *   _Date_
        *   _Text_
        *   _Sender_
        *   _Receiver_
        *   _Place of sending_
        *   _Place of receiving_
    *   _City_
        *   _Name_
        *   _Location_
3.   _The relations between the kinds of information would be:_
    *   _Person_
        *   _Place of Birth → City_
        *   _Place of Death →_ City
        *   _Places of Residence →_ City
    *   _Institute_
        *   _Location → City_
        *   _Members → Person_
    *   _Letters_
        *   _Sender → Person_
        *   _Receiver → Person_
        *   _Place of sending → City_
        *   _Place of receiving → City_

_This would lead to the following Data Design that has four Types:_
_Screenshot Person OD & SO_
_Screenshot Institute OD & SO_
_Screenshot Letter OD & SO_
_Screenshot City OD & SO_

![Data Design diagram](/assets/data_design_diagram.png)
