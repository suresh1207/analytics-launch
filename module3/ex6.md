### Exercise 3.6 - Walkthrough of Demo Scenario

Below is a standard script to walk through the demo scenario, this time in the context of Luma Retail. The same script can be applied to any other brand of choice, like La Boutique or your own custom brand.

The goal of this exercise is to get to know the standard path to demo the SYTYCD-environment.

#### **Demo flow:**

#### Step 1 - Unknown visitor browses the Luma website

  * Go to the Luma Homepage
  
  ![Demo](./images/lb_home.png)
  
  * Introduce the X-ray panel and explain the Real-Time Customer Profile:
    * **ECID** as the internal Adobe identifier
    * **Audience Manager ID** as the external identifier, and stress the importance and unique role of Audience Manager as the door and gateway between the internal 'owned' world and the external, paid media world.
      
  ![Demo](./images/lb_home_xup.png)

  * Introduce the concept of Experience Events

  ![Demo](./images/lb_home_xee.png)
  
  * Scroll down on the page until you see the products, click on the Nadia Elements Shell.
  
  ![Demo](./images/lb_els_dtl.png)
  
  * Have a look at the product, explain that an Experience Event of type ```Product View``` has been sent to Platform and then click on the ```+ Add To Cart``` - button.
  
  ![Demo](./images/lb_addtocart.png)
  
  * Explain that an Experience Event of type ```Add To Cart``` has been sent to Platform. Next, click on the cart icon in the top right corner of your screen to visualize the cart.
  
  ![Demo](./images/lb_cart.png)
  
  * Open the X-Ray panel and go to Experience Events. You'll now see an Experience Event as Browse Activity and also an Experience Event as Add To Cart Activity.
  
  ![Demo](./images/lb_cartee.png)
  
  * While the behaviour is anonymous, Luma is able to track every click and store in in Platform. Once the anonymous customer becomes known, Luma will be able to merge all anonymous behaviour automatically to the know profile.
  
#### Step 2 - Unknown visitor registers on the Luma website

As a best practice, please use the following convention for identifiers:

  * Email Address identifier: **ldap**+**DDMMYY**-**number**@adobetest.com
  * Mobile Nr identifier: **yourmobilenumber**-**DDMMYY**-**number**

As an example, for the ldap ```vangeluw```:
On Monday June 17 2019, this should be the first set of identifiers of the day.
  
  * Email Address identifier: **vangeluw**+**17062019**-**1**@adobetest.com
  * Mobile Nr identifier: **0473622044**-**17062019**-**1**

  * Go to the Login/Register page
  
  ![Demo](./images/lb_register.png)
  
  ATTENTION: please remember [the Platform Demo Best Practices guidelines](./ex5.md)
  
  ![Demo](./images/lb_register_dtl.png) 
 
  * Fill out your registration details and opt-in preferences and click ```CREATE ACCOUNT```.
  
  * After login, go to the Homepage of the Luma website and open the X-ray panel, go to Real-Time Customer Profile. On the X-ray panel, you should see all of your personal data displayed.
  
  ![Demo](./images/lb_x_loggedin.png)

  * On the X-ray panel, go to Experience Events. You should see the Browse Activity and the Add To Cart activity that was there before.

  ![Demo](./images/lb_x_loggedin_ee.png)

After becoming a known customer, it's time to install the ```Luma```-mobile app on your iPhone and then login to the app. 

#### Step 3 - Known visitor registers on the Luma website

To use the new mobile app, you need to install the ```SYTYCD```-mobile app. To get access to the mobile application, [click here to add yourself as a tester of the SYTYCD-demo app](https://testflight.apple.com/join/UfazvMKx).

  * Open the Luma mobile app.
  
  ![Demo](./images/app_hp.png)

  * Go to the Account-screen.
  
  ![Demo](./images/app_acc.png)

  * Login with the Email ID you used in the previous exercise and the password of 1234.
  
  ![Demo](./images/app_acc_login.png)

  * See your Real-Time Customer Profile data appear in the application, along with your Desktop Browse Activity

  ![Demo](./images/app_up.png)

  * Go to the app's Homepage
  
  ![Demo](./images/app_hp.png)

  * Go to the ```Mens```-category
  
  ![Demo](./images/app_men_cat.png)

  * Click on the product ```Proteus Fitness Jackshirt (Orange)``` and view the product.
  
  ![Demo](./images/app_proteus.png)

  * Go back to the previous screen
  
  ![Demo](./images/app_men_cat.png)

  * Go to the Account-screen and your Real-Time Customer Profile data will be refreshed, after which you'll see the ```Proteus Fitness Jackshirt (Orange)``` - product be part of your receent browse activity. Please note the fact that the channel on which the browse activity happened is being shown now.
  
  ![Demo](./images/app_after_proteus.png)

  * Now go back to your desktop computer and refresh the Luma homepage, after which you'll see the ```Proteus Fitness Jackshirt (Orange)``` - product also appear there. Please note the fact that the channel on which the browse activity happened is being shown now.
  
  ![Demo](./images/lb_x_aftermobile.png)
  
  
#### Step 4 - Personal advice in the brick-and-mortar store
  
  #### **Demo flow:**

  * To access the Personal Shopper Dashboard, click on the 3-dots in the desktop site's menu and select ```Personal Shopper```.

  ![Demo](./images/ps.png)
  
  * In the Personal Shopper Dashboard, you'll notice that the Email Address you used to register on the Luma - website has beeen filled out automatically for you. You can also enter any other email-address of choice to retrieve the customer profile. 
  
  ![Demo](./images/ps_id.png)
  
  * Click the ```Check``` - button. After 1-2 seconds, your Real-Time Customer Profile data is being shown to the store employee, including your browsing behaviour from the last couple of seconds and all of the important information like shoe size, shirt size and preferred color.
  
  ![Demo](./images/ps_response.png)
  
  
#### Step 5 - Call the most personal Call Center ever!

#### **Demo flow:**

  * To access the Personal Shopper Dashboard, click on the 3-dots in the desktop site's menu and select ```Personal Shopper```.

  ![Demo](./images/callcenter.png)
  
  * In the Call Center, you'll notice that the Mobile Number you used to register on the Luma - website has beeen filled out automatically for you. You can also enter any other mobile number of choice to retrieve the customer profile. 
  
  ![Demo](./images/callcenter_id.png)
  
  * Click the ```Check``` - button. After 1-2 seconds, your Real-Time Customer Profile data is being shown to the call center employee, including your browsing behaviour from the last couple of seconds.
  
  ![Demo](./images/callcenter_response.png)
  
With this, you've successfully completed this exercise.

[Next Step: Using Microsoft's Cognitive Services - Face Detection](./ex7.md)

[Go Back to Module 3](./README.md)

[Go Back to All Modules](../README.md)



