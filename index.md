# Guide :  GaBot - Discord Bot  
---

> ## *About GaBot* 
>  The bot was created for schools and their study purposes on a discord platform
> 
>  ***Fully customizable Discord server moderation bot for your Discord server that includes simple commands for using and setting up the boot***
> 
>  *Functionalities*
> - Reaction roles
> - Twich notifications 
> - Youtube notifications
> - Q&A system based on discord threads
> - Deadline planning for tests, exams ...
> - Adding and Tracking points from school subjects
> - Automatic notification for changes and notifications on the school web page
> 
> based on discord.py library
> 


---
 *GaBot is Open source project in python*
---

## *How to install Gabot with Docker*
> ...

---
## *Introduction*

### *Reaction roles*

Reaction roles allow you to easily add roles to teams on your discord server.

--- 

### *Twitch and Youtube notifications*
Automatic notifications when a lecture or exercise stream starts and when it is published new video on Youtube from the subject.

---

### *Q&A System*
People in dedicated channels can ask questions, vote for them (by responses). The voting results are displayed in Discord threads. If the question is answered, it can be "archived", i.e. moved to another, designated,channels.

---

### *Deadlines*

Functionality is focused on creating deadlines for credits, projects, assignments and any other events. In addition, you can cancel any date or view all active dates.

---

### *Adding and Tracking points*
The scoring functionality ensures that students can see their points from the discord subject. On the contrary, according to the discord role, the teacher has the power to add points to the students.

---

### *Automatic notification for changes*
Automatic notifications for subject page notifications.

---

## *Commands* 
---

#### *Prefix*
> **Bot** has a prefix dash **-**

---

#### *Help* 
> 
> `-help | h`

Displays all bot functionalities with their descriptions. The **```Example```** shows a listing after executing the help command

 
**Example**
```
• deadline
Command to set deadline notifications
He has other commands

• youtube
Command for youtube toggle
He has other commands

...
```

---

#### *Reaction roles*

> `-reaction_roles | rr`

Commands to display all commands for reaction roles functionality.
This command is used with other functions for reaction roles.

---

##### *toggle*
> `-rr toggle`

Command to ```enable | disable``` reactions roles on your server. After executing the command bot sends a message to the channel that you have enabled reaction roles.

**Example**
```
-rr toggle 
```

---

##### *channel*
> `-rr channel [channel]`

Command to set up a channel where bot displays the option to select roles by responding to **```emoji```**. 
If you do not specify a **```channel```**, the bot will list the role selection to the channel you are in.

**Example**
```
-rr channel 

-rr channel general
```

---

##### *add*
> `-rr add <emoji> <role>`

The command is used to **```add```** a **```role```** under a specific **```emoji```** to reaction roles.

**Example**
```
-rr add :joy: @example
```

---

##### *remove*
> `-rr remove <emoji>`

The command is used to **```delete```** roles from reaction roles.

**Example**
```
-rr remove :joy:
```

---

#### *Deadline*

> `-deadline | dl`

Commands to display all commands for deadline functionality.

---

##### *create*
> `-dl create <name> [args...]`

This command is used to create a **```deadline```**.
In the form `-dl create` **```[deadlin name]```** **```[dd / mm / yy HH / MM / SS]```**  **```[dd / mm / yy]```** days of notification.

**Example**
```
-dl create "Project 1" "1/11/21 23:59:59" "1,2,5"
```

---

##### *edit*
> `-dl edit <name> [args...]`

The command is used to **```change```** deadline settings.

**Example**
```
-dl edit "Project 1" "1/12/21 20:00:00" "1"

```

---

##### *showall*
> `-dl showall`

The command displays a list of all active deadlines.

---

##### *end*
> `-dl end <deadline_name>`

The command is used to **```cancel```** the deadline.

**Example**
```
-dl end "Project 1"
```

---

##### *endall*
> `-dl endall`

The command is used to **```cancel```** all deadlines.

---

#### *Youtube and Twitch*

> `-youtube | yt`
> `-twitch | tw`

Commands to display all commands for youtube and twich functionality.

---

##### *toggle*
> `-yt toggle`
> `-tw toggle`

Use these commands to turn Twitch and youtube notifications on and off.

---

##### *status*
> `-yt status`
> `-tw status`

Use these commands to find out if you have twich and youtube notifications on or off.

---

#### *Q&A System*
> `-question | q`

Commands to display all commands for the Q&A system.

---

##### *create*
> `-q [create|c] <question>`

