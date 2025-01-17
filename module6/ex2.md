### Exercise 6.2: Triggered Journeys: Setup Journey

In this exercise, you'll configure the journey that needs to be triggered when someone creates an account on the SYTYCD - website.

You can login to ACOP by clicking this link: [https://experienceplatform-mkt-prod1.campaign.adobe.com/](https://experienceplatform-mkt-prod1.campaign.adobe.com/).

After logging in to ACOP, you'll see this screen.

![ACOP](./images/acophome.png) 

From there, click on ``Triggered Journeys``

![ACOP](./images/acoptrig.png)

You'll be redirected to the ``Journeys`` - view in Triggered Journeys.

![ACOP](./images/acoptriglp.png)

Make sure that you're in the ``Journeys`` - view.

Let's create a new journey by clicking the ``Create`` - button.

![ACOP](./images/create.png)

You'll then see an empty Journey screen.

![ACOP](./images/journeyempty.png)

In the previous exercise, you created a new ``Event``. You named it like this ``ldapAccountCreationEvent`` and replaced **ldap** with your ldap. This was the result of the Event creation:

![ACOP](./images/eventdone.png)

You now need to take this eevent as the start of this Journey. You can do this by going to the left side of your screen and searching for your event in the list of events.

![ACOP](./images/eventlist.png)

Select your event, drag and drop it on the Journey - canvas. Your Journey now looks like this:

![ACOP](./images/journeyevent.png)

As the second step in the journey, you need to add an ``Email`` - action. Go to the left side of your screen to ``Actions``, select the ``Email`` - action, then drag and drop it on the second node in your journey.

![ACOP](./images/journeyactions.png)

Your journey now looks like this:

![ACOP](./images/journeyemailaction.png)

On the right side of your screen, you now need to configure the email.

![ACOP](./images/emptymsg.png)

Go to ``Message`` and open the dropdown-list. In that list, you need to select the template with the name ``Thanks for Signing Up``.
 
![ACOP](./images/emailmsglist.png)

Selecting this message automatically opens up a number of additional fields. These are the fields that. have been configured to be dynamic field in the email template. You now need to link each of the expected dynamic fields to a field coming from the Payload that is sent to Platform.

![ACOP](./images/emailpersdata.png)

Let's start with the ``Email`` - field.

Click on the ``Edit`` - icon.

![ACOP](./images/msgemail.png)

You'll then see a window to select a source field to use as Email Source.

![ACOP](./images/emptylink.png)

Click on the name of the event you created to open it.

![ACOP](./images/eventnode.png)

Navigate to ``_experienceplatform.accountcreation.email`` and click it.

![ACOP](./images/srcemail.png)

Click ``OK`` to save your configuration.

Next, let's configure the Brand Logo - field. This field has to be configured as you'll be doing many personalized demo's in the future and you probably want those emails to also reference the same brand logo as what is used on the website, mobile app and Alexa. This is where you can make that happen.

Click on the ``Edit`` - icon.

![ACOP](./images/msgbrandlogo.png)

Navigate to ``_experienceplatform.brand.brandLogo`` and click it.

![ACOP](./images/srclogo.png)

Click ``OK`` to save your configuration.

Next, let's configure the Brand Name - field. This field has to be configured as you'll be doing many personalized demo's in the future and you probably want those emails to also reference the same Brand Name as what is used on the website, mobile app and Alexa. This is where you can make that happen.

Click on the ``Edit`` - icon.

![ACOP](./images/msgbrandname.png)

Navigate to ``_experienceplatform.brand.brandName`` and click it.

![ACOP](./images/srcbrandname.png)

Click ``OK`` to save your configuration.

Next, let's configure the First Name - field. Personalization requires the usage of First Name.

Click on the ``Edit`` - icon.

![ACOP](./images/msgfn.png)

Navigate to ``_experienceplatform.accountcreation.firstName.`` and click it.

![ACOP](./images/srcfn.png)

Click ``OK`` to save your configuration.

Next, let's configure the Last Name - field. Personalization may also require the usage of Last Name.

Click on the ``Edit`` - icon.

![ACOP](./images/msgln.png)

Navigate to ``_experienceplatform.accountcreation.lastName.`` and click it.

![ACOP](./images/srcln.png)

Click ``OK`` to save your configuration.

Your configuration now looks like this.

![ACOP](./images/srcoverview.png)

Click ``OK`` again to save your configuration.

![ACOP](./images/ok.png)

For this exercise, our Journey is fine like it is now.

Let's add an Orchestration Event to ``End`` the Journey. In the left side of the screen, go to ``Orchestration`` and select ``End``. Drag and Drop this onto the 3rd step of the Journey.

![ACOP](./images/orch.png)

Your Journey now looks like this.

![ACOP](./images/journeyfinal.png)

You still need to give your Journey a Name. You can do that by clicking the ``Edit`` - icon in the top right side of your screen.

![ACOP](./images/journeyname.png)

You can then enter the Journey's name here. Please use ``ldap - Account Creation Journey`` as a naming convention and replace **ldap** with your LDAP.
  
![ACOP](./images/journeyname1.png)

Click ``OK`` to save your changes.

![ACOP](./images/ok.png)

You now see this in the top of your screen.

![ACOP](./images/journeyname2.png)

You can now publish your journey by clicking ``Publish``.

![ACOP](./images/publish.png)

You'll then see a green confirmation bar saying that your Journey is now Publish.

![ACOP](./images/published.png)

You've now finished this exercise.

Next Step: [Exercise 6.3: Configure Launch to trigger your Event](./ex3.md)

[Go Back to Module 6](./README.md)

[Go Back to All Modules](../README.md)



