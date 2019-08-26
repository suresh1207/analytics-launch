### Exercise 3.1 - Update your demo website template

![SYTYCD](./images/sytycd.png)

In this exercise, the goal is to update your demo website - template to the latest standard of the SYTYCD-website, which makes it now really easy to be customised and personalized for your customer.

Download the [new version of the SYTYCD-website zip package](./downloads/sytycd_demo_site_v1.zip) to your computer, unzip it in a directory of your choice, f.i. on your Desktop:

![MAMP Setup](./images/mamp_app6.png)

**Mac:** Go to Launchpad and click on the grey MAMP-icon to start MAMP.

**Windows:** Go to your Windows Desktop and double-click on the grey MAMP-icon to start MAMP.

![MAMP Setup](./images/mamp.png)

MAMP will start and you'll see the below screen.

![MAMP Setup](./images/mamp1.png)

Click on Start Servers to start MAMP.

![MAMP Setup](./images/mamp2.png)

Servers are now running, and you can access the Start Page by clicking on 'Open WebStart page'.

![MAMP Setup](./images/mamp_localhost.png)

Currently, the old version of the 'La Boutique' demo site is installed in MAMP. You need to delete that and replace it with the new version of the SYTYCD - website.

**Windows:** On you Windows machine, go directly to C:\MAMP\htdocs

**Mac:** On your MacBook, go to Applications and locate the MAMP folder in the Applications list.

![MAMP Setup](./images/mamp_app1.png)

**Only for Mac:** Double-click to go in the MAMP-folder.

![MAMP Setup](./images/mamp_app2.png)

**Only for Mac:** Open the folder 'htdocs'.

![MAMP Setup](./images/mamp_app3.png)

**Fot both Windows and Mac:** Delete all files in this folder.

![MAMP Setup](./images/mamp_app4.png)

Go to the folder where you unzipped the zip-package of the new version of the SYTYCD - website. Copy all files and paste them in the 'htdocs' folder.

![MAMP Setup](./images/mamp_app6.png)

Go back to your web browser.

![MAMP Setup](./images/mamp_localhost.png)

Click on ```My Website``` to navigate to the new Platform demo website.

You should now see the ```Admin``` - page of the new SYTYCD website:

![MAMP Setup](./images/mamp_admin.png)

This is the visual confirmation that you've loaded the newest version of the SYTYCD - website.

To load one of the generic demo - brands, click on ```Select Brand```.

![MAMP Setup](./images/mamp_selectbrand.png)

On the next page, wait 1-2 seconds and select any of the available generic demo-brands from the dropdown

![MAMP Setup](./images/mamp_selectbranddropdown.png)

Click ```Save``` to save your brand selection. 

![MAMP Setup](./images/mamp_selectbrandsave.png)

You'll see a spinner on your screen and after 10 seconds, you'll see the configuration of the brand that you selected.

![MAMP Setup](./images/mamp_brandloaded.png)

Let's re-install your Launch tag on the SYTYCD-website.

Go to [https://launch-demo.adobe.com/](https://launch-demo.adobe.com/) and login with your personal login details.

Open the Launch-property that you built in one of the previous modules. This Launch-property is called ```La Boutique - ldap``` (replace ldap with your ldap).

To find your development-library tag, navigate to the "Environments"-tab in the Launch UI.

![Launch Setup](./images/env.png)

Locate your Development Environment, and click on the "Install"-icon on the right side of the screen:

![Launch Setup](./images/iconinstall.png)

You'll see a screen like this one, which contains the tag to implement on the website:

![Launch Setup](./images/tag.png)

Copy the <head> tag.

**On Mac** Go to the folder Applications > MAMP > htdocs > js and locate the launch.js file

**On Windows** Go to the folder C:\MAMP\htdocs\js and locate the launch.js file

![Launch Setup](./images/launchjs.png)

Open the file launch.js in your favourite text editor.

![Launch Setup](./images/launchjstext.png)

Go to Line 1, where you'll see the following:

```javascript
var launchTagUrl = ""
```

On Line 1, replace "" with your launch tag:

![Launch Setup](./images/launchtagsite.png)

This should be the result:

```javascript
var launchTagUrl = "//assets.adobedtm.com/staging/launch-EN23xxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"
```

![Launch Setup](./images/launchjstagok.png)

Save your changes in the launch.js file and reload your website.

After this change, the new version of the demo website template is ready and will load your Launch configuration again!

Let's now optimize and clean up your Launch code.

[Next Step: Update Launch Configuration & X-ray panel](./ex2.md)

[Go Back to Module 3](./README.md)

[Go Back to All Modules](../README.md)



