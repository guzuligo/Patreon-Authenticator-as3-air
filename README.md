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
<h3>Patreon.login(client_id)</h3>
Connects to patreon and gets the current user
<h3>Patreon.logout()</h3>
Altough it is meant for logging out, it is also used to cancel the login, especially if user didn't press on allow.
<h3>Patreon.hasReward(reward_title)</h3>
Returns true if the user is eligable for the reward specified.

# Functions and Variables
<h3>Patreon.email:String</h3> 
this contains the patreon e-mail once connected. Otherwise, it is ""
<h3>Patreon.rewards:Vector.<PatReward></h3>
Contains and array (Vector) information about the rewards. 
  Patreon.rewards[0].id             //reward 0 id
  Patreon.rewards[0].amount_cents   //How much payed in cents
  Patreon.rewards[0].description    //reward 0 description
  Patreon.rewards[0].title          //reward 0 title
  
  In general, here is the verification code:
  public var id:String;
	public var amount:Number,amount_cents:Number;
	public var description:String,title:String;
	public var user_limit:int,patron_count:int,post_count:int,remaining:int;
  
