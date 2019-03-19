# MileStone 5 : The IPL Auction 

We're all familiar with the [Indian Premier League](https://en.wikipedia.org/wiki/Indian_Premier_League). Each year multiple teams compete in this summer long league to win the coveted title of "IPL Champions"

We're going to create a program today that will replicate the process of the IPL auction. 

## NOTE: This milestone has to be built in node and needs to run on the terminal. No browser needed

## Release 0 : Players, Staff and Teams 

The IPL has a simple structure. The IPL signs on multiple players to play the league. Each year, the teams participate in an auction for the players and the team staff. 

Our objective is to design a program that does the following:
- Creates and stores Teams
- Creates Players
- Creates Team Staff 
- Creates an Auction through which Teams can buy Players 

#### Players 
Players are of 4 types: 
    - Batsmen 
    - Bowlers 
    - All Rounders 
    - Wicket Keepers 

All players have a price assigned to them. This will be their Auction Price (between 20 lakhs - 2 crores). They also have a name, a type (Batsman/Bowler/WicketKeeper/All Rounder), matches played and any other attributes you might think the player might need. 

Each type of player has a special method which makes them their type. For e.g. Batsmen will have a "bat" method, Bowlers will have a "bowl" method, All Rounders will have both and Keepers can "keep".

Think of how will you design and represent Players. 

1) Create 90 players split as follows: 
    - 30 Batsmen 
    - 30 Bowlers 
    - 18 All Rounders 
    - 12 Wicket Keepers
2) You can use [Faker](https://github.com/marak/Faker.js/) to make these really quickly. 

#### Teams 
Teams have the following attributes: 
 - Name 
 - Mascot 
 - Budget (between 20-50 crores)
 - Players - These will be the players that the team gets to buy in the auction
 - Owners (can be one or many)
 - SendBid - a function to send a bid for the auction of a player with a random delay

 Each team will need to consist of the following: 
 - 7 Batsmen 
 - 6 Bowlers 
 - 2 Wicket Keepers 
 - 1 coach 
 - 1 medico
 - 2 training staff
      Note: All Rounders can be counted either as a batsman or a bowler but not both


 1) Create 6 teams

#### Team Staff
Team staff are of 3 types: Coaches, Medico and Trainers. They have the following attributes:
- Name
- Type (Coach/Trainer/Medico)
- Price

Each staff has a special method which allows them to do their job effectively. A coach can train the layers, medicos can heal players, trainers can support the players. 

1) Create 6 coaches (20 lakhs - 50 lakhs) , 6 medicos (5 lakhs - 10 lakhs) and 12 trainers (1 lakh - 5 lakhs)

## Release 1 : Auction 

Now that we have the players, staff and teams in place, let's discuss how the auction works. 

    1) Each player and staff will be Auctioned 
    2) Teams can all participate in this Auctione
    3) The Auction price for a player is the price of the player
    4) The Auction method should work as follows: 
        - The Auction is called for a player
        - All the teams send a request for the auction with random delay in the request
        - The player gets allocated to the first bid received only if : 
            - The team has the budget to afford the player
            - The team has place for the type of the player i.e. If the the player being auctioned is a batsmen and the team already has 7 batsmen, the team's request will be rejected
    5) The above logic applies to both Coaches and Staff too
    6) The team's budget can be reduced to 0 without meeting the  team requirements i.e. if a tem has 4 crores left in it's budget; it can't buy a player worth 4 crores if it only has 12 players in its squad

 - Create the Auction method which allows for Teams to send the bids in and it accepts or rejects the bids depending on the factors listed above. 

## Release 2 : Conducting the auction 

Now that we have everything in place, let's conduct the auction. You need to write the methods for the Auction to run for each player, coach and staff. The teams need to send bids to the Auction for each player and one team wins the bid. An example auction flow might look like the following: 

    - The auction starts for Player1 who is a batsmen with the price 1 crore
    - The first bid received is from Team2; however team 2 already has 7 batsmen and thus the bid gets rejected 
    - The second bid is received from Team5 but it does not have budget left to buy it and thus gets rejected 
    - Team6 choses not to send a bid 
    - Team3 is the third bid received and they meet the requirements and also have the budget and thus the player gets allocated to Team3
All steps of the Auction needs to be printed out to the console. For e.g. Output for the above example will be: 
``` 
Bid from Team2 rejected due to team structure
Bid from Team5 rejected due to budgets
Player1 sold to Team3 for 1 crore. Team3 now has the following players: 
- Player 1
- ...
- ...
- Other players
```

## Release 3 : Think about the flow 

There a lot of pieces in this Milestone with a lot of logic based decisions. It would be a good idea to build this out step by step. Think of the following: 

- How do you represent the Teams, Players, Staff? 
- What does adding a player to a team mean? How will you represent this?
- What is the control flow for the auction? 
- What logic should be verified by the team and what should be verified by the Auction method?
- How does the bid logic work? How do you reject a bid? 
- How do you ensure that a team gets all the required people without having to worry about its budget running out

## Release 4 : Extended Functionality

YOu can add functionality to make the teams' bidding process more efficient. 
- How will you define the method such that teams will only bid on players that cost lesser than a particular amount? 
- How will you manage your budgets more efficiently? How can you split your total budget between players and staff? 
- Let's say at the end of the auction, there are some players left who can't be sold? How will you write a method to redefine the price for the player and sell him again?

## Release 5 : Extended Functionality

Can you write the logic for a match between 2 teams? 
Create a scoring system for playing a match. It could be as follows: 
    - Each batsman scores between 0-100 runs
    - Each bowler takes between 0-6 wickets 
    - Keepers catch 0-5 catches which add to wickets
    - All rounders either score 0-50 runs or take 0-2 wickets
    - Write the win logic
    - Write a logic to create what each team scored in their innings. How will you go about this?