Command to create a question. The created question will be displayed in the active thread.
Creates new question, wrap question into ==" "== for question with spaces.

**Example**
```
-q c "How is the weather today?"
-question create "How are you today?"
```

---

##### *answer*
> `-q [answer|a] <answer>`

The command is usable only inside active question thread. Wrap answer into ==" "== for question with spaces.
Answers (resolves) question. 

**Example**
```
-q a "bad"
-question answer "good"
```

---

##### *remove*
> `-q [remove|r|delete|d] `

Removes question.The command is usable only inside active question thread. 

**Example**
```
-q r 
-q remove
-q delete 
-q d
```

---

##### *answer-emoji-marked*
> `-q [aem|answer-emoji-marked] :emoji: `

Scans all messages with a given emoji from the solver of the question in thread and takes them as an answer.
The command is usable only inside active question thread. 
After answering, the question is automatically deleted from the channel with active threads and moved to the archive and sent to the author in the DM.

**Example**

```
-q aem :joy:
```

---

#### *Notifications*
> `-question | q`

Commands to display all commands for Notifications.
***Beware***. Every command mentioned below is secured by specific validation. User is unable to run command if params or situation if not suitable for them. User will be also notified what error made, and how to fix it.

---

##### *notify*
> `-[notify|sn]  `

Command to display all commands for notify/scheduler actions.

---

##### *params_info*
> `-notify params_info `

This command  will return list of all set notify parameter for guild, from which is this command called. If some parameter is not set, his value will be „empty“.

**Example**
```
-notify params_info
```

---

##### *set_api_url*
> `-notify set_api_url [args...] `

This command is used for setting parameter Api url (url we will request for data). If parameter is already set, his value will be updated. Set url must start with http:// or „https:“.

**Example**
```
-notify set_api_url https://kokos.free.beeceptor.com/
```

---

##### *set_requests_time_minutes*
> `-notify set_requests_time_minutes [minutes] `

Command is used for setting requesting interval value in minutes. If parameter is already set, his value will be updated. Value can contain only numbers and value must be >= 1.

**Example**
```
-notify set_requests_time_minutes 5
```

---

##### *set_requests_subject_shortcut*
> `-notify set_requests_subject_shortcut [args...] `

Command is used for setting shortcut of wanted subject. Parameter is used to filter obtained data throu request. Used value must have length at least 1.

**Example**
```
-notify set_requests_subject_shortcut MSUS
```

---

##### *add_notify_info_channels*
> `-notify add_notify_info_channels [args...] `

Command is used for setting array of infromation channels (channels where we post info about new’s obtained throu request). Input must contain at least one channel that belongs under guild, from which is this command called (but can contain more of them).

**Example**
```
-notify add_notify_info_channels general info spam
```

---

##### *remove_notify_info_channels*
> `-notify remove_notify_info_channels [args...] `

This command is used to remove already set info channels. You can remove one or more of them. Input must contain at least one channel, and channel must be already in array of set info channels.

**Example**
```
-notify remove_notify_info_channels general info spam
```

---

##### *add_notify_system_error_channels*
> `-notify add_notify_system_error_channels [args...] `

Command is used for setting array of system error log channels (channels where we post occured system error). Input must contain at least one channel that belongs under guild, from which is this command called (but can contain more of them).

**Example**
```
-notify add_notify_system_error_channels general info spam
```

---

##### *remove_notify_system_error_channels*
> `-notify remove_notify_system_error_channels [args...] `

This command is used to remove already set system error channels. You can remove one or more of them. Input must contain at least one channel, and channel must be already in array of set system error channels.

**Example**
```
-notify remove_notify_system_error_channels general spam
```

---

##### *set_start_stop_requesting*
> `-notify set_start_stop_requesting [args...] `

Command is used to start or stop requesting Api url for this particular guild, from which is this command called. Note, that if you want to start requesting there is one condition. Every notify parameter must be already set (not „empty“). To start requesting use parameter true and to stop false.

**Example**
```
-notify set_start_stop_requesting true
```

---

#### *Adding and Tracking points*
> `-pts`

Commands to display all commands for adding and tracking points.

---

##### *show*
> `-pts show `

Reading points of a specific user from the database and listing points in the format 'Points': {number of points}.

**Example**
```
-pts show
```

---

##### *add*
> `-pts add [user] [points] `

Command to easily add points for a specific user directly using the discord bot.

**Example**
```
-pts add @user1 20
```

---

##### *API_URL*

A link to an API to which you can make a POST request for points

---
