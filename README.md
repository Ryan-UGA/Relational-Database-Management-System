
# Team 3 MIST 4610 Group Project 1

## Team Name:
20244 Group 3


## Team Members:
1. Nicolle Serafin [@nikkiserafin](https://github.com/nikkiserafin/MIST4610-Project1)
2. Shubhangi Khanna [@shubbykhanna](https://github.com/shubbykhanna/MIST-4610-Project1)
3. Jay Dumon [@JayDumon](https://github.com/JayDumon/MIST-4610-Group-Project-1)
4. Ryan Cullen [@javaprogrammer2023](https://github.com/Javaprogrammer2023/MIST4610-Project1)
5. Elyssa Abbott [@elyssaabbott](https://github.com/elyssaabbott/MIST4610-Project1)

## Problem Description:
We are the owner/operator of a tennis club needing to build a relational database. The central entity is the Members entity - Members being each person who has a membership at the tennis club. Members have the ability to reserve facility spaces (courts and club rooms), purchase tennis necessities (attire, racket, shoes,etc.), and develop their tennis skillset through lessons with tennis coaches or playing matches in a league. Through modeling these relationships in depth, we aim to precisely model these relationships, create sample data, add attributes to our entities, and perform valuable queries to effectively model our tennis club's operations.

## Data model:
![Group Project Model Image](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/1ea26718-c30b-4d62-b94c-475faada199f)

**Explanation of data model:**

Our model is based on a hypothetical tennis club. Members is the central entity including a member identification number, their first and last name, contact information, other personal information (age and gender), membership level, their team, and their coach if they have one.

There are also many membership options members can opt into. Each level provides members different perks correlated to the club. Each level has a price. This is why we created a One-To-Many Relationship for membership levels and members. Each membership level can have multiple members, but only a member can be part of one membership level.

Coaches have their own entity. The Coaches entity includes their coach identification number, first and last name, qualifications, availability, and their own membership level. There is a One-To-Many Relationship between MembershipLevels and Coaches because one specific membership is for all the coaches. Members do not have to have a coach, but they can only have one coach at a time. Coaches have to coach at least one member, but can coach more than one member. That is why there is a One-To-Many Relationship between Coaches and Members.

All members are able to make purchases at the tennis club as a part of their membership. They can make purchases directly from their memberID. There is a One-To-Many Relationship between Members and Purchases because one member may make many purchases, but the purchase can only belong to one member. The Purchases entity includes the purchaseID, date and time of the purchase, amount of the purchase, memberID, and itemID the member purchased. This corresponds directly to the Items entity. The Items entity includes the itemID, itemName, quantityInStock, sellingPrice, manufacturingCost, and vendor. There is a One-To-Many Relationship between Items and Purchases because one item may be purchased multiple times. To clarify, there may be multiple identical items in stock for purchase.

EventReservations is an entity at the tennis club for members to reserve for personal use. There is a One-To-Many Relationship between Members and EventReservations because a member can make many reservations, but does not have to. This entity includes the reservationID, name of the event, location of the event, date and time of the reservation, and the memberID.

Members can opt in to play for the club's tennis team. To clarify, Members have the option to join a home team, but do not have to. Our tennis team will play matches against different teams in the area in the same league. The home team has a specific teamID, teamName, as well as the number of players on their team. HomeTeams and Members have a One-To-Many Relationship; multiple members can be on the same team. The home team has the ability to play multiple Matches, giving HomeTeams and Matches a One-To-Many Relationship. The Matches entity includes matchID, homeScore, awayScore, date and time of the match, teamID, the court location of the match, and the leagueID. Basing our scoring method off of Junior Play, the matches will only be played first to win 8 games. Lastly, the HomeTeams can play multiple Matches in the same league. To clarify, Leagues and Matches have a One-To-Many Relationship. Members can play multiple Matches but only in one league. The Leagues entity has two attributes - leagieID and leagueName.

As a perk, Members are able to reserve courts as a part of all MembershipLevels (Silver, Gold, Platinum, Coach). The CourtReservations entity includes the reservationID, the date and time of the court reservation, the memberID, and courtID. There is a One-To-Many Relationship between Members and CourtReservations. One member can have multiple CourtReservations, but not at the same time. There is a One-To-Many Relationship between Courts and CourtReservations. One reservation can only reserve one court. The Courts entity includes the courtNumber, the surfaceType of the court, and whether the court is inside or outside. There is a One-To-Many Relationship between Courts and Matches because many Matches can be played on the same court if the timing is different. In other words, multiple Matches can be played on multiple Courts, but multiple Matches can be played on the same court at different times.

The next entity is CourtMaintenance which includes maintenanceID, the date and time of the scheduled maintenance, the maintenance worker's ID number, and the court that they maintained. There is a One-To-Many Relationship between Courts and CourtMaintenance. One court can be maintained by multiple workers.

The last entity is MaintenanceCrew which describes the specific employee maintaining the court. This includes employeeID, the employee's first and last name, and contact information. There is a One-To-Many Relationship between MaintenanceCrew and CourtMaintenance because one crew member can have multiple maintenance jobs.

## Data Dictionary:
![Members table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/06a7d2f8-411b-47b5-aafa-da1465008b7f)
![Leagues table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/b46e97e5-62d2-4c15-8e73-13315c3ecb5e)
![Courts table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/57699473-73ff-4e55-b76e-887c0aa5e0fc)
![Court Maintenance table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/43ada01d-7d38-4d46-892a-7e95f4435a0c)
![Court Reservations table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/a3ff9178-d71a-4e9d-b8d9-72a1a880ae33)
![Coaches table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/238b2c79-c5ab-4f76-9f0d-d27cfe0d173d)
![Membership Levels table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/2d829218-83d5-459f-967b-af165622f6a5)
![Items table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/0151b343-dfc0-4833-9578-c11c3ddbc0d2)
![Purchases table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/2067895a-5772-4dc1-9da3-9e282530d943)
![Matches table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/a0d3d0f1-203c-4374-856f-2dc99c4d23b9)
![EventReservations table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/27e4e316-499e-4d97-b2ad-065f30f1fc84)
![Events table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/2c0f9832-8f93-4b17-8408-b2e86a40282d)
![HomeTeams table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/8e2d8803-2426-4edb-8c13-862b0f605d44)
![MaintenanceCrew Table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/8c944b87-02c4-42f4-971e-4be65e781230)

## Query Table:
![Query Table](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/c9938534-5ad8-4735-abf8-77d722572c53)

## Queries:
![Query 1](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/37c2e754-0894-424b-951f-c85a1a2c0628)

The query listing all members with silver memberships provides a clear understanding of the size and composition of our silver membership base. This data allows the clu to tailor specific promotions, events, or services to cater to this segment, ensuring their satisfaction and loyalty. Additionally, tracking silver membership uptake over time can provide valuable insights into the effectiveness of the membership offerings and assist in making informed decisions about future membership tiers and benefits.

![Query 2](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/2ab5fd09-3920-405e-b0c9-6817febe1ee0)

This query provides valuable insight into the inventory status of the pro shop, indicating items with low stock levels. By identifying products with 10 or fewer items remaining, the club can efficiently manage inventory replenishment, ensuring popular items are always available to the customers. This allows the club to maintain satisfied customers.

![Query 3](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/77b469f9-63c0-4e6e-8ba7-d002e180f82e)

This query provides valuable insight into the specific courts that are located outside and are on clay. This information is valuable as it allows the owner to identify which courts are suitable for outdoor play or matches, which helps the owner organize scheduling and allocate resources effectively. Additionally, understanding the distribution of court surfaces can inform decisions about maintenance schedules and investments in amenities tailored to outdoor play, enhancing the overall experiences for members. 

![Query 4](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/61db5fe1-d88e-4e6a-9cbc-af3c45c92831)

This query provides insights into the specific clientele Lotti is catering to, allowing the club to understand her coaching workload and effectiveness. By knowing which members she is coaching, we can tailor marketing efforts, allocate resources, and make strategic decisions to enhance the coaching experience for both Lotti and her students, ultimately driving business growth and satisfaction.

![Query 5](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/e5b54643-c028-4fc4-95e6-64fcf8c32e6c)

Providing the average age of members in each membership level can help tailor the club's offerings and amenities to better suit the demographics of each group. Understanding the age distribution within membership levels enables the ability to create targeted marketing campaigns and develop programs and events that cater to the specific interests and needs of different age groups. Additionally, it aids in forecasting membership trends and making informed decisions regarding membership pricing and retention strategies.

![Query 6](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/8ec97203-df2c-4f56-a82f-a9ef8675acf9)

This query helps the club to identify members who haven't utilized the court reservation system, allowing management to reach out to them and encourage more frequent use of the facilities. By understanding which members are not engaging in court reservations, they can tailor promotional efforts or incentives to increase their participation, thus maximizing court usage and potentially boosting revenue. Additionally, it provides insights into areas where improvement in communication of the reservation system among members may be necessary.

![Query 7](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/1b865d28-d784-4c8d-ae94-c656a3257f51)

By identifying these members that are Silver Members and have booked an event in the Courtyard, we can tailor special promotions or offers specifically for them, enhancing their experience and encouraging loyalty. Additionally, understanding the preferences and behaviors of the Silver level members allows optimization in marketing strategies and allocating resources effectively, ultimately driving revenue and fostering a stronger sense of community within the tennis club.

![Query 8 pt 1](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/a77e9f67-c24c-488e-a2de-ba7764567ba7)
![Query 8 pt 2](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/33d43007-6a57-4149-9e24-cf808f0e9d7b)

This query will provide the tennis club owner with a list of member IDs, names, and the number of times each member has made a reservation. This information is valuable as it helps identify the club’s most active members, understand usage patterns, and tailor marketing or loyalty programs to reward frequent users. Additionally, it enables the club to optimize court availability to meet demand.

![Query 9](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/9ab9d211-630c-426c-8146-7d13466564a4)

Knowing which courts Ches Belliveau serviced with a hard surface can help the club to optimize your court maintenance schedule and resources. By understanding which courts are likely to endure more wear and tear, management can prioritize their upkeep to ensure they remain in top condition, thereby enhancing the overall playing experience for the customers. Marketing can use this data to allocate efforts to attract players who prefer hard surface courts.

![Query 10](https://github.com/nikkiserafin/MIST4610-Project1/assets/163012574/ee0a5828-6b13-4689-8c56-cd1615660fc0)

By identifying members with at least 5 reservations, we can pinpoint the most loyal and active customers. This insight allows the tennis club to tailor special offers or rewards programs to incentivize continued patronage, fostering customer loyalty. Additionally, understanding reservation patterns among these members can help optimize court scheduling and resource allocation, ultimately enhancing operational efficiency and customer satisfaction.
