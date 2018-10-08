# Patreon-Authenticator-as3-air
Connect Flash to Patreon and reward your patreons.
(FLA file works on Animate CC only)

# How to get started
1- Download Patreon.fla file
2- Copy the login button to your Animate CC(Library)
3- connect using Patreon.login( your_patreon_client_id_here );

# How to use properly
If you just use the Patreon.login(client_id) function, it would be enough.
Now, let's say you want to get the information once connected. Here is a sample code:

<h3>//Step 1: Use onStatus to know when you are connected</h3>

Patreon.onStatus = function (stat){
  if (stat==-1) trace("ERROR");
  if (stat== 1) connected();
}

<h3>//Step 2: Connect</h3>
Patreon.login(client_id_here);

<h3>//Step 3: Get the information once connected</h3>
function connected(){
  trace("User E-Mail"   +  Patreon.email);
  trace("Is rewarded with cool thing" + Patreon.hasReward("cool thing"));
}

# Functions

# Functions and Variables
<h3>Patreon.email:String</h3> 
this contains the patreon e-mail once connected. Otherwise, it is ""
<h3>Patreon.rewards:Vector.<PatReward></h3>
Contains information about the rewards.
  Patreon.rewards[0].
